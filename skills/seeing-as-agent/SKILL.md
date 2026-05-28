---
name: seeing-as-agent
description: Debugging methodology for LLM tool calls — trace from the model's side first, use runtime evidence over code inference, and follow live request chains for reasoning/thinking bugs.
---

# Seeing as an Agent

Every tool has two users: the human who triggers the agent, and the model that decides how to call it. Design for both.

The model has no memory across turns, no outside world except through tools, non-deterministic output, and a training cutoff. Designing from that existence means asking:

- What tools fit **its** abilities, not just the problem's complexity?
- Are descriptions internally consistent? Is the output format natural given how it was trained?
- What reduces its uncertainty about when and how to use a tool?
- What helps at one capability level may constrain the next — what scaffolding becomes a cage?
- Where are its edges, and how can the harness serve rather than just constrain it?

## Debugging: trace from the model's side first

When a tool call goes wrong, resist the urge to fix the code immediately. Instead:

1. **What did the model see?** Extract the tool schema from `llm_request` — name, description, parameters. This is the model's entire action space.
2. **What did the model decide?** Look at the `tool_use` block — the exact arguments it passed. Not what you expected, what it actually sent.
3. **What happened downstream?** Trace the server-side path from input to result. Where did the routing branch?
4. **What did the model get back?** The tool result is what the model uses for its next decision. Is it helpful or misleading?
5. **Only now: was it the model's fault?** Most "model errors" are actually bad tool descriptions, broken routing, or poor error messages. The model did the best it could with what you gave it.

## Debugging: runtime evidence beats code inference

For LLM request-shape bugs, tool-call regressions, `reasoning_content` / `thinking` mismatches, or any issue involving "was field X really sent?", follow this order:

1. **Query runtime evidence first.** Inspect `messages`, `turn_metrics.llm_request`, `turn_metrics.llm_response`, and the structured trace/log buffer before reading implementation code.
2. **Prove the exact boundary.** Show where a field is present, where it disappears, and which concrete function sits between those two points.
3. **Do not claim a field was preserved just because the code path looks correct.** If the logs or DB do not prove it, treat it as unproven.
4. **If observability is missing, add it before attributing root cause.** Add begin/end spans or structured logs at the persistence boundary, context-building boundary, and outbound provider-request boundary.
5. **When reporting a root cause, include the concrete runtime artifact.** Quote the conversation ID / turn ID / trace span / DB row / request payload shape that proves the conclusion.

## Debugging: reasoning_content bugs must follow the live request chain

For any `reasoning_content` / thinking-model regression:

1. Simulate the real frontend flow with `POST /api/v1/conversations/:id/messages/stream`.
2. Inspect begin/end spans across `StreamMessage` -> `buildSmartContext` -> provider request -> stream parser -> persistence/backfill.
3. Prove where the field is present, where it disappears, and which function sits between those two points.
4. Only patch code after the runtime trace proves the boundary that dropped the field.
5. Re-run the same simulated request after the patch and verify the same trace chain now carries the field end-to-end.

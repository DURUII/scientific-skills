# Skills

Natural language tooling skills for Claude Code — organized by domain.

## Available Skills

### Scientific

| Skill | Purpose |
|-------|---------|
| `ccf-rank` | Query CCF conference/journal rank (`A/B/C`) and type (`conference`/`journal`) |
| `ieee-search-mcp` | Search IEEE Xplore through university library proxy session with browser MCP |
| `dlai-transcript-fetcher` | Fetch and organize video transcripts (VTT) from DeepLearning.AI courses |
| `paper-summary` | Research-grade single-paper analysis with evidence-grounded structured extraction |

### Dev

| Skill | Purpose |
|-------|---------|
| `seeing-as-agent` | Debugging methodology for LLM tool calls — trace from the model's side first, use runtime evidence over code inference |

## Installation

### Via skills.sh (Recommended)

Install this repository (all included skills):

```bash
npx skills i DURUII/scientific-skills
```

Install one specific skill only:

```bash
npx skills add https://github.com/DURUII/scientific-skills --skill ccf-rank
npx skills add https://github.com/DURUII/scientific-skills --skill seeing-as-agent
```

### Via Claude Plugin

Install repo as a plugin:

```bash
/plugin install DURUII/scientific-skills
```

Install only one skill directory:

```bash
/plugin install DURUII/scientific-skills/skills/ccf-rank
/plugin install DURUII/scientific-skills/skills/seeing-as-agent
```

### Manual Installation

Clone locally and add as local plugin:

```bash
cd ~/dev
git clone https://github.com/DURUII/scientific-skills.git
/plugin add ~/dev/scientific-skills
```

## Useful External Skills

- [arxiv-search by yorkeccak](https://skills.sh/yorkeccak/scientific-skills/arxiv-search): Semantic arXiv search with natural-language queries.

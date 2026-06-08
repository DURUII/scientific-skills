---
name: file-management
description: >
  Help users design, audit, and maintain a file management system — folder structures,
  naming conventions, storage strategies, and cleanup workflows. Use this skill whenever
  the user mentions organizing files, cleaning up folders, setting up a file structure,
  naming files, managing photos/albums, digital asset organization, cloud vs local storage,
  backups, or says things like "my files are a mess", "where should I put this",
  "help me organize my drive", "set up a folder structure", or asks about file naming.
---

# File Management System

A practical framework for organizing digital files — born from studying two distinct
approaches: a creator's asset-heavy workflow (Ami) and a knowledge worker's information
architecture (Jeffrey). The core insight: organize by **where you'll use it**, not where
you found it (David Allen).

## Guiding Principles

1. **Function over form.** A folder structure that looks beautiful but requires
   discipline you don't have is worse than a slightly messy one you actually maintain.
   The best system is the one you stick to.

2. **Organize by usage context.** Meeting notes for Project A go inside Project A's
   folder — not in a global "Meeting Notes" folder. When you open the project,
   everything is there. When you share it, everything goes with it.

3. **Name for searchability.** The goal is: 6 months from now, you can find this file
   in under 30 seconds. That means consistent naming conventions, not perfect ones.

4. **Don't over-optimize.** Five levels of nested folders with a rigid numbering
   taxonomy will be abandoned in two weeks. Start simple, add structure only where
   friction actually appears.

5. **Dual backup, always.** Cloud + local. Never a single point of failure for
   anything you can't afford to lose.

---

## Folder Structure

### The Numbered Framework

Borrowed from Johnny Decimal, simplified. Use two-digit prefixes to control sort order
and signal priority:

```
Root/
  01-Active/          # What you're working on right now
  02-Work/            # Work-related (projects, clients, deliverables)
  03-Personal/        # Personal documents, finances, health
  04-Reference/       # Things you look up regularly (templates, IDs, guides)
  05-QuickShare/      # Temporary staging area for files to share with others
  06-Assets/          # Reusable resources (fonts, icons, music, graphics)
  07-Archive/         # Completed projects, cold storage staging
  99-Archive/         # Deep archive — stuff you can't delete but rarely touch
```

Not every folder is required. Use only the categories your life actually needs.
The key rules:

- **Lower number = used more often.** If you access Personal files daily but Work
  files weekly, swap 02 and 03.
- **99 is always archive.** It's the "I can't delete this but I never look at it" bin.
- **Max 5 levels deep.** Beyond that, you'll get lost. The 6th level must be files only.
- **Max 99 folders per level.** You'll rarely need more than 10.

### Per-Project Structure

For active projects (especially creative/media work), use this template inside the
project folder:

```
ProjectName/
  01-Source/           # Raw footage, original files, source data
    Camera-A/
    Camera-B/
    Screen-Recordings/
  02-Working/          # Work-in-progress, drafts, iterations
  03-Output/           # Final deliverables (video, PDF, slides)
  04-Assets/           # Project-specific reusable elements
  README.md            # Brief project description, dates, status
```

This mirrors Ami's creator workflow: separate raw inputs from finished outputs so you
can archive source material independently of deliverables.

### Photo Management

For personal photo libraries:

1. **Cull with reverse selection.** Instead of marking favorites, delete everything
   first (move to trash), then recover the keepers from trash. Psychologically faster
   than heart-ing photos one by one.

2. **Album naming: `YYYY-MM Event`**
   - `2025-03 Japan Trip`
   - `2024-12 Mom Birthday`

3. **Archive cycle.** Every 2-3 years, move older photos from phone/cloud to external
   drive. Keep the last 2 years on-device for quick access.

4. **Dual storage.** Cloud library (iCloud/Google Photos) for sync across devices +
   periodic backup to external drive.

---

## Naming Conventions

### Date-Based Naming

Choose granularity based on how you'll search for it:

| Granularity | Format | Example | When to use |
|---|---|---|---|
| Year only | `YYYY` | `2025-Budget.xlsx` | Annual docs, budgets |
| Year + Quarter | `YYYY-QN` | `2025-Q1-Review.pptx` | Quarterly reports |
| Year + Month | `YYYY-MM` | `2025-05-Presentation.pptx` | Monthly recurring |
| Full date | `YYYY-MM-DD` | `2025-05-05-Training.docx` | One-off events |

**Rule of thumb:** the more granular the date, the more you need to know which parent
folder it lives in. Use full dates only when the parent folder provides context
(e.g., `Jeff's Sharings/2025-05-05-Inbox-Zero-Training.docx`).

### Type Keywords

Prefix or suffix files with a consistent type keyword. Pick 5-8 and stick to them:

```
doc-       # Documents, reports
notes-     # Meeting notes, personal notes
wk-        # Working/draft files
brief-     # Briefs, briefings
slides-    # Presentations
form-      # Forms, templates
ref-       # Reference material
```

Combined: `2025-Q1 doc-Quarterly-Business-Review`

**90% findability rule:** if you combine a project name + one type keyword, you should
find the file in search. That's the bar.

### Folder and File Naming Rules

- Use hyphens or underscores, never spaces (shell-friendly, URL-friendly)
- No special characters except `-` and `_`
- Lowercase or Title-Case consistently — pick one
- Keep names under 60 characters when possible
- Lead with what changes most (date) so sort order is useful

---

## Storage Strategy

### Three-Tier Architecture

| Tier | Medium | What lives here | Access frequency |
|---|---|---|---|
| **Hot** | Local SSD / laptop | Active projects, today's work | Daily |
| **Warm** | Cloud sync (iCloud, Google Drive) | Recent projects, shared docs | Weekly |
| **Cold** | External drive / NAS | Completed projects, archives | Monthly or less |

### Cloud Sync Tips

- **Pin frequently used folders offline.** In iCloud Drive, right-click > "Keep Downloaded"
  for folders you open daily. Avoids the spinner tax.
- **Use color labels / custom icons** on important folders. In macOS: right-click folder >
  Get Info > drag image onto the icon. Especially useful for external drives.
- **Quick Share folder** (05) is a staging area: copy slides/docs here before sharing,
  so the original stays in its organized location and you don't create duplicates.

### Backup Rule

**3-2-1:** 3 copies, 2 different media types, 1 offsite.

Practical version for most people:
1. Working copy on laptop
2. Cloud sync (iCloud / Google Drive / Dropbox)
3. Periodic backup to external drive

---

## Shared Files and Collaboration

When someone shares a file with you, decide immediately:

| Action | When | Why |
|---|---|---|
| **Do nothing** | One-off request, you'll edit once and forget | No clutter |
| **Make a copy** | Template you'll reuse, or you need a frozen snapshot | Independent from source |
| **Add a shortcut** | Ongoing document you need to find in YOUR system | Organize without moving |

For shortcuts: create a pointer in your own folder structure (e.g., inside `02-Work/ProjectX/`)
that links to the original. You organize your way, the owner organizes theirs.

**Starred / Flagged files:** maximum 5 at any time. If everything is starred, nothing is.
Criteria for starring:
1. Used every single day
2. Need quick access on phone too
3. Can't be easily searched for

---

## Metadata Tricks

For files you can't rename (shared docs, system files):

- **Google Drive:** Press D > Details > add keywords in the Description field.
  Now searchable by those keywords.
- **macOS Finder:** Cmd+I > add keywords in Comments field.
  Searchable via Spotlight, Alfred, or Raycast.
- **Windows:** Right-click > Properties > Details > add Tags.

---

## Audit Checklist

When helping a user clean up their files, run through this:

1. **Inventory.** What's in the root? What's taking up space?
2. **Frequency.** What do they actually open daily vs. never?
3. **Pain points.** Where do they waste time looking for things?
4. **Current habits.** What naming conventions do they already use (even informal ones)?
5. **Constraints.** Cloud storage limits? External drives? Team sharing requirements?

Then propose a structure that starts from their current state — don't prescribe a
perfect system they'll never adopt. Migration should be gradual:
- Week 1: Set up top-level folders, move the obvious stuff
- Week 2: Rename the 20 most-accessed files with consistent convention
- Month 1: Archive completed projects
- Ongoing: Apply the system to new files as they're created

---

## Quick Reference: Search Operators

| Platform | Operator | Example |
|---|---|---|
| Google Drive | `type:presentation` | Find all Google Slides |
| Google Drive | `from:colleague@co.com` | Files shared by specific person |
| macOS Spotlight | `kind:pdf` | Find PDFs |
| macOS Spotlight | `date:this week` | Recent files |
| Alfred/Raycast | `open <keyword>` | Launch pinned files fast |

---

## Anti-Patterns

Things that look organized but create friction:

- **Global "Meeting Notes" folder.** Scatters context. Keep notes with their project.
- **Color-coding everything.** Reserve colors for 2-3 critical categories max.
- **Too many subcategories upfront.** You're planning for a library you don't have yet.
  Add folders when you have 5+ files that belong together.
- **Renaming shared files.** Breaks the owner's ability to find them. Use keywords/metadata instead.
- **Keeping everything "just in case."** That's what 99-Archive is for — but set a
  yearly purge reminder.

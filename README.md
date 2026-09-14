# analyze-memory

A Claude skill for reading, comparing, searching and consistency-checking Claude's own memory entries, when the memory store itself is what the question is about.

Claude reads memory on its own to answer ordinary questions. That is not this skill. This skill applies when someone wants to know what the store says, where a remembered fact came from, whether two entries agree, or whether a decision recorded months ago is still the current one.

## What it does

Four operations, all read-only:

- **Read one entry.** What it says, when its content is dated (not when the file was last touched), and what in it may have aged.
- **Compare two or more entries.** Each one in its own voice, where they diverge, which is more recent and why. Never a merged version.
- **Search a topic across the store.** Every hit with its project, entry and content date, plus the scope actually covered, including the projects that hold no memory at all.
- **Check consistency.** Contradictions between entries, each one with both sides quoted, the kind of contradiction named, and what would have to be decided. The skill stops at the open questions; it does not settle them.

Searches and consistency checks over more than one entry are written as a report with a fixed frame, so that two runs a month apart can be compared.

## What it never does

It never writes, edits, appends to or deletes a memory entry, and it never carries out a correction as part of answering. When an entry is wrong or stale, it says so, names the entry and the line, and stops. Deciding what memory should say is a separate request.

It does not search conversation history, project documents or files on disk, which are different stores with their own tools. It does not import or export memory.

## Installation

Clone the repository into your Claude skills directory, so that `SKILL.md` sits directly inside a folder named `analyze-memory`:

```
git clone https://github.com/paolodalprato/analyze-memory.git ~/.claude/skills/analyze-memory
```

On Windows the skills directory is `%USERPROFILE%\.claude\skills\`. Claude picks the skill up from `SKILL.md` and loads the reference files as needed.

To install it on claude.ai instead, zip the folder with `analyze-memory/` as the top-level entry and upload the archive as a skill.

## Layout

```
SKILL.md                        the skill itself: scope, the four operations, the rules that hold across them
reference/entry-anatomy.md      what a memory entry is made of, and how to read a store written in several formats
reference/dating-and-recency.md the dates attached to an entry, which one means what, and how to rank versions
reference/output-shapes.md      the answer structure for each operation, and what each part of a report is for
reference/reading-at-scale.md   how to read a scope too large for one context without answering from descriptions
assets/report-template.md       the fixed frame of a report, to copy and fill
```

## Language

The instructions are written in English. The skill answers in whatever language the question was asked in, and quotations from entries stay in the language they were written in, because a translated quotation is no longer evidence.

## License

MIT. See `LICENSE`.

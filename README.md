# analyze-memory

A Claude skill for reading, comparing, searching and consistency-checking Claude's own memory entries, when the memory store itself is what the question is about.

Claude reads memory on its own to answer ordinary questions. That is not this skill. This skill applies when someone wants to know what the store says, where a remembered fact came from, whether two entries agree, or whether a decision recorded months ago is still the current one.

## Why I built it

Two reasons.

The first is that memory, the way it gets written, is disordered. Entries are added by many different sessions over months, and nothing reconciles them. Two entries can describe the same decision differently, a rule can be recorded with one threshold in one project and another threshold in the next, and an entry can be superseded without any signal saying so. A store like that has to be managed, and managing it starts with being able to see what it contains. This skill is the reading side of that work: it finds the duplicates, the contradictions and the stale entries, and it hands them back as a list of open questions with the evidence attached. It never fixes anything, because deciding what memory should say is the owner's job.

The second reason is that memory is also the only place where everything I have done with Claude is recorded across projects. The general memory and the project memories, read together, are a record of decisions, conventions and working habits that no single conversation holds. I wanted a way to use that record as a whole: to ask what was decided about a topic, in which project, when, and whether it still stands. Memory has real limits as a record. Entries are short, they carry no link back to the conversation that produced them, their dates are ambiguous, and a whole store can agree with itself and still be out of date. The skill is written around those limits, which is why every finding carries its source, every date says what it is based on, and every answer says what was not covered.

## What it does

Four operations, all read-only.

- **Read one entry.** What it says, when its content is dated (not when the file was last touched), and what in it may have aged.
- **Compare two or more entries.** Each one in its own voice, where they diverge, which is more recent and why. Never a merged version.
- **Search a topic across the store.** Every hit with its project, entry and content date, plus the scope actually covered, including the projects that hold no memory at all.
- **Check consistency.** Contradictions between entries, each one with both sides quoted, the kind of contradiction named, and what would have to be decided. The skill stops at the open questions; it does not settle them.

Searches and consistency checks over more than one entry are written as a report with a fixed frame, so that two runs a month apart can be compared.

## What it never does

It never writes, edits, appends to or deletes a memory entry, and it never carries out a correction as part of answering. When an entry is wrong or stale, it says so, names the entry and the line, and stops. Deciding what memory should say is a separate request.

It does not search conversation history, project documents or files on disk, which are different stores with their own tools. It does not import or export memory.

## How to ask

The skill triggers on questions about the memory store, not on questions that memory merely helps to answer. The examples below are templates: replace the parts in angle brackets. Ask in any language; the answer comes back in the language of the question, and quotations stay in the language of the entry.

Reading one entry:

- "What does the memory of project <name> say about <topic>, and when was it written?"
- "Show me the entry where you got the idea that <fact>. Where did it come from?"

Comparing entries:

- "Compare what projects <A> and <B> remember about <topic>, and tell me where they diverge. Do not merge them."
- "Which of these two entries is more recent, the one in <project A> or the one in <project B>, and what actually changed?"

Searching a topic:

- "Search all my memories for every mention of <topic> and tell me where each hit came from."
- "Go through everything you remember about <process> across all projects and list the entries that disagree."

Checking consistency:

- "Is anything in my memories contradicting itself about <topic>?"
- "That decision about <subject> I took in <month>, is it still the current one or did I supersede it somewhere?"
- "Run a consistency check across all my memories, every project, and give me a report I can reuse next month."

Questions that do not trigger the skill: asking Claude to remember something new, asking it to fix or delete an entry, searching the conversation history, searching project documents or files on disk. Those are different requests, and the first two are writes, which this skill refuses by design.

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

## License

MIT. See `LICENSE`.

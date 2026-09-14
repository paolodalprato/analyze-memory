# Entry anatomy

What a memory entry is made of, and how to read a store whose entries were not all written the same way.

Nothing here is a specification. Memory formats differ between accounts and change over time, so treat this file as a field guide: expect these shapes, recognize them when they appear, and verify against the entries actually in front of you rather than against this description.

## The two parts

An entry is a text file with a header block and a body. The header is key-value metadata; the body is the content.

## Header fields

Field names vary. These appear commonly enough to plan for.

| Field | What it holds | Notes |
|---|---|---|
| `name` | The entry's identifier | Usually matches the filename stem |
| `description` | One line saying what the entry covers | The field the first search pass reads |
| `sources` | Where the entry came from | A list, not a single value |
| `aliases` | Other names the subject goes by | Useful for matching a question to an entry |
| `type` | A category for the entry | Present in some stores only |
| `imported_at` | When the entry was written into this store | Present on migrated entries; see `dating-and-recency.md` |

Three consequences.

**Fields are not always flat.** The same import can produce one entry with `type` at the top level and another that nests the same information inside a `metadata:` block alongside keys of its own. Read the header as a tree rather than as a fixed list of keys, and look one level down before concluding a field is absent.

**Absence of a field is not absence of the information.** An entry with no `type` is not untyped content, it is content written under a convention that had no `type` field. Do not report a missing field as a defect.

**`sources` is the best single predictor of body style.** Entries that share a source value were usually written by the same process under the same convention, so once you have read one of them you know roughly what the rest look like.

## Body styles

Two shapes recur, and a store can hold both at once.

**Tagged fact lines.** The body is short lines, one fact each, often under headings, and often carrying an inline marker in square brackets at the start of the line. Markers distinguish where a fact came from or how well established it is. This style is compact, easy to scan, and easy to compare mechanically between entries.

**Prose notes.** The body is continuous writing with headings, emphasis, sometimes tables, and sometimes labeled sections along the lines of "why this matters" or "how to apply this". This style carries reasoning, history and qualification that the line style cannot hold, and it is where free-text supersession markers usually appear.

Neither style is more authoritative. They answer different questions, and a store containing both is normal rather than broken.

**Reading implication.** A line-style entry can be compared field by field, so divergence between two of them is easy to state precisely. A prose entry has to be read whole before it can be compared, because its qualifications are distributed through the text and a single sentence pulled out of it can reverse its meaning. Never compare a prose entry on the strength of one extracted line.

## Inline markers

Both styles use bracketed markers inside the body. Conventions vary, and the same marker can mean different things in different stores, so read a few entries before relying on a marker's meaning.

Markers generally do one of two jobs: they say how the fact was obtained, or they say how certain it is. Report a marker's presence when it bears on the answer, and quote it rather than translating it into your own confidence language, because the person's own convention is more meaningful to them than your paraphrase.

Markers can also be compound, combining a claim about the source with a claim about confidence inside one bracket. Report the whole marker rather than reducing it to the half you recognize, since the qualification is usually the half that gets dropped.

Where a store marks facts by certainty, that marking is evidence for a consistency check. Two entries that disagree, one of them marked as established and the other not, is a different situation from two entries that disagree with equal confidence.

## Cross-references

Entries refer to each other in at least two forms: a wiki-style link wrapping an entry name in double brackets, and a bare filename mentioned in prose, sometimes with the folder it sits in. Neither form carries a full path.

**A reference does not always point at another entry.** Entries routinely name files that live outside the memory store altogether, reports, plans, working documents, and the reference files of a skill. Those targets are real, and the reference is not broken; they are simply not reachable from memory. Work out which case you are in before reporting anything. Telling someone a reference is broken when the file is sitting on their disk sends them looking for a problem that does not exist, and it costs you their trust in every other finding in the same answer.

Resolve these when a question depends on them. When a reference does not resolve, say so explicitly. A dangling reference is a finding, not a nuisance: it usually means a file was renamed, or that a migration moved part of a set and left the rest behind, and it tells the person something about their store that they will not learn any other way.

A reference that resolves is also worth following, because references frequently exist precisely to carry a correction. An entry that points at another one is often pointing at the version it replaced.

## Index entries

Some stores keep a per-project index entry that holds little more than the project's name and a one-line description. It identifies the project; it is not a summary of its contents and it should not be read as one. When an index entry is the only entry in a project, treat that project as having no substantive memory.

**An index entry is written once and not maintained.** Two failures follow, and both have been seen in practice.

The name can be stale. Renaming a project updates the container the environment reports, and leaves the index entry holding the previous name. So take a project's name from the environment, never from the index entry alone, and when the two differ say both, because the person needs to know their store and their interface disagree about what the project is called. Stale names are also a source of false duplicates: two projects can look like namesakes inside memory while being distinctly named outside it.

The description can be empty of content. An index entry created by an import sometimes carries the project's name in the description field instead of a description of the project. That is not a description, and it should not be quoted as one. Where sibling projects carry a real descriptive line and one does not, the gap is worth reporting as a finding about the store.

## What an entry is not

An entry has no link back to the conversation that produced it. Whatever context surrounded the writing is gone, and the entry is the whole record; SKILL.md says how to answer when a question assumes otherwise.

# Dating and recency

How to tell when an entry's content was true, and how to rank two versions of the same thing. This is the part of memory analysis where a confident wrong answer is easiest to produce.

## The problem

"Which of these is more recent" sounds like a metadata lookup. It is not. Several dates attach to a single entry, they mean different things, and the one the tooling hands you first is often the least informative of them.

## The four dates

**The last-modified time reported by the tool.** When the entry file was last touched. This is a fact about the file, not about the content. Any operation that rewrites a file updates it, including one that changed nothing of substance.

**An `imported_at` field in the header.** When the entry was written into this store from somewhere else. It dates the migration.

**A date in the filename.** Some naming conventions carry a month or a date in the stem. It usually dates the content, and it is usually approximate.

**Dates inside the body.** Written by whoever wrote the entry, naming when a decision was taken, a test was run, or an observation was made. These are the only dates that say when the content was true.

## The hierarchy

Rank recency using, in order:

1. **Dates stated in the body**, because they date the content directly.
2. **A date in the filename**, when the body carries none.
3. **`imported_at`**, and only as a floor, since it says the content is at least that old.
4. **The file's last-modified time**, and only when nothing else is available, with the uncertainty stated in the answer.

Where the sources disagree, the body wins, because a person wrote it about the subject while the timestamps were written by machinery about the file.

## The failure this prevents

A bulk import writes every entry within the same few seconds. Afterwards, the last-modified times of an entire archive are identical to the second, and they all say the import moment rather than anything about the content. Content spanning a year collapses into one instant.

Ranked on those timestamps, a set of entries recording decisions from different months comes out as simultaneous, or in whatever arbitrary order the writes happened to complete. The ranking looks precise, is reported to the second, and is meaningless.

The tell is easy to spot: several entries sharing a last-modified time to within seconds or minutes, especially across an entire project. When you see that, the timestamps are recording a bulk operation and must be set aside for ranking.

## Free-text supersession outranks every date

Some entries say in their own prose that another entry is outdated, or that a conclusion recorded elsewhere has since been corrected. Look for that language and quote it when it appears.

It beats any date comparison, because a person wrote it deliberately, knowing both versions. A date comparison is an inference about which version came later; a written supersession marker is direct testimony about which one is right, and those are not the same claim. An entry can be newer and still wrong.

## When the evidence does not settle it

Say so. "Both entries date from July and neither says which supersedes the other" is a correct answer, and it tells the person exactly what they need to resolve.

The failure mode to avoid is ranking on a weak signal and presenting the result as settled. Someone who is told which entry is newer will act on it; someone who is told the archive cannot say will go and check. The second outcome is better whenever the evidence is thin, so make the basis for every ranking visible in the answer.

## Content that ages, and content that does not

A supersession check is worth running on entries recording decisions, conventions, prices, version numbers, tool configurations, and anything described as current or recent. These expire.

It is rarely worth running on entries recording stable preferences, long-standing working habits, or background facts about a person or a project. These do change, but not on a timescale where a date comparison helps.

Say which kind an entry holds when flagging it, so the person can judge whether a check is worth their time.

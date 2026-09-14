# Reading at scale

How to read a scope that does not fit in one context, without giving up the rule that answers come from entries and not from their descriptions.

## The problem is room, not time

Entries are small and reading them is quick. What runs out on a large scope is the space to think afterwards. A reader who has taken in a hundred entries has spent the context that the comparison needs, and the comparison is the whole point: a contradiction lives between two entries, and nobody who reads one of them can see it.

So reading and comparing are two jobs, and past a certain size they cannot share a context. The threshold is roughly twenty entries, and it is a judgement rather than a constant: twenty long prose notes crowd a context that a hundred one-line entries would not.

## The extraction schema

Whoever does the reading returns the same structure for every entry, whatever the question was. A fixed schema is what lets the comparison happen later, by someone who never saw the originals.

For each entry:

- **Path**, exactly.
- **Header fields**, the keys as spelled, noting any nesting.
- **Body style**, tagged lines, prose, mixed, or empty.
- **Dates inside the body**, each with the fragment of text it sits in.
- **Internal retractions**, where the entry states something and later withdraws it, both parts quoted.
- **Cross-references**, each quoted, with whether the target looks like another entry or a file outside memory.
- **Open items**, anything declared pending, to verify, to correct, to decide, quoted.
- **Claims on the tracked subjects**, quoted.

The tracked subjects are fixed before the reading starts, from the question. Adding one afterwards means reading everything again, so it is worth a minute to name them all up front, and worth asking the person whether any are missing.

## The rule that makes the schema work

**Quote verbatim. Never paraphrase a tracked claim.**

This is not fussiness about provenance. Two entries that both say roughly "avoid bullet lists" may hold one rule or two: "no bullet lists in body text" and "lists only when structurally necessary" are genuinely different instructions, and one of them is stricter than whatever governs. Two different paraphrases of a single rule, on the other hand, look like a disagreement that does not exist.

Only the original wording tells the two cases apart, and only a numeric value read off the page can be compared with another numeric value. A reader who summarises destroys exactly the evidence the comparison runs on.

Quotes stay in the language they were written in. Translating a quotation makes it a paraphrase again.

## Three ways to separate reading from comparing

Pick by what the environment offers, not by preference.

**With sub-agents.** Split the scope into groups of comparable size and give each reader the exact list of paths, the schema, the tracked subjects, and the verbatim rule. Tell each reader to stop and say so if the memory tools are not available to it, rather than improvising. Readers do not judge, compare or rank anything; they extract. The comparison happens once, afterwards, across all their returns. Group by project where possible, so that one reader holds a whole project's internal consistency.

**Without sub-agents, with a filesystem.** Read in batches yourself and write each batch's extraction to a file as you go, then compare the files. Slower, same result. The discipline that matters is writing the extraction out and not carrying it in your head, because carrying it is what consumes the room you will need.

**Without either.** Narrow the scope until it fits, and say in the answer exactly how far it was narrowed and what was left out. A partial reading declared as partial is a usable result. A partial reading presented as complete is the failure this whole file exists to prevent.

## What the comparison does with the returns

The comparison is a separate pass over the extractions, and it looks for things no single reader could see: the same subject answered differently in two projects, a value that drifts across several entries, a reference whose target one reader saw and another did not, an entry whose internal dates sit far from everything else in the store.

Group by subject rather than by project, since contradictions are properties of subjects. Keep every claim attached to the path it came from; a finding without its source cannot be checked, and an analysis nobody can check has no standing against the entries it contradicts.

## What to check before trusting the run

A reader that returned nothing for a whole entry either found an empty entry or failed. The two look identical in the output, so confirm which. A reader that returned paraphrases rather than quotes has to be re-run on its group; the comparison built on it would be unsound, and no amount of care afterwards repairs it.

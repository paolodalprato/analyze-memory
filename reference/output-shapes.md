# Output shapes

The structure of the answer for each of the four operations.

These are shapes, not templates to fill in mechanically. A one-entry question deserves a short paragraph, not a report with empty headings. Scale the structure to the question, keep the order, and drop sections that have nothing in them rather than writing "none" under a heading. The one exception is coverage, which is never dropped, because an empty coverage line is itself a finding.

The language rule in SKILL.md applies to everything below.

## Read one entry

1. **What it says.** The substance, in your own words unless a verbatim extract was requested.
2. **When its content is dated**, and on what basis. Say which date you used and why, following `dating-and-recency.md`.
3. **What might have aged.** Decisions, conventions, versions, prices and configurations, if the entry holds any. Name them, and say what would have to be checked to confirm them. Omit this section for an entry holding only stable facts.
4. **Anything odd.** Broken cross-references, a description that does not match the body, markers worth knowing about.

## Compare two or more entries

1. **Each entry on its own**, one short block each, labeled with its project and name. Keep them separate. Do not begin by synthesizing.
2. **Where they diverge**, subject by subject. State what each side says on that subject.
3. **Where they agree**, briefly, because agreement is evidence too and it narrows what the person has to think about.
4. **Which is more recent**, with the basis for the ranking visible, or a statement that the evidence does not settle it.
5. **What a reconciliation would have to decide.** The open questions, not your answers to them.

Two things this shape exists to prevent.

**No merged version, ever**, for the reasons given in SKILL.md under "Compare two or more entries".

**Divergence is not automatically conflict.** SKILL.md lists the cases; when one of them applies, saying so is a result worth reporting.

## Search a topic

1. **The hits.** Each one carries what it says, which project and entry it came from, and the date of its content. A hit without provenance cannot be acted on, because the person cannot go back and check it. Name projects as SKILL.md prescribes under "Name sources the way the person sees them".
2. **Grouping.** Hits that agree, gathered. Hits that disagree, marked as disagreeing and left unresolved here. Resolution belongs to the consistency check, which is a different question and usually a different request.
3. **Coverage.** What was actually searched: which scope, and which projects were skipped for having no memory. This line is the difference between "the topic is not in your memory" and "the topic is not in the part of your memory I could read".

Order hits by relevance to the question, not by project order, and say what the ordering is.

## Check consistency

For each contradiction found:

1. **The subject** it concerns, stated in one line.
2. **Each side**, quoted or closely paraphrased, with its source.
3. **The kind of contradiction**, named from the list in SKILL.md under "Check consistency".
4. **Which side appears more recent**, with the basis shown, or a statement that it cannot be told.
5. **What has to be decided** to resolve it.

Alongside the contradictions, report what the entries themselves declare unfinished, as SKILL.md requires under "Check consistency".

Then stop. Do not decide, do not rank the contradictions by importance unless asked, and do not propose edits as actions to take now.

Close with the scope covered, in the same form as the search operation.

A run that finds nothing is a real result and should be reported as one, with its coverage, rather than being softened into a list of things that are merely slightly different.

## Extracts

When a verbatim extract is requested, give the text as it stands, mark clearly where it was cut, and keep the commentary separate from the quoted material so the two cannot be confused. An extract is evidence, and evidence that has been tidied is no longer evidence.

## The report

When the threshold in SKILL.md is met, the answer takes the shape of a report. The body is still the operation's own shape from the sections above; the report adds a frame around it that makes one run comparable with the next.

`assets/report-template.md` holds the frame to copy. What each part is for is set out here.

**Header.** Five lines, no more:

- the date the analysis was run;
- the operation and the subject;
- the scope requested, in the person's own terms;
- the scope in perimeter, meaning how many entries across which projects, and which projects hold no memory;
- how many of those entries were read in full, and by what method.

The last three are separate lines on purpose. The gap between what was asked for and what was reachable is the most useful thing in the header, and merging them hides it. The gap between what was in perimeter and what was actually opened is the one that decides how much the report is worth: an analysis covering a hundred entries and reading a dozen is a different document from one that read all hundred, and a single merged line lets the two pass for each other.

**Body.** The operation's shape, unchanged. Give each finding a short stable label so a later run can say whether it persists; the template explains the convention.

**Where the store agrees.** What was checked and found consistent, briefly, including against any governing source outside memory. A report of anomalies alone misrepresents an archive: someone reading only what is broken concludes that everything is. Knowing that a rule holds in every entry that states it is worth as much as knowing where it does not, and it is the part the findings never oblige anyone to write.

**Anomalies in the store.** A closing section for what the run noticed about the archive rather than about the question. Unresolved references, index names that no longer match the project, two projects carrying the same name, entries whose description repeats their name instead of describing them, entries that contradict themselves internally, clusters of entries sharing a bulk-write timestamp, projects holding nothing but an index.

These findings belong to no single question, and they are the reason someone runs the analysis a second time. Omit the section when there is nothing in it rather than writing that nothing was found.

**The name-to-identifier table.** Close a report with a table pairing every project named in it with its internal identifier. It is what lets the person verify a finding in their own interface, and what lets a later run match findings project by project after a rename.

**What the report does not cover.** What was not checked and why, and anything reported as declared by an entry rather than verified at the source. State plainly that nothing was resolved: the analysis stops at the proposal, and deciding what memory should say belongs to its owner.

**Where the report goes.** Into the conversation by default. Into a file when the person asks, or when the environment has an obvious place for one. Name the file descriptively, in the language the analysis is written in, and say where it was written.

**What a report is not.** It is not a longer answer. If the material would fit in four paragraphs of prose, four paragraphs of prose is the better report, and the header still earns its place because it is what makes the run repeatable.

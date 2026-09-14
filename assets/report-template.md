# Report template

Copy the frame below and fill it. The frame is fixed; the body is not.

**How to use it.** Sections marked FIXED always appear, even when the answer is short. Sections marked SHAPED are replaced by whatever the findings actually are. A section with nothing in it is deleted, never filled with "none", except coverage, which always stays; `reference/output-shapes.md` says why.

The language rule in SKILL.md applies to the whole report.

---

## [Title: what was analyzed, in a few words]

**Date of the analysis:** [date]
**Operation:** [read / compare / search / consistency check] — [subject]
**Scope requested:** [in the person's own words]
**Scope in perimeter:** [how many entries, across which projects, and which projects hold no memory]
**Read in full:** [how many of those entries were opened and read end to end, and by what method]

<!-- FIXED. The last two lines stay separate; reference/output-shapes.md says why. -->

---

### [Body]

<!-- SHAPED. The operation's own structure, from reference/output-shapes.md.
     Do not impose categories on the material; let the findings decide the sections.
     Give every finding a short stable label, see "Labels" below. -->

---

### Where the store agrees

<!-- FIXED. What was checked and found consistent, including against any governing source
     outside memory. Keep it brief; reference/output-shapes.md says why it matters. -->

---

### Structural anomalies

<!-- FIXED unless genuinely empty. What the run noticed about the archive rather than about the
     question; the list of what counts is in reference/output-shapes.md. -->

---

### Projects referenced

<!-- FIXED. A table pairing every project named in the report with its internal identifier,
     as SKILL.md prescribes under "Name sources the way the person sees them". -->

---

### What this report does not cover

<!-- FIXED. What was not checked and why; reference/output-shapes.md says what belongs here. -->

---

## Labels

Give each finding a short, stable label, `[SUBJECT-NN]`, built from the subject rather than from its position in the report: `[STYLE-01]`, `[VAULT-PATH-02]`. Reuse the same label for the same finding in every later run.

This is what the template is really for. A finding that persists across runs is the most actionable thing an archive produces, and without stable labels somebody has to count by hand across old reports to notice it. With them, the next run can say which findings are new, which are gone, and which have now been open for several cycles.

When a finding is resolved, keep its label in the next report with the outcome, once. Then drop it.

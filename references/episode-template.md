# Episode Template

Use this structure, adapting headings into natural Bengali while retaining identifiers.

For a requested excerpt or single-path run, merge adjacent sections and shorten prose as needed, but retain: snapshot/coverage note, one atomic timeline, evidence labels with anchors, Holmes' Pause, strongest Near-Miss, one Case Card, and a causal cliffhanger.

```markdown
# Season NN, Episode NN — [Original title]

> Case scope: [journey]
> Evidence snapshot: [commit or `unknown`]; worktree: clean / dirty / unknown; inspected-path overlap: yes / no / unknown
> Coverage status: [new / continuation / revisit]

## Cold Open — [anomaly]

[Short cinematic opening phrased as a possibility or question.]

## ঘটনাস্থলে আগমন

[Where this occurs, why value or authority passes here, and the exact components involved.]

## আজকের চরিত্র

| Character | Technical identity | Real authority/state |
|---|---|---|

## স্বাভাবিক রাতের Timeline

### T0 — Before
- Caller:
- Relevant state:
- Asset/liability position:

### T1 — Entry
- Function/instruction:
- Authorization and validation:

### T2 — Calculation and calls
- Formula/conversion:
- Internal calls:
- External call/CPI:
- Return assumptions:

### T3 — Writes and transfers
- Storage/account writes:
- Token/value movement:
- Events/logs:

### T4 — After
- Post-state:
- Obligation created or discharged:
- Invariant expected to hold:

## Evidence Board

| Label | Observation | Source anchor | Limits |
|---|---|---|---|

## Holmes' Pause

[Ask one specific deduction question. Give the reader enough facts to reason.]

## Counterfactual Crime

Change one condition only:

1. Changed condition
2. First affected check/calculation
3. State or value divergence
4. Potential observable harm
5. Missing fact required to call it exploitable

## The Near-Miss

[Present the strongest intended-behavior, guard, privilege, or harmlessness explanation.]

## Holmes' Notebook

- Newly learned mechanism:
- Trust assumption:
- Temporal assumption:
- Uncovered edge:
- Mental picture in one sentence:

## Case Cards

### CB-S01E01-Q01 — [Falsifiable question]
- Suspected invariant:
- Actor/capability:
- Minimal sequence:
- Evidence:
- Strongest disproof:
- Proof target:
- Question confidence: low / medium / high

## Cliffhanger

[One source-caused link to the next episode; do not assert a bug.]
```

## Atomic trace rule

For every important path, include these atoms when applicable:

`caller → authority → input domain → pre-state → check → normalization → calculation → external observation → external interaction → state write → asset transfer → event → post-state → later consumer`

If an atom cannot be established, mark it `UNKNOWN` and create a ledger gap. Do not bridge it with narrative invention.

## Encoding rule

Keep all skill and episode Markdown in UTF-8. When a shell displays Bengali or symbols incorrectly, re-read explicitly as UTF-8 before treating the text as corrupted. Prefer plain ASCII arrows such as `->` in machine-oriented traces when terminal encoding is uncertain.

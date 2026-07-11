# Verification Handoff

## Independence rule

The verifier receives the question, raw source targets, and observed facts. It must not inherit Casebook's atmosphere as evidence or its suspected outcome as a verdict. Require the verifier to rebuild the causal path and try to disprove it.

## Packet

```yaml
id: CB-S01E01-Q01
title: One falsifiable question
source_episode: casebook/seasons/season-01/episode-01.md
snapshot:
  repository: ""
  commit: ""
  dirty_worktree: false
ecosystem: ""
question_confidence: low|medium|high
suspected_invariant: ""
actor:
  identity: ""
  capability: ""
  unavailable_capabilities: []
entry_points: []
state_targets: []
asset_or_obligation: ""
observed_facts:
  - label: CODE FACT|TEST EVIDENCE|DOC CLAIM|RUNTIME/CONFIG FACT
    claim: ""
    source: "path:symbol-or-line"
minimal_sequence: []
potential_harm: ""
required_preconditions: []
strongest_disproof: ""
missing_evidence: []
recommended_verification:
  - source trace
  - focused unit test
  - fuzz or invariant test
  - fork/integration test
duplicate_family: ""
```

## Verifier obligations

Ask the proof workflow to:

1. Confirm the current snapshot and relevant scope.
2. Trace exact source and state-transition order.
3. Establish realistic actor capability and reachable preconditions.
4. Search for guards and downstream correction.
5. Create the smallest decisive test when useful.
6. Include negative controls and intended-behavior checks.
7. Separate internal code defects from trusted/config/external dependency risk.
8. Return a hard bounded verdict with evidence.

## Ledger return

Record verdict, proof artifact path, decisive evidence, and remaining limitation against the original Case Card. Never delete the original question merely because it was rejected; rejected mysteries teach the reader which guard actually closes the case.

# Evidence Discipline

## Evidence labels

- `CODE FACT`: directly visible in the current source snapshot.
- `TEST EVIDENCE`: demonstrated by an existing or executed test; state scope and whether mocks are involved.
- `DOC CLAIM`: asserted by documentation but not necessarily enforced.
- `RUNTIME/CONFIG FACT`: verified deployment, role, parameter, account, or external-state information.
- `INFERENCE`: a bounded conclusion from cited facts.
- `OPEN QUESTION`: missing evidence prevents a conclusion.

Never convert one class into another silently. A NatSpec statement is not a code guarantee. A mocked unit test is not mainnet runtime evidence. An X-Ray observation is not current-source proof until rechecked.

## Source reconciliation

For every X-Ray claim used in an episode:

1. Locate the current implementation.
2. Check the active code path rather than only interface or dead code.
3. Check overrides, inheritance, feature flags, account constraints, modifiers, and call-site preconditions.
4. Check tests for intended behavior and mocks for hidden assumptions.
5. Record one of: `VERIFIED`, `PARTIALLY VERIFIED`, `CONTRADICTED`, `STALE`, `NOT FOUND`, or `NEEDS RUNTIME EVIDENCE`.

## Snapshot discipline

Record branch/commit when available and whether the worktree is dirty. Do not mix behavior from committed source, local edits, historical audit commits, or generated artifacts without saying so.

Use this concise disclosure in every episode:

```text
Evidence snapshot: <commit-or-unknown>; worktree: <clean|dirty|unknown>; inspected-path overlap: <yes|no|unknown>
```

If dirty files overlap the narrated path, distinguish current working-tree behavior from committed behavior or limit the claim explicitly.

## Claim construction

Use this structure:

```text
Observation → source anchor → bounded meaning → limitation → open question
```

Avoid vague statements such as "this may be vulnerable." Name the state, assumption, actor, ordering, or conservation relationship that creates the question.

## False-positive guard

Before emitting a Case Card, test the idea against:

- explicit access control and realistic attacker capability;
- initialization and deployment constraints;
- downstream validation;
- revert/atomicity behavior;
- token/program semantics;
- rounding direction and actual magnitude;
- time and ordering prerequisites;
- trusted-role or configuration boundaries;
- documented intended behavior;
- known duplicate/root-cause relationship;
- whether the supposed harm is externally observable.

Keep the card if meaningful evidence remains missing, but state the strongest disproof.

## Narrative safety

- A fictional scene may illustrate a real mechanism, but must not introduce facts.
- Hypothetical actors must be labeled hypothetical.
- Exact numbers must come from code/config/tests or be labeled examples.
- Dialogue cannot serve as evidence.
- Do not describe a hypothetical loss as having occurred.

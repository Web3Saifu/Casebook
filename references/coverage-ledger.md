# Coverage Ledger

## Purpose

The ledger prevents narrative fluency from masquerading as codebase completeness. Track semantic coverage, not just files read.

During read-only or excerpt-only runs, maintain the ledger in working context and print only the relevant coverage summary. Persist this template only when file creation is authorized.

## Status values

- `UNSEEN`: not inspected.
- `MAPPED`: role and connections identified.
- `TRACED`: a concrete path followed through relevant checks, calls, and writes.
- `PRESSURED`: at least one counterfactual and strongest guard examined.
- `HANDED_OFF`: proof-ready question sent to verification.
- `VERIFIED`: independent proof verdict linked.
- `BLOCKED`: missing source, dependency, configuration, or runtime evidence.

## Required tables

```markdown
## Snapshot
- Repository:
- Commit/branch:
- Dirty worktree:
- X-Ray artifacts:
- Ecosystem:

## Season index
| Season | Journey | Dependencies | Status | Episodes |

## Entry-point coverage
| Component | Entry point/instruction | Value/state affected | Episode | Status | Gap |

## Invariant coverage
| Invariant | Source | Paths that may change it | Pressure status | Case Cards |

## Trust coverage
| Authority/dependency | Capability/data supplied | Failure mode visited | Episode | Status |

## Case Card queue
| ID | Root cause | Question confidence | Proof status | Verdict/evidence |

## Known gaps
| Gap | Why unknown | What evidence closes it | Priority |
```

## Completion rule

Do not call a scope fully covered merely because every source file was opened. Require all relevant entry points to be at least `TRACED`, all declared/high-value invariants to be mapped to their mutating paths, all trust boundaries to be visited, and all `BLOCKED` gaps to be disclosed.

Generated code, vendored dependencies, test helpers, and out-of-scope components may be excluded, but record the exclusion and its reason.

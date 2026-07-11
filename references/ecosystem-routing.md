# Ecosystem Routing

Identify the execution and account model before planning the serial. Use only the relevant route and inspect project-specific frameworks.

## EVM and Solidity

Trace:

- `msg.sender`, `msg.value`, delegatecall context, proxy/implementation storage;
- modifiers, inheritance, overrides, libraries, hooks, fallback/receive;
- checks-effects-interactions, callbacks, reentrancy, approvals, token quirks;
- block/timestamp assumptions, CREATE/CREATE2, signatures, nonces, chain IDs;
- storage slots, accounting units, decimals, rounding, unchecked math;
- upgrade, governance, pause, oracle, bridge, and keeper boundaries.

## Solana and Anchor

Trace:

- instruction, program ID, account list, signer/writable/owner constraints;
- PDA seeds, bumps, canonical derivation, initialization, close/realloc;
- account discriminator and serialization boundaries;
- lamports and SPL Token/Token-2022 authority, mint, decimals, extensions;
- CPI targets, remaining accounts, duplicate/mutable account aliasing;
- sysvars, clock/slot/epoch assumptions, rent, transaction atomicity;
- upgrade authority, validator/oracle/bridge dependencies.

Treat accounts as explicit participants in the cast. The same account appearing in multiple roles can itself be a clue.

## Move-family systems

Trace resources, abilities, capabilities, signer authority, object ownership, module/friend boundaries, generic type constraints, shared objects, and transaction ordering. Preserve chain-specific semantics.

## CosmWasm and message-driven systems

Trace storage, sender/funds, submessages, replies, cross-contract queries, asynchronous IBC packets, acknowledgement/timeouts, and admin/migration authority.

## Generic onchain systems

Always establish:

- execution atomicity and failure semantics;
- identity and authorization model;
- authoritative state location;
- asset standard and transfer behavior;
- cross-component call semantics;
- time/finality model;
- deployment/configuration facts;
- offchain or external truth dependencies.

Do not translate EVM concepts mechanically into another ecosystem. If semantics remain uncertain, mark them `OPEN QUESTION` and inspect authoritative local code/docs before narrating.

# LimitFlow — proposed 90-day builder roadmap

This is a forward-looking development plan, not a list of shipped features. Milestones depend on QMS Testnet stability, compatible QWAP integration interfaces and successful security testing.

| Period | Focus | Planned deliverables | Acceptance gate |
|---|---|---|---|
| Days 1–30 | Public demo quality and execution safety | Clear expired-order indicators; robust RPC/error states; expanded negative tests; documented deployed contracts and example receipts; independent-RPC witness investigation | Reproducible build, public read-only demo and passing tests; no wallet or transaction pathways exposed on the public dashboard |
| Days 31–60 | QWAP feasibility and guarded integration | Review QWAP-supported swap interfaces and quote sources; prototype a separate testnet adapter; simulate slippage, approvals, liquidity and expiry cases | Demonstrated bounded testnet simulations and written integration limitations; no public real-asset execution |
| Days 61–90 | Controlled testnet pilot and feedback | Incremental keeper trial only after independent review and fresh-state checks; user testing of order lifecycle; operational runbook; performance and failure reports | Measured testnet order outcomes and explicit go/no-go review for the next phase |

## Dependencies

- Confirmation of current QMS network and any announced testnet reset.
- Availability and suitability of independently operated read-only RPC sources, where possible.
- A documented QWAP integration interface compatible with the order contract's safeguards.
- Budget for monitoring and, only if necessary, inexpensive VPS-based keeper operation.

## Risks and mitigations

- **Mock-rate versus live liquidity:** Keep simulated pricing explicitly labelled until verified integration exists.
- **RPC history inconsistency:** Fail closed, preserve evidence and require recovery review.
- **Double fills, stale state, expiry:** Revalidate on-chain order state and balances before each execution.
- **Keeper keys and secrets:** Never ship them in browser code, public repositories or public environment variables.
- **Testnet instability:** Treat public demonstrations as testnet evidence, not production guarantees.

## Intended users

QMS testnet participants exploring conditional order execution, followed by wider DEX users only if QWAP integration and security work prove feasible.

# LimitFlow

**Limit-order infrastructure prototype on QMS Testnet** · Independent, unofficial project

[**Live read-only dashboard**](https://limitflow-qms-demo.vercel.app) · [**Testnet contract**](https://testnet.qmsscan.io/address/0xBE3BB99682BBD569aC124a4858f7cC0a0BE7a9a7) · [**Development roadmap**](ROADMAP.md) · [**Testnet evidence**](TESTNET_EVIDENCE.md)

## What is LimitFlow?

LimitFlow explores user-defined limit orders on the QMS EVM-compatible testnet: traders specify an input amount and a minimum acceptable output, while a separate keeper checks whether an order can be filled. The present demonstration uses **valueless mock dUSD and dQMS tokens, a mock swap adapter, and a controlled test rate**. It does not trade through QWAP.

The public website is deliberately **read-only**. Visitors can inspect deployed contracts, order statuses, testnet balances and a historical settlement example without connecting a wallet or signing transactions.

## Demonstrated so far

- A Solidity limit-order contract deployed on QMS Testnet (chain ID **19480**).
- Testnet order creation, cancellation and successful single-order settlement with mock tokens.
- An order activity dashboard and contract registry served on Vercel.
- Local test coverage for order eligibility, shared-liquidity planning, simulation guards, checkpoint recovery, read-only receipt inspection and restart evidence continuity.
- Read-only multi-order **planning and simulation**; this is **not** a claim that live autonomous multi-order execution is complete.

## Public demonstration

**Website:** https://limitflow-qms-demo.vercel.app

On the dashboard, review the order table, select an order to inspect its parameters, and open the explorer links in the settlement and contract registry sections. On-chain `Open` status alone does not mean an order is unexpired or currently executable.

**QMS chain ID:** `19480`
**LimitFlow contract:** `0xBE3BB99682BBD569aC124a4858f7cC0a0BE7a9a7`
**Example keeper-executed testnet fill transaction:** [View on explorer](https://testnet.qmsscan.io/tx/0xf39420c375c77c0592e7b49fb7ca3a2fd7e67e7a2532231b62e17a48b962065b)

See [TESTNET_EVIDENCE.md](TESTNET_EVIDENCE.md) for the historical demonstration snapshot. Testnet data can change or be reset.

## What is not yet implemented

- QWAP swap routing or use of actual QWAP liquidity.
- Production-grade price feeds or real-market execution.
- Unattended, general-purpose multi-order settlement.
- Mainnet or real-asset trading.

## Why QMS?

QMS provides an EVM-compatible testnet on which to test on-chain order custody and execution. LimitFlow's next research and integration milestone is to connect a guarded executor to suitable QMS ecosystem liquidity, subject to API/contract feasibility and security review.

## Next 90 days

See [ROADMAP.md](ROADMAP.md) for specific milestones, dependencies and success criteria.

## Project status and source access

This is a **public project showcase**, not a source-code release. The active development repository remains private while its execution tooling and wallet-related files receive further review. Documentation here does not authorize signing or trading. The prototype is independent and is **not affiliated with or endorsed by QMS or QWAP**.

**Builder contact:** [CaptainTee on GitHub](https://github.com/CaptainTee) · [Project demo](https://limitflow-qms-demo.vercel.app)

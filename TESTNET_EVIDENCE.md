# LimitFlow — testnet demonstration evidence

Evidence summarized from the project's locally observed testnet and public dashboard on **31 October 2026**. These are historical observations, not independent third-party audits or guarantees of finality.

## Chain and contract

- **Network:** QMS Testnet, chain ID `19480`
- **LimitFlow contract:** [`0xBE3BB99682BBD569aC124a4858f7cC0a0BE7a9a7`](https://testnet.qmsscan.io/address/0xBE3BB99682BBD569aC124a4858f7cC0a0BE7a9a7)
- **Public dashboard:** https://limitflow-qms-demo.vercel.app
- **Mock adapter:** `0xF3aA2151CEa9Da41d5Fca081190044a992EED773`
- **Mock tokens:** dUSD and dQMS, both without monetary value
- **Controlled test rate at observation:** `1 dUSD → 1.60 dQMS` (not a QWAP or market quote)

## Historical order activity

| Order | Observed on-chain status | Note |
|---|---|---|
| #1 | Filled | Public dashboard displays a demo settlement of 100 dUSD input, 120 dQMS minimum and 130 dQMS received |
| #2 | Cancelled | Cancellation demonstrated |
| #3 | Filled | Mock-token order settlement |
| #4 | Filled | Guarded single-order keeper transaction was observed and locally verified |
| #5 | Open | Subject to its expiry and current eligibility; not executed in the read-only batch preview |
| #6 | Open | Subject to its expiry and current eligibility; not executed in the read-only batch preview |

**Example order #4 transaction:** [0xf39420c375c77c0592e7b49fb7ca3a2fd7e67e7a2532231b62e17a48b962065b](https://testnet.qmsscan.io/tx/0xf39420c375c77c0592e7b49fb7ca3a2fd7e67e7a2532231b62e17a48b962065b)

The read-only batch planner simulated orders #5 and #6 at 160 mock dQMS each, with shared inventory constraints, **without broadcasting either fill**. Offline evidence and witness checks intentionally return HOLD instead of authorizing execution when required proof is absent.

## Public website checks

On 31 October 2026, the project operator reported:

- Homepage HTTP `200` and `/api/state` HTTP `200`.
- `/api/state` returning chain ID `19480`, contract presence and six historical orders.
- Public access via Chrome Incognito without Vercel authentication.
- No wallet connect, mint, approval, cancellation or fill buttons visible on the deployed read-only homepage.

These are operator-observed checks, **not an independent security audit**. The production source code, RPC configuration and blockchain state may evolve after this snapshot.

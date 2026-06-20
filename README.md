# Hey, I'm Tonchain — DeFi Infrastructure Engineer

Building production-grade infrastructure for Uniswap V4 — fully on-chain, no off-chain relayers, no trusted intermediaries.

[![Uniswap Hook Incubator — UHI9](https://img.shields.io/badge/Uniswap_Hook_Incubator-UHI9-FF007A?logo=uniswap&logoColor=white)](https://atrium.academy)
[![Solidity 0.8.26](https://img.shields.io/badge/Solidity-0.8.26-363636?logo=solidity&logoColor=white)](https://soliditylang.org)
[![DApps live](https://img.shields.io/badge/DApps-2_live-22c55e)](https://il-aware-hook.vercel.app)

---

## 🚀 Featured Work

| Project | What it does | Live DApp | Chains | Tests |
| --- | --- | --- | --- | --- |
| **[il-aware-limit-order-hook](https://github.com/impetus82/il-aware-limit-order-hook)** | Limit orders that become yield-bearing positions and **rebate impermanent loss** from accrued yield. UHI9 Hookathon submission. | [il-aware-hook.vercel.app](https://il-aware-hook.vercel.app) | Unichain | **53 / 53** ✅ |
| **[limit-order-hook-v4](https://github.com/impetus82/limit-order-hook-v4)** | Fully on-chain limit orders for Uniswap V4, executed in `afterSwap`. | [limit-order-hook-v4.vercel.app](https://limit-order-hook-v4.vercel.app) | Base · Unichain | **38 / 38** ✅ |

---

## 🧩 il-aware-limit-order-hook — *IL-Aware Limit Orders*

Turns a passive limit order into a yield-bearing position and compensates the user for impermanent loss out of the yield it earns. Submitted to the **UHI9 Hookathon** (Impermanent Loss & Yield theme), live on **Unichain mainnet**.

- **Oracle-free IL rebate** — impermanent loss derived from `sqrtPriceX96` deltas via a 2nd-order Taylor approximation; `rebate = min(yield, IL)`. No external price feeds.
- **Yield routing** — executed output is deposited into an **ERC-4626** vault until claim.
- **Orders as NFTs** — every order is an **ERC-721**: composable and tradable on secondary markets.
- **O(1) tick scanning** — doubly-linked list of *active* ticks only; swap cost scales with populated ticks crossed, not range width.
- **Anti-DoS execution** — failed orders don't revert the swap: they emit and re-queue, with gas metering to avoid OOG.
- **Flash accounting** — atomic settlement via Uniswap V4 native accounting, no ERC-20 transfer overhead.
- **Deployed (Unichain)** — hook `0x8C19f1641946c662308000bB4E2Eaf684c81d4CE`
- **Stack** — Solidity 0.8.26 · Uniswap V4 · OpenZeppelin (ERC-721 / ERC-4626) · Foundry · Next.js · wagmi v2 · viem · RainbowKit

---

## 🔁 limit-order-hook-v4 — *Fully On-Chain Limit Orders*

Production limit orders for Uniswap V4 with automated, gas-bounded execution. Live on **Base** and **Unichain** mainnet.

- **Architecture** — `afterSwap` hook · O(1) tick-bucket doubly-linked list · anti-DoS graceful execution
- **Fee model** — 5 BPS execution fee · gas-metered batch execution · 150k gas cutoff
- **Audit scope** — [AUDIT_SCOPE.md](https://github.com/impetus82/limit-order-hook-v4/blob/main/AUDIT_SCOPE.md)
- **Stack** — Solidity 0.8.26 · Uniswap V4 · Foundry · Next.js · wagmi v2 · RainbowKit

---

## 🛠 Tech Stack

- **Contracts** — Solidity · Foundry · Uniswap V4 · OpenZeppelin (ERC-721 / ERC-4626)
- **Frontend** — Next.js · TypeScript · wagmi v2 · viem · RainbowKit
- **Chains** — Base · Unichain · Arbitrum (upcoming)
- **Ops** — Gnosis Safe 2-of-3 · Vercel · GitHub Actions

---

## 📫 Contact

[Telegram @yurka_e](https://t.me/yurka_e) · egoshin_crypto@proton.me

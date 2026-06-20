<div align="center">

# Tonchain

**DeFi Infrastructure Engineer — building on-chain primitives for Uniswap V4**

[![Portfolio](https://img.shields.io/badge/Portfolio-impetus82.github.io-FF007A?logo=githubpages&logoColor=white)](https://impetus82.github.io)
[![Uniswap Hook Incubator — UHI9](https://img.shields.io/badge/Uniswap_Hook_Incubator-UHI9-FF007A?logo=uniswap&logoColor=white)](https://atrium.academy)
[![Solidity 0.8.26](https://img.shields.io/badge/Solidity-0.8.26-363636?logo=solidity&logoColor=white)](https://soliditylang.org)
[![DApps live](https://img.shields.io/badge/DApps-2_live-22c55e)](https://il-aware-hook.vercel.app)

Production-grade hooks that run **fully on-chain** — no off-chain relayers, no keepers, no trusted intermediaries.
Two live DApps shipped to **Base** and **Unichain** mainnet.

[Portfolio](https://impetus82.github.io) · [Telegram](https://t.me/yurka_e) · egoshin_crypto@proton.me

</div>

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

**Stack:** `Solidity 0.8.26` · `Uniswap V4` · `OpenZeppelin (ERC-721 / ERC-4626)` · `Foundry` · `Next.js` · `wagmi v2` · `viem` · `RainbowKit`

**Deployed:** hook on Unichain → [`0x8C19…d4CE`](https://uniscan.xyz/address/0x8C19f1641946c662308000bB4E2Eaf684c81d4CE)

---

## 🔁 limit-order-hook-v4 — *Fully On-Chain Limit Orders*

Production limit orders for Uniswap V4 with automated, gas-bounded execution triggered directly inside swaps. Live on **Base** and **Unichain** mainnet.

- **Self-executing** — orders fill in the `afterSwap` hook as the pool crosses their tick. No keepers, no relayers.
- **O(1) tick buckets** — doubly-linked list of populated ticks for constant-time lookup during execution.
- **Anti-DoS, graceful execution** — a failing order never bricks the swap path.
- **Bounded gas** — 5 BPS execution fee, gas-metered batch execution, 150k gas cutoff per swap.
- **Audit-ready** — documented scope and invariants for external review: [AUDIT_SCOPE.md](https://github.com/impetus82/limit-order-hook-v4/blob/main/AUDIT_SCOPE.md).

**Stack:** `Solidity 0.8.26` · `Uniswap V4` · `Foundry` · `Next.js` · `wagmi v2` · `RainbowKit`

---

## 🧭 How I build

- **Fully on-chain** — execution lives in the contract, not in a bot. If it needs a keeper or a relayer to work, it isn't done.
- **Gas as a hard constraint** — bounded, metered execution paths; no unbounded loops on the swap hot path.
- **Anti-DoS by design** — one failing order must never brick the pool for everyone else.
- **Test-first** — full Foundry suites covering unit, integration, and adversarial paths before anything ships.
- **Mainnet or it didn't happen** — deployed, verifiable, with a live frontend.

---

## 🛠 Tech Stack

- **Contracts** — Solidity · Foundry · Uniswap V4 · OpenZeppelin (ERC-721 / ERC-4626)
- **Frontend** — Next.js · TypeScript · wagmi v2 · viem · RainbowKit
- **Chains** — Base · Unichain · Arbitrum *(upcoming)*
- **Ops** — Gnosis Safe 2-of-3 · Vercel · GitHub Actions · Foundry CI

---

## 📫 Contact

- 🌐 Portfolio — **[impetus82.github.io](https://impetus82.github.io)**
- 💬 Telegram — **[@yurka_e](https://t.me/yurka_e)**
- ✉️ Email — **egoshin_crypto@proton.me**

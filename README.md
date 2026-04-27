# Hey, I'm Tonchain — DeFi Infrastructure Engineer

**Focus**: Uniswap V4 Hooks · On-chain order execution · DeFi tooling  
**Currently**: Building production-grade limit orders on Base & Unichain  
**Program**: [Uniswap Hook Incubator (UHI9)](https://atrium.academy) · Cohort 9

---

## What I'm Building

### 🔁 [limit-order-hook-v4](https://github.com/impetus82/limit-order-hook-v4)
Fully on-chain limit orders for Uniswap V4 — no off-chain relayers, no trusted intermediaries.

- **Deployed**: Base mainnet (`0x45d971...c4040`) · Unichain mainnet (`0x9138F6...8040`)
- **Architecture**: `afterSwap` hook · O(1) tick bucket linked list · anti-DoS graceful execution
- **Fee model**: 5 BPS execution fee · gas-metered batch execution · 150k gas threshold
- **Stack**: Solidity 0.8.26 · Uniswap V4 · Foundry · 38/38 tests passing
- **Frontend**: [Live demo](https://limit-order-hook-v4.vercel.app) — Next.js · Wagmi v2 · RainbowKit

---

## Tech Stack

**Smart Contracts**: Solidity · Foundry · Uniswap V4 · OpenZeppelin  
**Frontend**: Next.js · TypeScript · Wagmi v2 · RainbowKit  
**Infra**: Gnosis Safe (2-of-3 multisig) · Vercel · GitHub Actions  
**Chains**: Base · Unichain · Arbitrum (coming)

---

## Contact

[Telegram](https://t.me/yurka_e) · egoshin_crypto@proton.me

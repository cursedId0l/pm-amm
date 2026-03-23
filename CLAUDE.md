
# pm-AMM Hook — Agent Context File
> Read this before doing anything on this project.

## What We're Building
A Uniswap v4 hook that implements Paradigm's **pm-AMM** (prediction market AMM) design from their November 2024 paper.

**Paper:** https://www.paradigm.xyz/2024/11/pm-amm
**Repo:** cursedId0l/uniswap-v4-pm-amm (GitHub)

## Why This Matters
- Zero production implementations exist of this paper
- Binary outcome token markets (Polymarket-style) have terrible LP economics today
- Paradigm's design solves Loss-versus-Rebalancing (LVR) using Black-Scholes / Gaussian score dynamics
- First implementation = major ecosystem contribution + research credibility

## Background Reading (in order)
1. Paradigm pm-AMM paper: https://www.paradigm.xyz/2024/11/pm-amm
2. Uniswap v4 hooks docs: https://docs.uniswap.org/contracts/v4/overview
3. Our research notes: ~/.openclaw/workspace/research/prediction-market-amm/
4. Thesis node: ~/.openclaw/workspace/research/nodes/theses/pm-amm-doppler-thesis.md

## Build Approach
- 15 minutes per day, small daily commits to keep GitHub green
- Start simple: stub → price function → full hook logic
- No rush — quality over speed

## Current Status (as of 2026-03-20)
- [x] forge init uniswap-v4-pm-amm
- [x] Repo created on GitHub
- [ ] read article: intro,  
- [ ] Add v4 dependencies (v4-core, v4-periphery)
- [ ] Write README
- [ ] Stub hook contract with NatSpec
- [ ] Implement price function from paper

## Key Concepts to Understand Before Coding
- What is LVR (Loss-versus-Rebalancing)?
- How does Black-Scholes apply to AMM pricing for binary outcome tokens?
- How do Uniswap v4 hooks work? (beforeSwap, afterSwap callbacks)
- What does Doppler do differently? (Dutch auction bonding curve, also a v4 hook)

## Stack
- Foundry (forge)
- Solidity 0.8.x
- Uniswap v4-core, v4-periphery
- PRBMath (likely needed for fixed-point math)

## Questions to Answer as We Build
- Which hooks does the pm-AMM need? (beforeSwap? afterSwap? beforeInitialize?)
- How do we represent the probability state p ∈ (0,1) in the contract?
- How do we handle the Black-Scholes price function in Solidity without a math library?
- What's the minimal viable first version?

- realize i need more knowledge on prediction markets


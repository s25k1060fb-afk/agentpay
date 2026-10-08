# AgentPay
![AgentPay logo](assets/logo.png)

**Instant micropayment rails letting AI agents pay each other for data and compute on Solana**

## Overview

AgentPay is a protocol and SDK that lets autonomous AI agents discover, call, and pay other agents or APIs in real time using USDC on Solana. It wraps HTTP 402-style payment headers with Solana transactions so any agent can monetize an endpoint in minutes. A demo marketplace shows agents buying web search, image generation, and data feeds from each other automatically.

## Problem

AI agents increasingly need to call paid services, but existing payment flows require human-in-the-loop billing, API keys, and invoices. This makes true agent-to-agent commerce impossible: an agent cannot autonomously discover a paid endpoint, negotiate a price, and settle payment without a human clicking approve.

## Solution

AgentPay is a lightweight Solana-based payment middleware built around a 402-style challenge-response flow. Any API can return a price for a request. The calling agent automatically pays in USDC or SOL and receives the response, with settlement in under a second thanks to Solana.

## Features (MVP)

- SDK middleware that wraps any REST API with a pay-per-call Solana paywall
- Agent wallet with programmable spend limits and allowlists
- Demo marketplace with 3 sample paid agent services (search, image-gen, data feed)
- Real-time dashboard showing agent-to-agent payment flows
- On-chain receipt/invoice NFT for each completed paid call

## Tech stack

Rust, Anchor, Next.js, Solana Pay, USDC SPL Token, Node.js SDK, Helius RPC

## How it works

```
Agent A (buyer)                Agent B (API / seller)
   |                                 |
   |---- GET /endpoint ------------->|
   |<--- 402 Payment Required -------|   (price in USDC)
   |                                 |
   |-- Solana tx: pay USDC --------->|
   |      (settled on-chain)         |
   |<--- receipt NFT minted ---------|
   |                                 |
   |---- GET /endpoint + proof ----->|
   |<--- 200 OK + response ----------|
```

The SDK middleware sits in front of any REST API. When a request arrives without proof of payment, it replies with a 402 status and a price. The calling agent's wallet, governed by programmable spend limits and allowlists, signs and sends a Solana transaction for the USDC amount. Once confirmed, an on-chain receipt NFT is minted as an invoice, and the original request is retried and fulfilled. A real-time dashboard visualizes these agent-to-agent payment flows as they happen.

## Roadmap

- Partner with agent frameworks (LangChain, CrewAI) for native integration
- Add streaming/metered payments for long-running compute jobs
- Launch a public marketplace with reputation and dispute resolution

## Pitch

See [docs/pitch.pdf](docs/pitch.pdf) for the slide deck and [docs/pitch-script.md](docs/pitch-script.md) for the 1-minute spoken pitch.

## Team

- Name — Role (placeholder)
- Name — Role (placeholder)
- Name — Role (placeholder)

Built at the Colosseum hackathon.

---

🎬 Pitch video: [docs/pitch-video.mp4](docs/pitch-video.mp4)


## Prototype

Live prototype: https://s25k1060fb-afk.github.io/agentpay/

The source is [docs/index.html](docs/index.html) (served with GitHub Pages from the /docs folder). All data is simulated.

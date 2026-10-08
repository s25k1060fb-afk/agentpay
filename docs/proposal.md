# AgentPay

_Instant micropayment rails letting AI agents pay each other for data and compute on Solana_

## Summary

AgentPay is a protocol and SDK that lets autonomous AI agents discover, call, and pay other agents or APIs in real time using USDC on Solana. It wraps HTTP402-style payment headers with Solana transactions so any agent can monetize an endpoint in minutes. A demo marketplace shows agents buying web search, image generation, and data feeds from each other automatically.

## Target users

AI developers building autonomous agents, API providers wanting micropayment monetization

## Problem

AI agents increasingly need to call paid services but existing payment flows require human-in-the-loop billing, API keys, and invoices, making true agent-to-agent commerce impossible.

## Solution

A lightweight Solana-based payment middleware with a 402-style challenge-response flow lets any API return a price, and the calling agent auto-pays in USDC/SOL to receive the response, settled in under a second.

## MVP features

- SDK middleware that wraps any REST API with a pay-per-call Solana paywall
- Agent wallet with programmable spend limits and allowlists
- Demo marketplace with 3 sample paid agent services (search, image-gen, data feed)
- Real-time dashboard showing agent-to-agent payment flows
- On-chain receipt/invoice NFT for each completed paid call

## Chains

Solana

## Tech

Rust, Anchor, Next.js, Solana Pay, USDC SPL Token, Node.js SDK, Helius RPC

## Category

AI

## Why now

Agentic AI adoption is exploding in 2025 and the lack of native machine-to-machine payment rails is a widely cited blocker; Solana's speed/cost makes it the natural settlement layer.

## Roadmap

- Partner with agent frameworks (LangChain, CrewAI) for native integration
- Add streaming/metered payments for long-running compute jobs
- Launch a public marketplace with reputation and dispute resolution

# Awesome-Agent-Financial-Transaction-Gatekeepers

## Top Agent Financial Transaction Gatekeepers Ecosystem



**Curated List of SaaS Products & Open-Source GitHub Projects**  

*Focused on Agent Payment Authorization, Budget Guardrails & Human-in-the-Loop Controls*  

**Last updated: March 2026**



This repository tracks notable **SaaS platforms** and **open-source projects** for **Agent Financial Transaction Gatekeepers**. These tools provide the authorization layer between autonomous AI agents and payment execution—enforcing spending limits, merchant allowlists, approval thresholds, and audit trails before funds move.



**Examples** include Sphere, Helio, Rain Cards, Crossmint, Stripe Agent Toolkit, Skyfire Systems, Payman AI, Openfort, Nevermined, and AP2 (Agent Payments Protocol) (the category leaders).



**Open-source emphasis**: This section is heavily expanded with every major active project for self-hosting policy engines, deterministic spending gates, and auditable agent payment workflows—ideal for platform engineers, fintech developers, and organizations seeking transparent, vendor-independent agent spend governance.



Contributions welcome! Open a PR to add/update entries. Keep descriptions factual and link to official sites.



## Table of Contents

- [SaaS/Hosted Platforms](#saas-hosted-platforms)

- [Open-Source GitHub Projects](#open-source-github-projects)

- [How to Contribute](#how-to-contribute)

- [Disclaimer](#disclaimer)



## SaaS/Hosted Platforms



- **[Skyfire Systems](https://skyfire.xyz/)**  

  KYA (Know Your Agent) identity and payment tokens enabling agents to log in and pay sellers. Issues signed JWT tokens with spending caps, request-count ceilings, and expiry directly embedded. Funding via card, ACH, wire, or USDC. Tokenized cards with Visa, Mastercard, and Discover. Spending limits per agent enforced at the token layer .



- **[Payman AI](https://paymanai.com/)**  

  Governed AI agents that move money inside banks and credit unions. Policy layer with approvals, audit trail, and kill switch. Dashboard policies include per-transaction, daily, and monthly limits plus an explicit approval **Threshold**—spend above it requires manual sign-off before clearing. Custody remains with the regulated institution, never with Payman .



- **[Crossmint](https://www.crossmint.com/)**  

  Agent wallets, virtual cards, and stablecoin orchestration. Features spending limits, **merchant allowlists**, and **human approval above a threshold**. Non-custodial stablecoin wallets with support for Visa virtual cards, x402, and AP2 protocols .



- **[Stripe Agent Toolkit / Issuing](https://stripe.com/)**  

  Machine payments infrastructure letting businesses accept payments from agents. **Shared Payment Tokens** carry usage and expiry limits per token. Issuing exposes **allowed_categories/blocked_categories** spending controls. Card-network enforcement declines the authorization before funds move—a hard stop .



- **[Openfort](https://www.openfort.io/)**  

  Policy Engine v2 for agent payments. Rail-agnostic authorization service called before a payment executes. Documents both an **enforced boundary** and an **audit trail** tying transactions back to the authorizing principal. Not tied to a single card network or blockchain .



- **[Nevermined](https://nevermined.io/)**  

  Scoped **delegations** for agent payments. Permission-token model treating budgets as revocable, server-enforced constraints. Demonstrated multi-vendor autonomous payments where agents paid independent services without pre-arranged API keys. Budget works like a prepaid card with server-enforced limit .



- **[Sphere](https://sphere.xyz/)**  

  Agent payment authorization and spend governance. Provides policy evaluation, approval workflows, and audit trails for autonomous agent financial transactions.



- **[Helio](https://helio.com/)**  

  Agent payment gatekeeper with budget controls and human-in-the-loop escalation. Enforces spending policies before payment execution.



- **[Rain Cards](https://raincards.com/)**  

  Agent card programs with spending controls at the card-network layer. Enforces authorization before settlement.



- **[AP2 (Agent Payments Protocol)](https://ap2-protocol.org/)**  

  Open protocol from Google Cloud for agent-initiated transactions. Uses **mandates** to represent intent, assembled purchase, and final payment. Approval signs a Cart Mandate creating immutable record of items and price. Compatible with cards, stablecoins, and real-time bank transfers. 60+ participating institutions including Visa, Mastercard, PayPal, Coinbase, and Ethereum Foundation .



## Open-Source GitHub Projects



- **[SpendShield](https://github.com/SpendShield/SpendShield)**  

  Open-source payment safety layer for Python and MCP agents (MIT). Born from a real incident where a "test order" charged ¥396 for real. Features **agent identity (KYA)** with per-agent budgets and blacklists, **four deterministic gates** (dry_run, budget, max_amount, approval), **prompt injection defense**, and **encrypted secret vault** (AES-256). Rules are code, not AI opinion—agents cannot argue past them. MCP server enables Claude Code and OpenClaw integration .



- **[AgentGate](https://github.com/AgentGate/AgentGate)**  

  Open-source policy engine for agentic payments (framework-agnostic). Not a payment processor. The **authorization layer** between an AI agent and any payment API. Features **policy schema** (per-transaction limits, daily/weekly/monthly caps, merchant category allowlists, time-of-day restrictions), **evaluation engine** returning ALLOW/DENY/ESCALATE, **human-in-the-loop hooks**, **audit trail** with agent reasoning, and **velocity controls** preventing runaway loops. YAML or Python policy definition .



- **[closegate](https://github.com/closegate/closegate)**  

  Open-source policy gate for finance AI agents (MIT). Built for SOC 2 compliance with **append-only SQLite audit log** with BEFORE UPDATE/DELETE triggers. **Four pillars**: Policy gate (T0 read-only, T1 reversible, T2 reversible+above-materiality requires HITL, T3 irreversible requires dual-HITL), hash-chained audit log, HITL approval envelopes with server-side segregation of duties, and eval harness. 986 passing tests. Docker Compose demo in 60 seconds .



- **[PrismAgenticPay](https://github.com/PrismAgenticPay/PrismAgenticPay)**  

  Open-source payment authorization and spend controls service. Turns signed payment mandates and server-owned authority data into explicit **ALLOW/REVIEW/STALLED/REFUSE** decisions. Features **ES256 signature verification** for payment mandates, **multi-bucket ledger** reserving spending capacity before execution, **durable operation identity** surviving restarts, and **signed receipts** (ES256). SQLite transactions persist holds, decisions, cases, audit events, and payment operations together .



- **[Sovereign-OS](https://github.com/Sovereign-OS/Sovereign-OS)**  

  Charter-governed operating system for autonomous AI agents with verifiable fiscal discipline (arXiv paper). Five layers: **Charter** (constitutional YAML with daily burn cap, total budget ceiling, minimum job margin), **CEO/Strategist** (goal decomposition), **CFO/Treasury** (fiscal gatekeeping with balance check, daily burn cap, job profitability), **Workers with SovereignAuth** (earned-permission execution via dynamic TrustScore), and **Auditor** (output verification). All financial flows recorded in append-only UnifiedLedger .



- **[lango](https://github.com/langoai/lango)**  

  Go-based agent payment framework with built-in governance. Features **USDC payments on EVM chains**, **X402 auto-pay protocol** (Coinbase SDK, EIP-3009 signing), **payment limits and daily usage** tracking, **approval system** for sensitive tools, **budget allocation status**, **escrow service**, and **Security Sentinel** engine. CLI commands for payment balance, history, limits, and info .



- **[openAgentPay](https://github.com/neosun100/openAgentPay)**  

  Open, pluggable Agent Payments platform for AWS Bedrock AgentCore (MIT). **7-Layer Guardrail** system with **22 protocol adapters** (x402, AP2, ACP, MPP, L402) and **61 wallet connectors**. 4,114 tests passing across 5 languages. Live on HashKey Chain Testnet. Features spend analytics, wallet matrix, and certification CLI .



- **[envoy-pay](https://github.com/envoy-pay/envoy-pay)**  

  On-chain payment authorization with EIP-712 signed auths. **EnvoyFacilitator** validates signer against canonical **ERC-8004** agent wallet, enforces per-(agent, token) **rolling-window spending limits**, splits amount into net (merchant) and fee (treasury), and emits Settled events. Live on Celo Mainnet with sub-cent fees and ~5s finality. Agents are first-class ERC-8004 NFTs, 8004scan-indexed .



- **[afrinex/agent](https://github.com/afrinex/agent)**  

  LangGraph-powered conversational AI agent for financial transactions (npm). Features **Human-In-The-Loop (HITL)** with configurable **approvalThreshold**—any transaction exceeding it suspends graph execution and requires explicit human approval. Built on LangGraph state machine with agentNode, toolsNode, and hitlNode. Checkpointer enables pause/resume mid-graph .



- **[FinScope Agent](https://github.com/fangyunok/finscope-agent)**  

  Profile-driven financial agent with confirmed cross-session memory and deterministic calculations. Features **Decimal precision** (50-digit context) for all monetary calculations—model never touches numbers. **Hard constraint filtering** before product ranking. **Three-way verification** (proposal_id + version + content hash) for memory confirmation. 100 tests passing, 20/20 simulated cross-session sequences passing .



### Additional Strong Open-Source Options



- **[Thoughtworks Authority Model](https://www.thoughtworks.com/insights/blog/generative-ai/why-agentic-payments-require-executable-model-organizational-authority)** — Framework for executable organizational authority in agentic payments. Connects agent identity to legal principal, business purpose, owner, budget, counterparty class, and time-bounded mandate. Evaluates cumulative effect of individually permitted transactions .

- **[AP2 Reference SDK](https://ap2-protocol.org/)** — Google's reference implementation for agent payment mandates with constraint evaluation.

- Community **n8n** workflows for agent payment approval routing and audit alerting.



**Frameworks for building custom systems**: Combine **SpendShield** or **AgentGate** as the deterministic policy gate with **closegate** for SOC 2-compliant audit trails, **PrismAgenticPay** for cryptographic mandate verification and durable operation identity, **Sovereign-OS** for charter-governed fiscal discipline, and **SQLite/PostgreSQL** for persistence—creating a fully self-hosted, enterprise-grade agent financial transaction gatekeeper platform.



## How to Contribute



1. Fork the repo.

2. Add/edit entries in `README.md` (follow existing format).

3. Include: name, link, 1–2 sentence description, and whether it's SaaS or open-source.

4. Submit PR with a short explanation.



Star the repo if you find it useful!



## Disclaimer



- This is a **community-curated** list — not exhaustive and not an endorsement.

- Agent payment gatekeepers handling financial transactions must comply with payment regulations (PCI-DSS, PSD2, SOC 2, etc.) and applicable financial services law.

- Self-hosted open-source solutions require proper security hardening, cryptographic key management, and ongoing maintenance. A spending cap alone tells you spend stayed under a number—not who is accountable for the number. Require at least one of: a numeric cap enforced automatically, a human-approval step above a threshold, or an audit trail tying each transaction back to the authorizing principal . Test limits before trusting them: send a transaction just above the cap and confirm it's **declined, not just logged** .



---



**Made for fintech engineers, platform teams, compliance officers, and developers building transparent agent payment governance.**  

Let's make Agent Financial Transaction Gatekeepers more open, data-driven, and auditable.

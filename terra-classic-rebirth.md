# TERRA CLASSIC 2030

## From a Stablecoin Blockchain to Complete Infrastructure for the Multichain Builder

**Version 2.2** — Strategic Vision Document

> ⚠️ **Disclaimer**: This is a *vision and strategic direction* document, not a guaranteed execution plan. The financial projections are hypothetical scenarios, not promises. Every economic change described depends on on-chain governance, development resources, and market adoption. Nothing here is financial advice.

---

# EXECUTIVE SUMMARY

Terra Classic survived the largest collapse in the history of cryptocurrencies. Since then, the network has retained four assets that money cannot buy back:

* A functional, uninterrupted blockchain
* Active on-chain governance
* Independent validators
* A resilient global community

However, the current economic model depends almost entirely on three fragile and **correlated** sources:

* Gas fees (low volume)
* Staking (partly inflationary rewards)
* Market speculation (cyclical and unpredictable)

These three rise and fall **together** — when the market drops, they all drop at the same time.

## The core thesis

Terra Classic becomes **complete infrastructure for the multichain builder**: a set of ready-to-use tools and modules — where **each module also generates revenue for the network**.

Instead of the builder assembling everything alone (data layer, bridges, execution on each chain, treasury custody), they receive from Terra Classic, integrated and ready:

* **Data Availability** for their rollup (Evolve module on the L1)
* **Cross-chain execution** — trigger contracts on ETH, SOL, BSC
* **Cross-chain treasury without multisig** (Interchain Accounts)
* **Interoperability** (Hyperlane)
* **Collateralized stablecoin** as the means of payment for the infrastructure

> **We give the builder complete infrastructure. They build on top of it — and every tool they use generates revenue for Terra Classic.**

Each module is, at the same time, **a tool for the builder and a recurring revenue source for the network**. It is this combination — complete infrastructure + usage-based revenue — that sustains TC without depending on inflation, burning, or speculation. And it is also what makes it hard to copy: the strength is not in any single piece, but in the **kit working together, in the same place**.

| Objective | Do NOT depend on | Build |
|---|---|---|
| Sustainability | Inflation | Revenue from infrastructure services |
| Security | Supply burning | Productive cross-chain treasury |
| Growth | Speculation | Real builder adoption |

---

# THE PROBLEM

Today, the network's economic engine is a closed loop:

```text
Users → Transactions → Gas Fees → Validators
```

Growth is **directly coupled** to the volume of the blockchain itself — today low and tied to the price of LUNC. There is a natural ceiling that rises and falls with the market, not with the effort of building.

**The problem is structural, not technical:** the network only earns when it is *used directly*. We need revenue that grows even when native volume is flat — capturing value from what happens **on other networks too**.

---

# THE NEW VISION

Terra Classic should **sell infrastructure** to builders, not just execute its own transactions.

```text
External Builders and Applications
      │
      ▼
Terra Classic Infrastructure  (interop · cross-chain execution · treasury · DA · settlement)
      │
      ▼
Revenue in real assets
      │
      ▼
Decentralized treasury (cross-chain, productive)
      │
      ▼
Staking with real revenue sharing
      │
      ▼
Greater economic security for the network
```

---

# STRATEGIC PILLARS

| # | Pillar | What it sells | Maturity |
|---|---|---|---|
| 1 | **Hyperlane / Interoperability** | Cross-chain bridges and messages | ✅ Already in production on TC |
| 2 | **Interchain Accounts (Cross-chain Execution + Treasury)** | Remote execution and custody without multisig for any project (CW20, modular/sovereign, DAOs) — fee per transaction to the treasury | 🟡 Primitive exists (Hyperlane ICA) → needs hardening |
| 3 | **Data Availability on the L1 (via Evolve)** | Blob storage for rollups (revenue per blob) | 🔴 To be built — TC does not yet have a DA module |
| 4 | **Decentralized Treasury** | Productive multichain reserves | 🟡 Depends on Pillar 2 |
| 5 | **Main Stablecoin** | Fully collateralized stablecoin | 🟡 Feasible, sensitive to regulation and reputation |
| 6 | **Global Stablecoin System** | Multi-currency basket, segregated backing | 🔴 Very long term, depends on Pillar 5 |

> **Sequencing principle:** the pillars are built **in order of maturity and dependency**, validating real revenue at each stage (see KPIs) before funding the next. Trying everything at once dilutes resources and kills the project.

---

# OVERALL ARCHITECTURE

```text
                           TERRA CLASSIC
                                  │
      ┌───────────────────────────┼───────────────────────────┐
      │                           │                           │
      ▼                           ▼                           ▼
  HYPERLANE              INTERCHAIN ACCOUNTS              STABLECOINS
 (interop base)        (execution + treasury)         (fuel of the infra)
      │                           │                           │
      └──────────────┬────────────┴────────────┬──────────────┘
                     ▼                          ▼
        DATA AVAILABILITY (L1 via Evolve)     TREASURY
        (rollups post blobs → fees)        (productive ETH/SOL/BTC)
                     │                          │
                     └────────────┬─────────────┘
                                  ▼
                       RECURRING REVENUE
                                  │
                                  ▼
                    STAKING WITH REAL REVENUE SHARING
```

---

# PHASED ROADMAP

Phases are **sequential and conditional**: each one only receives full funding after the previous one proves measurable traction (see KPIs).

---

## PHASE 1 — HYPERLANE (Foundation) ✅

**Objective:** Terra Classic as a genuinely interoperable network.

**Target integrations:** Ethereum · BNB Chain · Solana · Cosmos (IBC) · Injective

**Real status:** TC already has a Hyperlane deployment on mainnet. It is the proof of concept for revenue before expanding.

**Revenue:** cross-chain message/transfer fees + IGP (Interchain Gas Payment).

---

## PHASE 2 — INTERCHAIN ACCOUNTS: CROSS-CHAIN EXECUTION AND TREASURY WITHOUT MULTISIG ⭐

> **This is the centerpiece of the thesis and the project's biggest differentiator.**

### The real problem this solves

Today, for Terra Classic to have liquidity on a DEX like Uniswap, or reserves in ETH/SOL, it needs a **multisig account on the destination chain** (like a Gnosis Safe), with human signers. This is terrible:

* **Governance vs. custody collide** — governance approves on-chain, but execution depends on N humans signing. It becomes a political fight and almost never happens.
* **Custody risk** — keys can be lost, compromised, or signers disappear.
* **Practical result:** TC is **prevented from diversifying its treasury** into productive, growing assets (ETH, SOL) that would strengthen the network. It is stuck because it cannot hold assets outside Cosmos without fragile human custody.

### The solution

Each TC wallet/governance has a **deterministic account-contract on other blockchains** (ETH, SOL, BSC), controlled by Hyperlane messages. Instead of humans signing a multisig:

```text
TC Governance / Wallet  (on-chain decision)
        │
        ▼
Hyperlane message  (validated by the ISM)
        │
        ▼
Remote account-contract (ETH / SOL / BSC)
        │
   ┌────┼─────────────┬──────────────┐
   ▼    ▼             ▼              ▼
 Deposit   Swap on DEX    Add/Remove    Buy
           (Uniswap)      liquidity     tokens
        │
        ▼
Verified result, asset under TC's on-chain control
```

This **already exists as a primitive in Hyperlane** (`InterchainAccountRouter` / ICA) — it is not R&D from scratch, it is integration + hardening. The same model gives the protocol:

* **Cross-chain contract execution** — sold per use (fee per intent/action).
* **Cross-chain treasury without multisig** — TC becomes able to hold and manage productive ETH/SOL/BTC, controlled by on-chain governance.

### Who it serves: any project, not just governance

The cross-chain account-contract is **not exclusive to the network treasury** — it is an open primitive, available to **any project built on Terra Classic**:

* **CW20 and CosmWasm contracts** — a CW20 token or dApp on TC can trigger actions on ETH/SOL/BSC (move liquidity, swap, buy/sell) directly from its own contract, without building its own bridge infrastructure or multisig.
* **Modular projects / sovereign chains** — appchains and sovereign rollups that use TC gain the same cross-chain execution and custody power as a native service, instead of rebuilding everything themselves.
* **Third-party DAOs and treasuries** — any DAO on TC can manage assets on other networks via on-chain governance, without human signers.

In other words: the same tool that unlocks the network treasury becomes a **sellable product for the entire ecosystem**.

### The revenue model: every transaction feeds the community treasury

**Every cross-chain execution — from any project, CW20 or modular — charges a fee.** And that fee goes **directly to Terra Classic's community treasury**.

```text
Any project (CW20 · modular · DAO · governance)
        │
        ▼  triggers cross-chain execution
Remote account-contract (ETH / SOL / BSC)  ──► fee per transaction
        │                                         │
        ▼                                         ▼
   action executed                      COMMUNITY TREASURY (direct)
```

The more projects use cross-chain execution, the more transactions happen — and **the more the community treasury grows, recurrently and automatically**. It does not depend on TC's native volume: it depends on third-party adoption. This is the sustainable revenue engine.

### Why this is the lock-in

Whoever builds with TC gains cross-chain execution and treasury **without building and operating a multisig on each chain**. If they leave, they lose that access. That switching cost is the moat — not the price list.

### 🚨 The point that decides everything: ISM security

If the remote account is controlled by Hyperlane messages, then **the security of the entire cross-chain treasury = the security of the ISM (Interchain Security Module)** that validates those messages. An attacker who forges a valid message **drains all remote accounts at once**. Bridges/messengers are the #1 target for hacks in crypto — billions have already been lost on this vector.

**Non-negotiable** requirements:

1. **Robust ISM** — multisig ISM with a strong validator set and, ideally, economic security (staking/slashing of signers). Never the default configuration.
2. **Hardened remote contract** — strict authorization (only accepts a message from the TC origin + legitimate sender), replay protection, clear upgrade governance.
3. **Limits and timelocks** — value caps per execution and delays on large operations, to allow time to react to a forged message.
4. **Heavy auditing** — this is custody of funds; a bug = total loss. Auditing is not optional.

### Recommended technical sequence

Start with **EVM (ETH/BSC/Uniswap)**, where remote execution is more mature. **Solana comes later** — executing swaps on Raydium/Orca from a remote account requires CPI and PDAs, much more complex. Prove the model on EVM first, then expand to SVM.

---

## PHASE 3 — DATA AVAILABILITY ON THE L1 (via Evolve)

> **Current state:** Terra Classic does not yet have a rollup or DA capability. This phase **builds** that capability into the L1 itself.

**Objective:** turn the **Terra Classic L1 into the Data Availability layer** — TC stores rollup *blobs* and **charges for that storage**. Every rollup that posts data on TC generates recurring revenue for the network.

**How it works:** today TC is a standard Cosmos SDK chain and **does not store blobs**. The **Evolve** technology is integrated into the L1 to add DA capability (storage and availability of blobs). From there:

```text
Rollup (built on top of TC's DA, e.g., the Evolve framework)
        │
        ▼  posts blob (transaction data)
Terra Classic DATA AVAILABILITY (L1 + Evolve)
        │
        ▼  stores and guarantees availability
Charge per blob  →  Revenue  →  Treasury
```

**Revenue:** fee per blob stored/published ("blob fees" model). The more rollups post on TC, the more the network earns — revenue that **grows with third-party adoption, not with TC's native volume**.

**Honest positioning:** the DA market already has well-funded, established leaders (Celestia, EigenDA, Avail) and is **price-competitive** — pure DA margins are thin and volume-driven. TC **does not win by being "just another cheap DA"** (a race to the bottom). It wins because its DA comes **bundled with the unique package**: whoever posts blobs on TC gets, in the same place, **cross-chain execution + treasury without multisig (Phase 2) + settlement + interop**. DA is the *front door* that brings the rollup; the cross-chain primitives are what lock it in and carry the higher margin.

> ⚠️ **Technical realism:** building reliable DA is not trivial. Serious DA requires data throughput, *data availability sampling* (DAS), light clients, and guarantees that the data is genuinely available. Integrating Evolve into the L1 is a **significant engineering effort**, not a config. It is the roadmap's highest technical-risk pillar — which is why it comes **after** Hyperlane (Phase 1) and Interchain Accounts (Phase 2) are already generating cash.

> ⚠️ **Cheap fees are not the argument.** Low fees attract, but it is a race to the bottom. The lock-in is the **integrated primitives**, not the blob price.

---

## PHASE 4 — DECENTRALIZED TREASURY

**Objective:** accumulate productive assets that sustain the network regardless of the price of LUNC.

**Enabled by Phase 2:** with Interchain Accounts, TC can finally hold and manage reserves in **ETH, SOL, BTC, and stablecoins** under on-chain governance control — without a human multisig.

**Revenue sources:** Hyperlane · Cross-chain execution · DA (blob fees) · Stablecoins · services.

**Treasury governance is critical:** custody via audited contracts, transparent rules, limits/timelocks, public accountability. A large treasury without this is a target and a capture risk.

---

## NEW STAKING MODEL

**Today:** delegation → rewards (partly inflationary).

**Future:** delegation → **sharing in the real revenue** of the services.

```text
User → Delegates LUNC → Shares in the Revenue
                          ├─ Hyperlane
                          ├─ Cross-chain execution
                          ├─ Data Availability (blob fees)
                          ├─ Stablecoins
                          └─ Infrastructure
```

Staking stops being an inflationary subsidy and starts representing **economic participation in a business that generates cash**. It is, on its own, one of the strongest concepts in the document.

> ⚖️ **Regulatory warning:** distributing service revenue to stakers may characterize LUNC as a *security* in several jurisdictions. The mechanism design needs legal counsel before implementation.

---

## REVENUE DISTRIBUTION (illustrative example)

```text
Hypothetical annual revenue = US$ 100M

├─ 40% Treasury        (reinvestment and productive reserves)
├─ 30% Staking         (delegator revenue sharing)
├─ 20% Development     (funding those who build)
└─ 10% Reserve         (contingency / insurance fund)
```

*Percentages are a starting point for governance, not final numbers.*

---

## PHASE 5 — MAIN STABLECOIN (fuel of the infrastructure)

**Objective:** create a **fully collateralized** stablecoin — the exact opposite of the UST mistake — to be the **means of payment for the infrastructure itself** (execution, rollups, settlement, lending).

**Non-negotiable characteristics:**

* ✅ Real and auditable collateral (no algorithm, no reflexivity)
* ✅ Redeemable 1:1
* ✅ Multichain
* ✅ Public, continuous proof of reserves (PoR)

```text
Real collateral (USDC / T-bills) → Terra Stablecoin → [Execution · Rollups · Lending · Settlement] → Fees → Treasury
```

The business logic: builders and users pay for the infrastructure in the Terra stablecoin → the fees feed the treasury → the profit circulates to the whole network via staking.

> 🚨 **The most politically delicate phase.** TC carries the scar of UST. The new stablecoin **must** be visibly and technically different (full collateralization, radical transparency) — or the market rejects it by association. Done right, it is also the biggest opportunity for reputation rehabilitation.

---

## PHASE 6 — GLOBAL STABLECOIN SYSTEM (segregated backing)

**Only after** the main stablecoin is validated, audited, and has real adoption beyond TC itself.

Expansion into a multi-currency basket (target list): USD · EUR · BRL · GBP · AUD · CAD · JPY · CHF · KRW · CNY · SGD · MXN · INR · ZAR · SEK · NOK · DKK · TRY · ARS · CLP · COP · NZD.

The idea: the 22 stablecoins use the main Terra stablecoin as a rail/fuel to pay for the infrastructure, generating profit for the network.

### 🚨 Contagion risk — requires segregated backing

Stacking stablecoins (the 22 backed *by* the Terra stablecoin) recreates the **category of error that killed UST**: second-degree collateral and a single point of failure. If the base wobbles, **all 22 wobble at the same time**.

**Non-negotiable rules for this phase:**

* Each of the 22 must have its **own traceable backing** (even if operationally routed through the main Terra stablecoin) — not pure stacked collateral.
* **Proof of reserves per currency**, never aggregated.
* **Zero algorithmic/reflexive component** at any layer.
* Treat it as a **very-long-term north star**, not a roadmap deliverable: each fiat currency requires a banking partner, regulated custody, and a license per jurisdiction. Each currency is a regulatory project in itself.

```text
                   USD Stablecoin (anchor, real backing)
      ┌─────────────┬─────┼─────┬─────────────┐
      ▼             ▼     ▼     ▼             ▼
    EUR           BRL   GBP   JPY           AUD
 (own traceable backing + PoR per currency)
      └─────────────┴─────┼─────┴─────────────┘
                          ▼
                   Terra Classic (settlement layer)
```

---

# ADDRESSABLE MARKET

Terra Classic can operate in: interoperability, cross-chain execution, treasury without multisig, infrastructure for builders, stablecoins, settlement.

**Defensible differentiator:** very few networks offer *DA + mature interop + cross-chain execution + treasury without human custody + collateralized stablecoins*, integrated. TC does not beat Celestia on *cheap* DA — it wins because its DA comes **bundled** with the cross-chain primitives the rollup also needs. The thesis wins by choosing the **niche where the combination matters**, not by competing head-on in each isolated category.

---

# FINANCIAL PROJECTIONS

> ⚠️ **Purely illustrative scenarios**, based on premises to be validated. They are not forecasts. The "Premise" column shows what would need to be true.

| Scenario | Hyperlane | Cross-chain execution | DA (blob fees) | Stablecoins | **Total/year** | Core premise |
|---|---|---|---|---|---|---|
| **Conservative** | $2M | $3M | $5M | — | **$10M** | Hyperlane with modest traction, execution in beta, few rollups posting |
| **Moderate** | $10M | $20M | $20M | $10M | **$60M** | Execution adopted + several rollups on DA + 1 live stablecoin |
| **Aggressive** | $25M | $50M | $50M | $25M | **$150M** | TC becomes a reference DA + infra in multichain |

**Honest reading:** the conservative scenario ($10M/year) would already be a **historic achievement** for TC in its current state. Moderate and aggressive depend on winning markets where TC is currently a latecomer. **Plan for the conservative; treat the rest as upside.**

---

# 2030 GOAL

Transform Terra Classic into:

* A **Data Availability layer** that earns revenue per rollup blob (via Evolve on the L1)
* A layer of **cross-chain execution and treasury without multisig**
* A hub of **collateralized** stablecoins (rehabilitating the reputation)
* An infrastructure provider with a **productive treasury** (ETH/SOL/BTC)

**Final goal:** a treasury capable of sustaining network development and security **regardless of the market cycle**, replacing dependence on inflation and speculation with revenue from infrastructure services.

---

# ⚠️ RISKS AND CRITICAL DEPENDENCIES

1. **Cross-chain security (ISM) = risk #1** — the entire remote treasury depends on the security of Hyperlane messages. Requires a strong ISM, limits, timelocks, and auditing. Bridges are the industry's biggest hack target.
2. **Execution vs. resources** — TC does not have Ethereum/Celestia's R&D budget. Six simultaneous pillars guarantee failure. **Brutal focus is mandatory.**
3. **Building DA from scratch is high technical risk** — TC has no DA today; integrating Evolve into the L1 (blobs, DAS, light clients, availability guarantees) is heavy engineering. And the DA market is mature and cheap (Celestia/EigenDA). It only wins as an integrated niche package, never as generic DA.
4. **Cheap fees as a hook** — race to the bottom; it must be a consequence, not an argument.
5. **Stablecoin contagion** — the 22 cannot be pure second-degree collateral; they require segregated backing and PoR per currency.
6. **UST reputation** — any new stablecoin carries the historical weight; radical transparency is mandatory.
7. **Regulatory risk** — stablecoins (custody/licenses) and staking-with-revenue (LUNC as a security) need legal structuring before code.
8. **Treasury governance** — without custody in audited contracts, limits, and accountability, it becomes a capture risk.
9. **Dependence on dev talent** — the whole thesis depends on attracting and retaining engineers. Without it, it's just a PDF.

---

# VALIDATION KPIs (gates between phases)

Each phase only advances with a proven metric:

| Phase | Exit metric to unlock the next |
|---|---|
| 1 — Hyperlane | Sustained monthly cross-chain volume + IGP revenue > operating cost |
| 2 — Interchain Accounts | Executions paid by real users + 1st cross-chain reserve (ETH) managed on-chain via ICA, audited |
| 3 — Data Availability | DA on the L1 (via Evolve) in production + ≥ 1 rollup posting blobs and paying blob fees |
| 4 — Treasury | Publicly audited reserves, contract custody, limits/timelocks, quarterly report |
| 5 — Stablecoin | Continuous public PoR + adoption beyond TC itself |
| 6 — Basket | Main stablecoin profitable and stable for ≥ 12 months, before any expansion |

---

# CONCLUSION

The strategic direction is **correct and, refined, stronger than it first appeared**: replacing dependence on inflation/speculation with **infrastructure revenue** is what separates sustainable networks from zombie networks.

The two strongest concepts are:

1. **Interchain Accounts** — cross-chain execution and treasury without a human multisig. It solves a real, concrete pain for TC (it cannot today hold liquidity/reserves in ETH/SOL without fragile custody), uses a primitive that **already exists** in Hyperlane, and creates a lock-in that is hard to copy.
2. **Staking as real revenue sharing** — turns an inflationary reward into a dividend from a business.

The risk is not in the vision — it is in the **temptation to do everything at once** and in **underestimating cross-chain security**. Success depends on:

1. **Sequencing** (Hyperlane → Interchain Accounts → DA via Evolve → stablecoins)
2. **Focusing on the niche** where the integrated package is defensible
3. **Treating projections as hypotheses**, planning for the conservative case
4. **Taking ISM security and regulatory risk seriously from day 1**

Done with focus and honesty, it is one of the few *realistic* rebirth theses for Terra Classic.

---

*Vision document (v2.2) — subject to governance debate and technical validation. This does not constitute financial advice nor a promise of return.*

# TERRA CLASSIC 2030

## From a Survivor Chain to Complete Infrastructure for the Multichain Builder

**Version 2.2 — Presentation edition (without financial projections)** · Strategic Vision Document

> ⚠️ **Disclaimer**: This is a *vision and strategic direction* document, not a guaranteed execution plan. **It deliberately contains no revenue numbers or financial projections** — its purpose is to show the *potential and the direction*, not to promise figures. Every economic change described depends on on-chain governance, development resources, and market adoption. Nothing here is financial advice.

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
* **Interoperability** (Hyperlane) — the on-ramp that attracts builders (foundation, not a revenue line)

> **We give the builder complete infrastructure. They build on top of it — and every revenue-generating tool they use feeds Terra Classic's treasury.**

Each revenue module (cross-chain execution, DA) is, at the same time, **a tool for the builder and a recurring revenue source for the network** — while Hyperlane is the foundation that brings builders in. It is this combination — complete infrastructure + usage-based revenue — that sustains TC without depending on inflation, burning, or speculation. And it is also what makes it hard to copy: the strength is not in any single piece, but in the **kit working together, in the same place**.

| Objective | Do NOT depend on | Build |
|---|---|---|
| Sustainability | Inflation | Revenue from infrastructure services |
| Security | Supply burning | Productive cross-chain treasury |
| Growth | Speculation | Real builder adoption |

---

# THE TECHNICAL FOUNDATION IS ALREADY MODERN — COSMOS SDK v0.53

A vision is only credible if the chain underneath it is current. Terra Classic just delivered a **major core upgrade: from Cosmos SDK v0.47.x (running since 2023) to v0.53.x** — jumping over the entire v0.50/v0.52 line in a single, non-breaking upgrade. This is not cosmetic: it puts TC on the **same modern tier as the most advanced chains in the Cosmos ecosystem**, and it is exactly the base the rest of this plan needs.

### What the v0.53 upgrade unlocks

* **Modern IBC (ibc-go v10 / IBC v2)** — the current interchain standard, and the door to **IBC Eureka**, which connects Cosmos to **Ethereum** with ZK light-client security. This is directly complementary to the cross-chain thesis (Phase 1–2): native, standards-based interoperability instead of bespoke bridges.
* **`x/epochs`** — cron-like, time/block-based hooks for **automated on-chain actions** (reward distribution, oracle updates, periodic rebalancing). A natural primitive for the staking-as-revenue-sharing and treasury automation in this plan.
* **`x/protocolpool`** — the community pool **decoupled from `x/distribution`**, giving far more flexible, transparent funding: governance grants, developer funding, and **protocol-owned liquidity**. This is the on-chain plumbing for the productive-treasury model (Phase 4).
* **Unordered transactions** — "fire-and-forget" txs using a timeout timestamp instead of strict sequence numbers, reducing failed transactions in high-volume flows (DeFi swaps, bots) — useful for the cross-chain execution engine (Phase 2).
* **Module upgrades** — improvements across `x/mint`, `x/gov`, `x/auth`, `x/bank`, and `x/staking`, plus modern developer APIs (Collections / KVStoreService) that make building the new modules (cross-chain execution, DA) faster and safer.

### This puts Terra Classic ahead of most chains

Running v0.53 is still rare — only a short list of top chains have made the jump. Terra Classic is now in that group:

| Chain | On Cosmos SDK v0.53 |
|---|---|
| **Terra Classic** | ✅ (core v4.0.0 / v14_1 upgrade, 2026) |
| Cosmos Hub | ✅ |
| Babylon | ✅ |
| MANTRA | ✅ |
| Warden | ✅ |
| Crypto.com / Cronos POS | ✅ |

> 🛠️ **Why it matters for this plan:** every pillar that follows (cross-chain execution, treasury without multisig, DA, staking-as-revenue) is built **on top of a current, well-supported SDK with modern IBC** — not on a legacy stack. The upgrade is itself **proof the team can ship hard core changes**, and it removes the "old, abandoned chain" objection before the first revenue module is even built.
>
> *Chain list and feature set verified against public Cosmos Stack / Cosmos SDK sources as of mid-2026; SDK/IBC adoption moves fast — confirm before citing externally.*

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
| 1 | **Hyperlane / Interoperability** | Foundation / on-ramp — attracts builders and liquidity. **Does not generate network revenue** (bridge fees go to relayer operators and UI hosts) | ✅ Already in production on TC |
| 2 | **Interchain Accounts (Cross-chain Execution + Treasury)** | Remote execution and custody without multisig for any project (CW20, modular/sovereign, DAOs) — fee per transaction to the treasury | 🟡 Primitive exists (Hyperlane ICA) → needs hardening |
| 3 | **Data Availability on the L1 (via Evolve)** | Blob storage for rollups (revenue **by storage: size × retention**, not per transaction) | 🔴 To be built — TC does not yet have a DA module |
| 4 | **Decentralized Treasury** | Productive multichain reserves | 🟡 Depends on Pillar 2 |

> **Sequencing principle:** the pillars are built **in order of maturity and dependency**, validating real revenue at each stage (see KPIs) before funding the next. Trying everything at once dilutes resources and kills the project.

---

# OVERALL ARCHITECTURE

```text
                           TERRA CLASSIC
                                  │
              ┌───────────────────┴───────────────────┐
              │                                       │
              ▼                                       ▼
        HYPERLANE                          INTERCHAIN ACCOUNTS
       (interop base)                      (execution + treasury)
              │                                       │
              └──────────────┬────────────────────────┘
                             ▼
        ┌────────────────────┴────────────────────┐
        ▼                                          ▼
DATA AVAILABILITY (L1 via Evolve)              TREASURY
(rollups post blobs → fees)               (productive ETH/SOL/BTC)
        │                                          │
        └────────────────────┬─────────────────────┘
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

**Target integrations:** Ethereum · BNB Chain · Solana · Cosmos (IBC)

**Real status:** TC already has a Hyperlane deployment on mainnet — proof that the team can ship.

> ⚠️ **Important — Hyperlane does NOT generate revenue for the network.** Cross-chain message fees go to the **relayer operators**, and the UI fees go to **whoever hosts the interface**. Hyperlane is a **bridge tool**: its role is to attract builders, liquidity, and users into Terra Classic. It is the **on-ramp / foundation that makes every other phase possible — not a revenue source**. The actual network revenue starts in Phase 2.

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

* **Cross-chain contract execution** — priced as **gas + a fixed fee**. The gas is pass-through to the chains involved (it pays validators, not the network); the **fixed fee is the network's revenue**.
* **Cross-chain treasury operations** — a **fee per transaction** (deposit, swap, move liquidity, rebalance). This is the same primitive that also lets TC hold and manage productive ETH/SOL/BTC under on-chain governance, without a human multisig.

### Who it serves: any project — including projects NOT on Terra Classic

The cross-chain account-contract is **not exclusive to the network treasury, and not even exclusive to projects built on Terra Classic** — it is an open primitive:

* **CW20 and CosmWasm contracts** — a CW20 token or dApp on TC can trigger actions on ETH/SOL/BSC (move liquidity, swap, buy/sell) directly from its own contract, without building its own bridge infrastructure or multisig.
* **Modular projects / sovereign chains** — appchains and sovereign rollups that use TC gain the same cross-chain execution and custody power as a native service, instead of rebuilding everything themselves.
* **Third-party DAOs and treasuries** — any DAO can manage assets on other networks via on-chain governance, without human signers.
* **External projects on other chains** — a DAO or treasury living on Ethereum, Solana, or anywhere else can use Terra Classic purely as a **cross-chain execution hub**: they don't build their app on TC, they use TC as the *control plane* to operate across many chains from one place — for example, executing a Uniswap swap on Ethereum without juggling a multisig there.

> **This is the biggest market expansion in the plan.** It moves the target from "projects built on TC" (a small market) to **"any treasury or DAO anywhere that is tired of running a separate multisig per chain"** (a huge market) — and every one of them pays a fee per execution to the community treasury, directly feeding the revenue engine.

### Non-custodial by design: each user owns their account

Critically, **Terra Classic does not custody anyone's funds.** Each user **instantiates their own contract, exclusive to them** — like Uniswap or Safe, TC is *infrastructure*, not a custodian. That account can sign and execute calls on other contracts (a Uniswap swap, a lending action), but the assets and control belong to the user, never to the network.

Two consequences:

* **Lower regulatory and custody risk** — the protocol is not a honeypot holding billions; it provides the rails, and users hold their own assets.
* **The right pitch is "programmable cross-chain smart account," not "no multisig."** The value is not removing secure control — it is giving the user **one programmable account that reaches many chains** (with policies, automation, conditions), instead of juggling one multisig per chain. The user still controls it; they just control it better, from one place.

### The revenue model: every transaction feeds the community treasury

**Every cross-chain execution — from any project, CW20 or modular — charges a fee** (the fixed fee on contract execution, or the per-transaction fee on treasury operations). And that fee goes **directly to Terra Classic's community treasury**.

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

> 💎 **LUNC is the currency of the network.** Gas on the Terra Classic L1 and the network's fixed fee on every cross-chain execution are paid **in LUNC** — the destination-chain gas (ETH/SOL/BSC) is only passed through to that chain. So every service in the plan settles its network fees in LUNC, tying real usage back to demand for the token.

### A high-volume use case: trading bots and automated strategies

One of the most natural — and highest-volume — users of cross-chain execution is **automated trading**: arbitrage, market-making, DCA, grid, and liquidation **bots** that need to act on several chains at once. Instead of each team running its own multisig and infrastructure per chain, they can route their strategy through Terra Classic's cross-chain execution as a single control plane.

> 🤖 **Why this matters for revenue:** bots are, by nature, **high-frequency** — projects that operate them generate **many transactions**, and **each transaction pays a fee to the community treasury**. More bot activity → more volume → more recurring fees, without depending on the price of LUNC.

> ⚠️ **Fee model is still under study — no value is defined yet.** Whether the network fee on a bot/cross-chain transaction is a **fixed amount** or a **percentage per transaction**, and what that amount or percentage would be, is **not yet decided** — it is subject to governance and further study.

### Why this is the lock-in

Whoever builds with TC gains cross-chain execution and treasury **without building and operating a multisig on each chain**. If they leave, they lose that access. That switching cost is the moat — not the price list.

### 🚨 The point that decides everything: security (even when non-custodial)

Non-custodial **relocates** the risk — it does not eliminate it. Two systemic risks remain:

**1. Shared template code.** Every user's account is "theirs," but all are instances of the **same template/factory contract**. A bug in that shared code drains *every* account at once — exactly what happened in the 2017 Parity multisig freeze (~$280M across all instances). Auditing the template is **existential**, not optional.

**2. The authorization model (the decisive design choice).** What authorizes a remote account to execute? If it executes *any* ISM-validated message, then an attacker who forges a valid message (by compromising the ISM) can make the user's own account sign the attacker's transaction — draining it **without the user's key**. Bridges/messengers are the #1 hack target in crypto.

| Authorization model | Security |
|---|---|
| Executes any ISM-validated message | 🔴 ISM compromise = every account drainable |
| Requires the **user's own signature** carried in the message (ISM only transports) | 🟢 ISM compromise alone is not enough — the user's key is also required |

**Anchor authorization to the user's key**, so the non-custodial promise is real.

**Non-negotiable requirements:**

1. **Robust ISM** — multisig ISM with a strong validator set and, ideally, economic security (staking/slashing of signers). Never the default configuration. It is the shared trust base for everyone.
2. **User-key-anchored authorization** — the remote account executes only with the user's own signature, not on message validity alone; plus replay protection and clear upgrade governance.
3. **Audited template** — a bug in the shared contract is a collective loss. Audit is existential.
4. **Limits and timelocks** — value caps per execution and delays on large operations, so even a forged message cannot drain everything instantly.

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

**Revenue:** DA is charged **by storage, not per transaction** — a fee based on the **size of the data (bytes) and the retention period** of each blob ("blob fees" model). The more data rollups post on TC and the longer it is kept available, the more the network earns. This revenue **grows with third-party adoption, not with TC's native volume** — but note it is inherently low-margin per blob, and meaningful only once many high-throughput rollups post data.

**Honest positioning:** the DA market already has well-funded, established leaders (Celestia, EigenDA, Avail) and is **price-competitive** — pure DA margins are thin and volume-driven. TC **does not win by being "just another cheap DA"** (a race to the bottom). It wins because its DA comes **bundled with the unique package**: whoever posts blobs on TC gets, in the same place, **cross-chain execution + treasury without multisig (Phase 2) + settlement + interop**. DA is the *front door* that brings the rollup; the cross-chain primitives are what lock it in and carry the higher margin.

> ⚠️ **Technical realism:** building reliable DA is not trivial. Serious DA requires data throughput, *data availability sampling* (DAS), light clients, and guarantees that the data is genuinely available. Integrating Evolve into the L1 is a **significant engineering effort**, not a config. It is the roadmap's highest technical-risk pillar — which is why it comes **after** Hyperlane (Phase 1) and Interchain Accounts (Phase 2) are already generating cash.

> ⚠️ **Cheap fees are not the argument.** Low fees attract, but it is a race to the bottom. The lock-in is the **integrated primitives**, not the blob price.

---

## PHASE 4 — DECENTRALIZED TREASURY

**Objective:** accumulate productive assets that sustain the network regardless of the price of LUNC.

**Enabled by Phase 2:** with Interchain Accounts, TC can finally hold and manage reserves in **ETH, SOL, BTC, and third-party stablecoins (e.g., USDC, USDT)** under on-chain governance control — without a human multisig.

**Revenue sources:** Cross-chain execution · DA (blob fees) · services. *(Hyperlane is the on-ramp, not a revenue line.)*

**Treasury governance is critical:** custody via audited contracts, transparent rules, limits/timelocks, public accountability. A large treasury without this is a target and a capture risk.

> 🔗 **How the treasury sustainably funds staking** (the endowment/flywheel model — spending only the yield, never the principal, to replace inflation-funded staking), see the companion document: `sustainable-treasury-and-staking.md`.

---

## NEW STAKING MODEL

**Today:** delegation → rewards (partly inflationary).

**Future:** delegation → **sharing in the real revenue** of the services.

```text
User → Delegates LUNC → Shares in the Revenue
                          ├─ Cross-chain execution (fees)
                          ├─ Data Availability (blob fees)
                          └─ Infrastructure services
```

Staking stops being an inflationary subsidy and starts representing **economic participation in a business that generates cash**. It is, on its own, one of the strongest concepts in the document.

> ⚖️ **Regulatory warning:** distributing service revenue to stakers may characterize LUNC as a *security* in several jurisdictions. The mechanism design needs legal counsel before implementation.

> 🔗 **The funding mechanism behind this model** — how staking transitions from inflation to real service revenue + endowment yield, and why payouts must be capped at (revenue + yield) to avoid an unsustainable-yield collapse — is detailed in `sustainable-treasury-and-staking.md`.

---

## REVENUE DISTRIBUTION (how revenue would be split)

For **every 100 units of revenue** the network earns, an illustrative split could be:

```text
Of every 100 units of revenue:

├─ 40% Treasury        (reinvestment and productive reserves)
├─ 30% Staking         (delegator revenue sharing)
├─ 20% Development     (funding those who build)
└─ 10% Reserve         (contingency / insurance fund)
```

*Proportions only — a starting point for governance, not final numbers, and not a revenue forecast.*

---

# ADDRESSABLE MARKET

Terra Classic can operate in: interoperability, cross-chain execution, treasury without multisig, infrastructure for builders, settlement.

**Defensible differentiator:** very few networks offer *DA + mature interop + cross-chain execution + treasury without human custody*, integrated. TC does not beat Celestia on *cheap* DA — it wins because its DA comes **bundled** with the cross-chain primitives the rollup also needs. The thesis wins by choosing the **niche where the combination matters**, not by competing head-on in each isolated category.

---

# 2030 GOAL

Transform Terra Classic into:

* A **Data Availability layer** that earns revenue per rollup blob (via Evolve on the L1)
* A layer of **cross-chain execution and treasury without multisig**
* An infrastructure provider with a **productive treasury** (ETH/SOL/BTC)

**Final goal:** a treasury capable of sustaining network development and security **regardless of the market cycle**, replacing dependence on inflation and speculation with revenue from infrastructure services.

---

# ⚠️ RISKS AND CRITICAL DEPENDENCIES

1. **Cross-chain security (ISM) = risk #1** — the entire remote treasury depends on the security of Hyperlane messages. Requires a strong ISM, limits, timelocks, and auditing. Bridges are the industry's biggest hack target.
2. **Execution vs. resources** — TC does not have Ethereum/Celestia's R&D budget. Too many simultaneous pillars guarantee failure. **Brutal focus is mandatory.**
3. **Building DA from scratch is high technical risk** — TC has no DA today; integrating Evolve into the L1 (blobs, DAS, light clients, availability guarantees) is heavy engineering. And the DA market is mature and cheap (Celestia/EigenDA). It only wins as an integrated niche package, never as generic DA.
4. **Cheap fees as a hook** — race to the bottom; it must be a consequence, not an argument.
5. **Regulatory risk** — staking-with-revenue (LUNC as a security) needs legal structuring before code.
6. **Treasury governance** — without custody in audited contracts, limits, and accountability, it becomes a capture risk.
7. **Dependence on dev talent** — the whole thesis depends on attracting and retaining engineers. Without it, it's just a PDF.

---

# VALIDATION KPIs (gates between phases)

Each phase only advances with a proven metric:

| Phase | Exit metric to unlock the next |
|---|---|
| 1 — Hyperlane | Sustained monthly cross-chain volume + builders/liquidity arriving (adoption metric — Hyperlane is the on-ramp, not revenue) |
| 2 — Interchain Accounts | Executions paid by real users + 1st cross-chain reserve (ETH) managed on-chain via ICA, audited |
| 3 — Data Availability | DA on the L1 (via Evolve) in production + ≥ 1 rollup posting blobs and paying blob fees |
| 4 — Treasury | Publicly audited reserves, contract custody, limits/timelocks, quarterly report |

---

# CONCLUSION

The strategic direction is **correct and, refined, stronger than it first appeared**: replacing dependence on inflation/speculation with **infrastructure revenue** is what separates sustainable networks from zombie networks.

The two strongest concepts are:

1. **Interchain Accounts** — cross-chain execution and treasury without a human multisig. It solves a real, concrete pain for TC (it cannot today hold liquidity/reserves in ETH/SOL without fragile custody), uses a primitive that **already exists** in Hyperlane, and creates a lock-in that is hard to copy.
2. **Staking as real revenue sharing** — turns an inflationary reward into a dividend from a business.

The risk is not in the vision — it is in the **temptation to do everything at once** and in **underestimating cross-chain security**. Success depends on:

1. **Sequencing** (Hyperlane → Interchain Accounts → DA via Evolve → productive treasury)
2. **Focusing on the niche** where the integrated package is defensible
3. **Validating each phase with real, on-chain metrics** before scaling the next
4. **Taking ISM security and regulatory risk seriously from day 1**

Done with focus and honesty, it is one of the few *realistic* rebirth theses for Terra Classic.

---

*Vision document (v2.2 — presentation edition, without financial projections) — subject to governance debate and technical validation. This does not constitute financial advice nor a promise of return. For internal revenue modeling, see the full edition `terra-classic-rebirth.md`.*

---

### Authorship & credits

The **idea, vision, and intellectual property of this document belong to Igor Veras**, who conceived and directs the strategy described here. **Research, drafting, and editing were assisted by Claude (Anthropic, via claude.ai).** AI-assisted research can contain inaccurate or outdated data — figures, technical claims, version numbers, and the list of chains/SDK versions should be independently verified before being acted upon or cited externally.

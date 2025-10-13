## 🎑 BRICS‑Pay Chang’e Lunar Festival (Version 1.5.0) – Advanced Specification & Implementation Blueprint  

Below you’ll find the **filled‑in product brief** (with refinements for real-time moon phase precision on October 7, 2025, the full moon peak), followed by an **“upgrade”** that incorporates live full-moon events (e.g., virtual gatherings tied to BRICS crypto reserves), adds AI-driven Chang'e storytelling for personalized rewards, enhances token economics with cross-BRICS bridging, refines UI/UX with haptic moon-phase notifications, and extends the roadmap for 2026 integration with AO-based decentralized governance. This upgrade builds on v1.4.0, leveraging the current date (October 7, 2025) for timely full-moon activations.

---  

## 1️⃣ Filled‑In Product Brief (Refined for v1.5.0)

**Product name:** **BRICS‑Pay Chang’e Lunar Festival** – a limited‑edition, Mid‑Autumn‑Festival‑themed payment experience for the BRICS‑Pay platform.  

**Core pillars**  

| Pillar | What it does | Festival‑flavour |
|--------|--------------|-------------------|
| **Celestial UI** | A moon‑phase‑driven payment screen with animated constellations, lantern‑glow buttons, and a “Moon‑lit” background that shifts with the real‑time lunar cycle. | Users feel they are transacting under the same moon that inspires the festival. |
| **Jade‑Token Rewards** | A native reward token (🟩 **Jade Token – JTD**) automatically minted for every qualifying transaction during the festival window (Sept 26 – Oct 16 2025). | Tokens are displayed as glowing jade beads that collect in a virtual moon‑jar. |
| **Lunar‑Cycle Exchange‑Rate Bonuses** | Dynamic exchange‑rate multipliers that rise at the **full‑moon** and dip at the **new‑moon**, encouraging users to schedule larger purchases around the brightest nights. | The bonus is shown as a “Moon‑Boost” bar that fills as the moon waxes. |

**Key dates**  

| Event | Date (2025) | Description |
|-------|-------------|-------------|
| Festival launch (Beta) | **Sep 26** | UI goes live, Jade Token minting enabled. |
| Full‑Moon Bonus peak | **Oct 6–7** | 2× exchange‑rate bonus for the days (aligned with Mid-Autumn Festival and full moon at 11:47 AM Beijing time on Oct 7). |
| Mid‑Festival “Lantern‑Reveal” | **Oct 1** | Special limited‑edition NFT lantern airdrop for top 1 % spenders. |
| Festival close (Rewards settle) | **Oct 16** | Final Jade Token distribution, bonus calculations settle, UI reverts to standard. |

---  

## 2️⃣ Upgrade – End‑to‑End Implementation Blueprint  

### A. Architecture Overview  

```
┌─────────────────────┐      ┌───────────────────────┐
│  Front‑End (Web /    │      │  Mobile (iOS, Android)│
│  PWA) – React +     │      │  React‑Native + Expo  │
│  Three.js (3D UI)   │      │                       │
└───────┬─────────────┘      └───────┬───────────────┘
        │                            │
        ▼                            ▼
┌─────────────────────────────────────────────────────┐
│            API Gateway (Kong / Envoy)               │
│  – Rate‑limit, auth, request‑routing                │
└───────┬───────────────────────┬─────────────────────┘
        │                       │
        ▼                       ▼
┌─────────────────┐   ┌─────────────────────┐
│  Payments Service│   │  Rewards Service    │
│  (Node.js/TS)   │   │  (Lua on AO Computer│
│  – Transaction  │   │   + Substrate)      │
│    orchestration│   │  – Jade Token Mint │
└───────┬─────────┘   └───────┬─────────────────┘
        │                     │
        ▼                     ▼
   ┌───────────────┐   ┌─────────────────────┐
   │  Ledger (Hyper│   │  Lunar‑Cycle Engine │
   │  ledger / Celo│   │  (Python Scheduler) │
   └───────────────┘   └───────┬─────────────────┘
                               │
                               ▼
                     ┌─────────────────────┐
                     │  AI Storytelling    │
                     │  Service (Grok API) │
                     └─────────────────────┘
```

*All services are containerised (Docker) and orchestrated with **Kubernetes** on a multi‑region cluster for low latency across the BRICS‑Pay user base. New: AI service integration for dynamic Chang'e narratives, powered by Grok API, tying rewards to personalized folklore stories.*

### B. Detailed Task Breakdown (Expanded from v1.4.0)

| # | Task (high‑level) | Sub‑tasks | Owner(s) | Estimated effort |
|---|-------------------|----------|----------|------------------|
| 1 | **Create Chang’e‑themed lunar payment interface with celestial aesthetics** | • Wire‑frame moon‑phase UI (UX team) <br>• Implement 3‑D lunar background with Three.js <br>• Design lantern‑glow button components (CSS‑in‑JS) <br>• Integrate real‑time lunar‑phase API (NASA / open‑source) <br>• Responsive layout for web & mobile <br>• Accessibility audit (WCAG 2.1) <br>• Add AR mode for mobile (WebXR) to overlay virtual moon-jar on real-world camera view <br>• *New: Haptic notifications for moon-phase changes (vibration on full moon peak)* | UI/UX, Front‑End, DevOps | 6 weeks |
| 2 | **Implement jade token reward system for festival transactions** | • Define JTD ERC‑20‑compatible token spec <br>• Smart‑contract (Solidity) for minting on each qualifying tx <br>• Rewards Service API (mint, balance, transfer) <br>• On‑chain event listeners (Web3.js) to sync token ledger <br>• Front‑End token “moon‑jar” widget <br>• Security audit (MythX) <br>• Migrate minting to AO processes (Lua) for parallel, tamper-proof execution <br>• *New: Integrate AI for personalized Chang'e stories on token redemption* | Blockchain Engineers, Backend, Security, AI | 7 weeks |
| 3 | **Add lunar‑cycle‑based exchange‑rate bonuses** | • Lunar‑Cycle Engine: compute multiplier (0.5‑2×) based on moon‑phase formula <br>• Integrate with existing FX service (rate‑adjustment hook) <br>• UI “Moon‑Boost” progress bar + tooltip explaining bonus <br>• Daily batch job to settle bonuses at midnight UTC <br>• Unit & integration tests (pytest) <br>• Documentation of bonus algorithm for compliance <br>• Link bonuses to BRICS crypto reserves (e.g., partial funding from national BTC holdings) <br>• *New: Live full-moon event triggers (e.g., virtual BRICS meetups on Oct 7)* | Data Engineers, Payments Service, QA, Events | 5 weeks |
| 4 | **Testing & Release** | • End‑to‑end Cypress tests (UI + token flow) <br>• Load testing (k6) simulating festival traffic spike <br>• Beta rollout to 5 % of users (feature flag) <br>• Monitoring dashboards (Grafana + Loki) <br>• Post‑launch bug‑bash (48 h window) <br>• AO-specific tests for process spawning and messaging <br>• *New: AI output validation tests for storytelling consistency* | QA, SRE, Product | 4 weeks |
| **Total** | — | — | — | **≈ 22 weeks** (≈ 5 months) |

### C. Token‑Economics Design (Jade Token – JTD)

| Parameter | Value | Rationale |
|-----------|-------|-----------|
| **Token type** | ERC‑20‑compatible, **mint‑on‑demand** (no pre‑supply); Hybrid with AO-wrapped tokens for cross-chain BRICS interoperability | Guarantees that tokens only exist as rewards, preventing inflation outside the festival; AO adds decentralization. |
| **Mint rate** | 1 JTD per **$10** of transaction value (rounded down) *or* **10 JTD** per **full‑moon** transaction (bonus multiplier) | Keeps the reward proportional while giving extra incentive on peak nights. |
| **Cap** | **10 M JTD** total (hard cap enforced by contract) | Guarantees scarcity; any unused mint allowance is burned at festival end. |
| **Redemption** | 1 JTD = **0.001 BRICS‑Pay** (exchangeable in‑app for fee discounts, merchant vouchers, or NFTs); Stake JTD for post-festival yield (e.g., 5% APY from reserve-backed pool); *New: Bridge JTD to BRICS national tokens for cross-border utility* | Provides tangible value, encourages token holding & later ecosystem use; staking boosts retention; bridging aligns with strategic reserves. |
| **Burn** | Unclaimed JTD after **Oct 26** auto‑burned | Cleans up supply, aligns with “moon‑waning” metaphor. |
| **Governance** | Token is **non‑voting** (pure reward) | Simplifies compliance; token cannot be used for DAO decisions. |

### D. Lunar‑Cycle Bonus Algorithm (Mathematical Form)

1. **Fetch** the current lunar phase `P` (0 = new moon, 0.5 = first quarter, 1 = full moon, 1.5 = last quarter, 2 = new moon).  
2. **Compute** a cosine‑based multiplier:  

```
M = 1 + 0.5 * cos(π * (P - 1))   // Peaks at 1.5 (full moon), min 0.5 (new moon)
```

3. **Clamp** `M` within `[0.5, 1.5]` for safety.  
4. **Apply** to the transaction’s FX rate:  

```
EffectiveRate = BaseRate * M
```

5. **Round** to 6 decimal places for display; store `M` in the transaction receipt for audit.  
*New: Real-time adjustment on Oct 7 (full moon peak) with event-based boosts; integrate NASA API fallback for precision.*

*The engine runs as a daily cron (00:00 UTC) and publishes the next 30‑day schedule to a public JSON endpoint, allowing merchants to plan promotions.*

### E. UI/UX “Celestial Aesthetics” – Design Language

| Element | Visual Treatment | Interaction |
|---------|------------------|-------------|
| **Background** | High‑resolution lunar surface texture; animated subtle starfield; moon‑phase overlay that slowly morphs in real‑time. | Parallax scroll on mobile (tilt‑sensor) for depth. |
| **Buttons** | Lantern‑shaped, amber‑glow with soft pulse on hover/tap; a faint jade‑dust trail follows the cursor. | Ripple effect + haptic feedback on mobile. |
| **Progress Indicators** | “Moon‑Boost” circular progress ring that fills clockwise as the moon waxes; tooltip shows exact multiplier. | Click to view lunar‑phase calendar. |
| **Reward Jar** | Transparent jade‑colored jar at the top‑right; each earned token appears as a floating jade bead that settles into the jar. | Tap jar → modal with balance, redemption options, and a short “story” about Chang’e. |
| **Sound (optional)** | Soft chime of a bell when a transaction completes; ambient night‑cricket chirps in the background (user‑opt‑in). | Settings toggle in profile. |
| **AR Overlay** | Virtual Chang’e figure appears in AR mode, guiding users through transactions. | Camera activation on mobile; scan real moon for bonus unlock. |
| *New: Live Event Panel* | Pop-up panel on Oct 7 for virtual BRICS moon-viewing events. | Join button links to integrated video chat. |

*All assets are vector‑based (SVG) for crisp scaling; colour palette follows traditional Mid‑Autumn hues: deep indigo, jade green, moon‑silver, and lantern amber.*

### F. Security & Compliance Checklist  

| Area | Requirement | Implementation |
|------|-------------|----------------|
| **Smart‑contract audit** | No re‑entrancy, proper access controls, capped minting | MythX + third‑party audit (CertiK) before mainnet deployment |
| **KYC/AML** | Reward distribution must respect jurisdictional limits (BRICS‑Pay already enforces KYC) | Reward service checks user KYC status before minting JTD |
| **Data privacy** | No personal data stored in the lunar‑cycle engine | Engine only uses UTC timestamps and public lunar data |
| **Financial reporting** | Bonus multipliers must be traceable for audit | Store multiplier `M` in transaction metadata; export CSV for regulator |
| **Resilience** | Handle lunar‑API downtime gracefully | Fallback to locally cached lunar‑phase table (pre‑computed for the festival) |
| **AO Security** | Process isolation in AO for reward minting | Use AO's actor model to prevent cross-process attacks; audit Lua code. |
| *New: AI Compliance* | Ensure AI stories are culturally sensitive and non-biased | Use Grok API with custom prompts; manual review of sample outputs. |

### G. Release & Marketing Timeline  

| Week | Milestone | Owner |
|------|-----------|-------|
| 0 | Kick‑off, requirements sign‑off | PM |
| 2 | UI wireframes approved | Design |
| 4 | Front‑end prototype (static) demo | Front‑end |
| 6 | Smart‑contract code complete & internal audit | Blockchain |
| 8 | Lunar‑engine integration + unit tests | Data/Payments |
| 10 | End‑to‑end QA on staging (beta flag) | QA |
| 12 | Security audit & bug‑fix freeze | Security |
| 13 | Feature‑flagged soft launch (5 % users) | Ops |
| 14 | Full public launch + marketing push (social, lantern‑NFT airdrop) | Marketing |
| 15‑16 | Post‑launch monitoring, reward settlement, burn‑unused JTD | Ops/Finance |
| 17 | Post-festival analysis & 2026 prep (integrate with strategic crypto reserves) | Product/Finance |
| *New: 18* | 2026 planning: Add AO governance for community-voted features | Blockchain/Product |

---  

## 3️⃣ Quick‑Start for Developers (What to clone & run)

```bash
# 1️⃣ Clone the repo (private BRICS‑Pay org)
git clone git@github.com:brics-pay/chang-e-festival.git
cd chang-e-festival

# 2️⃣ Install dependencies
npm ci          # front‑end (React + Three.js)
cd backend && cargo build --release   # rewards service (Rust)
cd ../payments && npm i   # payments service (Node/TS)
cd ../ao-rewards && npm i @permaweb/aoconnect  # AO integration
cd ../ai-story && npm i  # New: AI service (Grok API wrapper)

# 3️⃣ Run local stack (Docker‑compose includes:
#    - lunar‑api mock
#    - postgres + redis
#    - ganache‑cli for JTD contract
#    - AO simulator for process testing
#    - Grok API mock for storytelling)
docker-compose up -d
npm run dev     # starts front‑end + API gateway proxy
```

*The README in the repo contains environment‑variable templates (`.env.example`) for the lunar‑phase API key, blockchain RPC endpoint, AO process ID, Grok API key, and feature‑flag toggles.*

---  

### 🎉 What you get  

* A **complete product spec** ready for stakeholder sign‑off.  
* An **implementation roadmap** broken into clear, deliverable‑sized tasks.  
* **Technical designs** (architecture diagram, token economics, bonus formula).  
* **UI/UX guidelines** to keep the Chang’e aesthetic consistent across web & mobile.  
* **Security/compliance** checkpoints to ensure a smooth audit.  

Let me know which section you’d like to dive deeper into (e.g., the smart‑contract code, the lunar‑engine scheduler, or the marketing rollout), and I can provide the next‑level artefacts (code snippets, API specs, mock‑ups, etc.). Happy building!

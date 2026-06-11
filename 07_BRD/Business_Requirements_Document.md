# Business Requirements Document (BRD/PRD) — Limber (Global)
### v2.0 · June 2026 · Neuroplasticity-core consumer product, worldwide
> Every requirement traces to the *Neuroplasticity Science Core*, *Global Market Dossier*, or UX/adherence research. Prioritization: MoSCoW + RICE. The claims policy is a binding non-functional requirement.

## 1. Background & problem
The brain stays plastic across life, but plasticity is gated, specific, effortful, and slow. The market is large and fast-growing yet credibility-poisoned (Lumosity's $2M FTC fine; far-transfer is null). No product integrates the *full validated plasticity stack* honestly. Limber productizes the Kleim & Jones recipe — attended, adaptive, spaced practice + the lifestyle levers — measured against a personal baseline, claimed only as far as the evidence allows.

## 2. Objectives & success metrics
- **Business:** ~$100M Year-3 revenue (B2C + B2B PEPM + hardware attach + DiGA); NA optimizer beachhead → global expansion.
- **North star:** *Weekly Trained-and-Consolidated Sessions* (in the ~85% zone AND consolidated).
- **Guardrails (with falsifiable targets, to be validated in pilot):** Day-30 retention ≥35% / Day-90 ≥20% (vs the ~30% / ~10% category floor); ≥70% of sessions held in the ~85% zone; measured near-transfer ≥ d=0.30 on trained domains by week 8; ≥3 lifestyle-lever actions/week among actives; NPS ≥40 and "trust" top-2-box ≥70%; B2B seat utilization ≥30% (renewal threshold). **Unit economics:** target **LTV:CAC ≥ 3:1** with **≤12-month CAC payback** per channel.

## 3. Scope
**In (v1):** Prime→Train→Consolidate loop; adaptive-difficulty training engine (~85% zone) across named domains (attention, working memory, processing speed, cognitive flexibility); honest baseline assessments + 4-week re-assessment; personal-baseline progress (no leaderboards); lifestyle levers (move/sleep/stress); goal tether + implementation intentions; evidence library; ethical engagement; wearable/biometric integration (optional); world-class accessible, localized UX; B2C subscriptions; B2B employer dashboard.
**Out (v1):** disease-treatment/diagnostic claims; far-transfer/IQ claims; invasive neurotech; full DiGA clinical track (v2); broad hardware manufacturing (integrations only).

## 4. Functional requirements (by epic)
**Epic A — Prime (open the window)**
- A1 [Must] State check + breath/HRV regulate option. *Parasympathetic → PFC availability [Strong].*
- A2 [Must] Attention primer + goal-tether reminder. *Salience is biological (Principle 7).*

**Epic B — Train (drive change)**
- B1 [Must] Adaptive-difficulty engine holding **~85% accuracy**. *Validated challenge zone [Strong].*
- B2 [Must] Domain-specific exercises (attention, WM, speed, flexibility). *Specificity (Principle 3).*
- B3 [Must] Novelty rotation. *Novelty → dopamine → lowers LTP threshold [Strong].*
- B4 [Should] Difficulty-zone meter (Rest/Challenge/Overdrive), no raw level numbers.

**Epic C — Consolidate (lock in)**
- C1 [Must] Close-the-loop reflection.
- C2 [Must] Spaced-review scheduling. *Reconsolidation/spacing [Strong].*
- C3 [Must] Sleep wind-down + hygiene support. *Sleep consolidation [Strong].*

**Epic D — Levers (gate plasticity)**
- D1 [Must] Movement/exercise nudges. *Aerobic → BDNF [Strong].*
- D2 [Should] Sleep tracking/insights. D3 [Should] Stress regulation tools.

**Epic E — Measurement & personalization**
- E1 [Must] Baseline battery (5–7 min) + 4-week re-assessment.
- E2 [Must] Progress vs personal baseline; domain radar; 30-day trends (no population leaderboards).
- E3 [Must] Personalize for individual variability (response-based difficulty/modality). *≈30% respond differently.*
- E4 [Should] Wearable/biometric integration (Oura/Apple Health/EEG).

**Epic F — Trust, accessibility, monetization**
- F1 [Must] **Evidence library**: "what the science shows / doesn't," citations per feature.
- F2 [Must] **Claims policy enforced in copy** (near-transfer + lifestyle only; no IQ/dementia/cure claims).
- F3 [Must] WCAG 2.2 AA + APCA; dark/focus modes; reduced-motion; dyslexia/ADHD options; i18n/RTL/offline.
- F4 [Must] Ethical engagement (no dark patterns, no variable-reward compulsion; streaks with forgiveness).
- F5 [Must] B2C tiers + B2B PEPM dashboard (aggregate-only); GDPR/HIPAA-ready data controls + export.

## 5. Non-functional requirements
Performance: offline-capable lite mode (<150KB/screen on 3G); cross-platform.
**Data protection (designed, not just declared):** cognitive-performance and biometric (EEG/Oura/HRV) data are treated as **GDPR Article 9 special-category data** → explicit, granular, opt-in consent (no bundled consent), a **DPIA**, purpose limitation, configurable **data residency** (EU/US), retention limits, and one-tap export/delete. **HIPAA applies only on the covered-entity/BAA path** (B2B/DiGA clinical) — stated explicitly, not blanket-claimed. B2B aggregate dashboards enforce a **minimum cohort size (k-anonymity, k≥10)** to prevent re-identification.
**Clinical safety & vulnerable users:** F-D6 [Must] a **clinical-handoff / safety-netting pathway** — when baseline or in-session signals suggest clinical-range depression/anxiety or significant cognitive decline, the app routes to professional help + crisis resources (not app content). F-D7 [Must] a **"this is not a diagnostic test"** interstitial before/after assessments, with older-adult-appropriate framing (Principle 8) to avoid implying dementia screening.
Compliance: FTC substantiation (claims), EU MDR/**DiGA only for the v2-gated regulated track** (DiGA reimbursement requires a medical-device claim, so it is excluded from v1 and not booked as near-term revenue), EAA/Section 508/GIGW accessibility. Ethics: anti-overclaim review; predictable notifications; clinical advisory board veto on claims/efficacy framing.

## 6. Prioritization (RICE — computed: score = Reach × Impact × Confidence ÷ Effort)
Reach (0–1 share of users/qtr), Impact (0.25–3), Confidence (0–1), Effort (person-months).
| Requirement | Reach | Impact | Conf. | Effort | **RICE** |
|---|--:|--:|--:|--:|--:|
| F1/F2 Evidence + claims policy (moat) | 1.0 | 3 | 0.95 | 2 | **1.43** |
| E1/E2 Baseline + honest progress | 1.0 | 3 | 0.9 | 3 | **0.90** |
| A1/A2 Prime | 0.9 | 2 | 0.9 | 2 | **0.81** |
| D1 Exercise nudge | 0.8 | 2 | 0.85 | 2 | **0.68** |
| C2/C3 Spaced review + sleep | 0.9 | 3 | 0.9 | 4 | **0.61** |
| B1 Adaptive ~85% engine | 1.0 | 3 | 0.85 | 5 | **0.51** |
| E4 Wearable integration | 0.5 | 2 | 0.6 | 4 | **0.15** |
*(Ranked by RICE; the low-effort evidence/claims layer tops the list, confirming the moat is also the cheapest high-impact build. B1 scores lower only because effort is high — it remains a Must.)*

## 7. Key risks (owner · severity · trigger · mitigation)
| Risk | Owner | Severity | Trigger / checkpoint | Mitigation |
|---|---|---|---|---|
| Far-transfer / overclaiming (FTC) | Head of Product + Legal | Existential | Any new marketing/claim copy | Claims policy gate; legal review; cite every claim |
| Adherence (~70% churn) | Growth/PM | Existential | Day-30 retention < 35% in pilot | Visible progress, ethical streaks, coaching, meaning-tether; iterate before scale |
| Efficacy vs BrainHQ | Science lead | High | Competitor publishes / our study underpowered | Build & publish evidence program early; honesty as the wedge |
| DTx commercial trap (Pear/Akili) | CEO/Finance | High | Considering a regulated claim | Lead consumer/B2B; DiGA only where reimbursement is real (v2-gated) |
| Data protection / re-identification | DPO/Eng | High | Special-category data flow or new B2B report | GDPR Art. 9 consent + DPIA; k-anonymity (k≥10); residency |
| CAC > sustainable | Growth/Finance | High | Blended LTV:CAC < 3:1 in any channel | Organic/creator-led acquisition; B2B as ARPU multiplier; pause paid UA | Trust in a hype market (transparency is the brand).

## 8. Release plan
- **v0 (Pilot, NA optimizers):** A1–A2, B1–B3, C1–C3, E1–E3, F1–F4 — prove retention + near-transfer.
- **v1 (Global GA):** + D1–D3, E4, B4, F5 B2B, full i18n/accessibility.
- **v2:** DiGA/clinical recovery track, deeper biofeedback, longevity-stack integrations.

## ✅ Excellent-criteria self-review
Objectives, scope, functional + non-functional requirements, MoSCoW + RICE, evidence-traced decisions, metrics, risks, phased release — tied to cited neuroscience, market, and UX research.

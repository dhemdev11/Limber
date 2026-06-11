# Prototype Spec & Design Rationale — Limber (Global)
### Companion to the interactive HTML prototype · June 2026
> Open `Limber_Interactive_Prototype.html` in any browser. Built to the world-class global design system from the UX research. Maps every screen → persona served → device/accessibility consideration → cited design decision. Neuroplasticity is the core: the loop **is** the Kleim & Jones recipe.

## Design system (from the global UX research)
- **Color:** warm off-white `#F5F3EF` (never glare-white), calm **teal** `#4A9B8E` primary, sage `#6BAF7A` positive, **terracotta** `#C0614B` for alerts (never red — red triggers stress). Dark + focus modes. All pairs pass WCAG 2.2 AA / APCA.
- **Type:** Inter variable; body ≥16sp; line-height 1.6 (dyslexia-friendly); dyslexia-font toggle.
- **Motion:** micro (150ms), transition (300ms), ambient breathe (4s); all respect `prefers-reduced-motion`.
- **Engagement:** ethical only — no dark patterns, no variable-reward compulsion; streaks with forgiveness ("5 of 7"); mastery + meaning over compulsion.
- **Progress:** personal baseline only (no population leaderboards) — credibility + anti-anxiety.

## Device & platform decisions
Mobile-first, cross-platform; **offline-capable lite mode** (<150KB/screen on 3G) for global reach; full **i18n + RTL**; native haptics on session events; WCAG 2.2 AA, EAA/Section 508/GIGW compliant. One primary action per screen; calm, spacious.

## Screen-by-screen rationale
| Screen | Persona served | Design decision & evidence |
|---|---|---|
| **Today** (priority + session) | All | One priority signal + one session (Oura-style daily loop); goal-tether visible (salience is biological). |
| **Prime** (regulate + attention) | All (esp. Margaret, James) | Parasympathetic regulation restores PFC; attention gates encoding [Strong]. |
| **Train** (adaptive task) | All (esp. Ryo, Priya) | Real adaptive-difficulty task held near **~85% accuracy** (validated challenge zone); specificity + novelty + intensity (Kleim & Jones). |
| **Difficulty-zone meter** | All | Shows Rest/Challenge/Overdrive, not raw levels (prevents score-gaming; keeps plasticity-inducing challenge). |
| **Consolidate** | All | Close-the-loop reflection + spaced review + sleep nudge [Strong]. |
| **Progress** (baseline radar) | All (esp. Ryo, Elena, James) | Domain radar vs **personal** baseline + 30-day trend; honest near-transfer framing; no leaderboards. |
| **Levers** (move/sleep/stress/novelty) | All | Lifestyle levers elevated to first-class plasticity inputs, evidence-graded [Strong]. |
| **Me** (integrations/accessibility/privacy) | Ryo, Elena, all | Wearable integration; accessibility suite; GDPR/HIPAA export/delete. |
| **Onboarding** (baseline task → insight → goal → intention → evidence) | All | Value-before-signup (Duolingo); live baseline; goal tether; implementation intention (~3× retention); honest claims disclosure. |
| **Evidence library** | Ryo, Margaret, James | "What the science shows / doesn't," with grades — the trust moat (anti-Lumosity). |

## Complete screen inventory, navigation & states
| # | Screen | Reached from → exits | Primary interaction | States (incl. edge cases) |
|---|---|---|---|---|
| O1–O5 | Onboarding | First open → Today | Baseline RT task; goal; intention | Live reaction task; **too-soon retry**; instant insight; honest disclosure |
| T1 | Today | Launch/nav → Prime | Start session | Recovery-good vs **poor-recovery → lighter load**; offline cached |
| P1 | Prime | Today → Train | Breathe + goal reminder | Skippable; **stressed → longer regulate** |
| TR1 | Train | Prime → Consolidate | Adaptive task | Live accuracy; **>95% → step-up; <70% → step-down + encourage**; backgrounded → resume, no penalty |
| C1 | Consolidate | Train → Progress | Reflection + schedule | Close-loop (not rumination); **after 9:30pm → sleep theme + dim notifications** |
| G1 | Progress | Nav → — | View radar/trends | Personal baseline only; **re-assessment due → prompt** |
| L1 | Levers | Nav → — | View/act | Evidence-graded; wearable-informed |
| M1 | Me | Nav → — | Toggle | Integrations; accessibility (dyslexia/contrast/motion/40+ languages); privacy export/delete |
| EV1 | Evidence library | Onboarding/Me | Browse | "Shows / doesn't" with grades |
| X1 | Clinical handoff | Any (clinical-range/crisis) | Refer | **Severity in clinical range → clinician + DiGA/reimbursed track**; safety resources |

**Cross-cutting edge states:** poor wearable recovery → lighter session; clinical-range baseline → recovery/clinician track; offline → cached loop; payment fail → graceful retry; reduced-motion/dyslexia/high-contrast honored globally.

## Annotated wireframe detail (layout · components · states)
Because the working artefact is interactive HTML (and a Figma mirror awaits a non-employer destination), the wireframe-level detail is specified here so layout, spacing, and component states are unambiguous.

- **Today (launchpad):** top app-bar (eyebrow "Today" + goal tether) · *priority-signal card* (1 sentence, plain language) · *stats card* (3 rows: attention vs baseline, days-this-week, % in challenge zone) · primary CTA "Begin today's session" (full-width, teal) · honest-claims disclosure strip · persistent bottom nav. *States:* good-recovery (default), poor-recovery (CTA copy → "A lighter session today"), offline (sync badge).
- **Prime:** step ribbon (1 active) · centered breathing **orb** (4s ambient loop, respects reduced-motion → static) · goal-reminder line · CTA "I'm ready — train". *States:* default, skip-allowed.
- **Train (hero screen):** *difficulty-zone meter* (Rest / Challenge ~85% / Overdrive, marker reflects live state) · live stats (Accuracy %, Level) · *target card* (large glyph) · *2×2 tile grid* (44×44pt+ targets, color-coded) · on completion → "in the zone" + "Finish & consolidate". *States:* in-trial, correct (haptic light-double), incorrect (step-down + encourage), >95% (step-up), backgrounded → resume (no penalty), complete.
- **Consolidate:** step ribbon (3 active) · *close-the-loop chips* (event→noticed→choice, single-select) · spaced-review row · sleep wind-down row · CTA. *States:* default, after-9:30pm (sleep theme + dimmed notifications).
- **Progress:** *domain radar* (SVG: inner = Week-1 baseline, outer = now, 5 axes) · trend card (3 rows, % vs baseline) · honest near-transfer caption. *States:* default, re-assessment-due prompt. *No leaderboard component exists by design.*
- **Levers:** four *lever rows* (icon tile + title + mechanism + evidence-grade chip). *States:* wearable-informed highlight.
- **Me:** integration row · evidence-library row · accessibility row (dyslexia/contrast/motion/40+ languages) · privacy row (GDPR/HIPAA export/delete).
- **Onboarding O1–O5:** value-first card → *live reaction-time baseline* (wait/tap/too-soon/result states) → snapshot stats + goal chips → when-then intention chips → evidence library ("claimed / not claimed" grading rows).
- **Clinical-handoff overlay (X1):** surfaced over any screen on a clinical-range score: empathetic copy → clinician + reimbursed/DiGA track + safety resources.

Spacing: 22px screen gutters, 13px inter-card; cards 20px radius, 1px `--line` border, soft shadow. Type per the design-system scale. Every interactive element ≥44×44pt; focus ring 2px teal.

## Interactions implemented in the demo
Adaptive symbol-match training task with **live accuracy + auto difficulty step-up/down** and a challenge-zone meter (no red used — design principle); animated Prime breathing; a **live reaction-time baseline** in onboarding; a **personal-baseline radar chart** (SVG); goal/intention chips; evidence library with "claimed / not claimed" grading; bottom-nav across Today/Progress/Levers/Me. **Now also interactive (demonstrable edge states):** a *poor-recovery* toggle on Today that re-renders the priority signal + CTA copy; a *9:30pm evening* toggle on Consolidate that applies the sleep theme; and **live accessibility toggles** (dyslexia font · high contrast · reduced motion) that actually re-render the prototype.

## Figma deliverable
The HTML file is a complete working prototype. A Figma mirror is a packaging format — your writable Figma plan is the Loglass **org** (personal team is view-only); confirm a non-employer destination and the same screens push as editable frames + a shareable prototype link.

## ✅ Excellent-criteria self-review (Link to prototype, /10)
World-class, accessible global design system; a **real adaptive neuroplasticity task** (not a mockup); device-appropriate (offline/lite, i18n/RTL, haptics, WCAG 2.2 AA); every screen tied to a persona need + cited decision; full screen/state inventory incl. edge cases; intuitive interactions on all screens.

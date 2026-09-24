# AG Consulting interactive presentation

## Objective
Build the approved AG Consulting digital presentation as a static Astro site with restrained GSAP motion, using the local approved assets and source-faithful Spanish copy.

## Problem and rationale
The approved Mockup V6 needs to become a maintainable, responsive presentation site rather than a static prototype. The site is sent by email as a professional introduction, not a lead-generation landing page.

## Scope and constraints
- Follow Mockup V6 visual direction.
- Keep copy direct; do not invent metrics, claims, titles, or jargon.
- Use the large logo only in the hero; reveal the small header logo after scrolling past it.
- Respect `prefers-reduced-motion`.
- Use approved local assets only; do not use the rejected methodology artwork.
- Do not commit without explicit user authorization.
- Delivery strategy: ask-on-risk. Forecast: about 300 authored source lines, excluding generated files.
- Test mode: standard verification (explicit user choice, 2026-09-24); use the production build per task rather than strict TDD.

## Tasks

- [x] **1. Bootstrap Astro foundation** — completed
  - Route: delegated direct (`gentle-ai-explore`, `gentle-ai-worker`, then independent verification).
  - Trigger: the task required understanding and creating multiple project/configuration files.
  - Evidence: static Astro scaffold, local runtime assets, strict TypeScript, and baseline page/styles completed. `npm install` and writer `npm run build` passed; independent `npm run build` passed. The authorized `.gitignore` rules now hide only `node_modules/`, `.astro/`, and `dist/`; independent Git-status verification passed. `npm install` reported 3 dependency vulnerabilities (1 low, 1 high, 1 critical), intentionally outside this task scope.
  - Commit: `3a020c3` — `feat: build AG Consulting presentation`.

- [x] **2. Build the presentation content** — completed
  - Route: inline CSS panel-presence correction, then independent verification.
  - Evidence: at 1440×900, 04 now measures 900px like identity/approach/purpose; its frame shares their 70rem bounds and content is centered within 0.01px. All cards/bullets/icons are readable with no overflow. At 390×844, mobile remains natural-height/block layout. Build and Chromium/CDP visual verification passed.
  - Commit: `9da51b1` — `feat: refine presentation interactions`.

- [x] **3. Add motion and verify** — completed
  - Route: delegated direct (`gentle-ai-worker`, then verification as required by native assessment).
  - Add restrained GSAP/ScrollTrigger motion, header-logo behavior, reduced-motion fallback, and run project checks.
  - Checks: build succeeds; interactions and responsive behavior are inspected.
  - Evidence: independent desktop/mobile runtime verification confirmed normal motion, post-hero logo reveal, 18 visible entrance targets, no overflow, and successful build. Reduced-motion/no-JS verification found the header logo visually visible at the hero despite its `hidden` attribute because the global image display rule overrides it.
  - Evidence: base motion and interaction behavior is verified. User authorized a second, motion-only iteration: more noticeable but smooth editorial hero sequencing, heading-word stagger, practice icon/card staging, and restrained illustration parallax. Preserve desktop snap, reduced motion, mobile behavior, and no-JS content visibility.
  - Evidence: final Chromium/CDP verification passed. Hero timeline, heading/card/icon/list staggers, desktop parallax, and soft snap work without overflow or errors. The hero logo is proportionally 270×126.72px with CLS zero. Reduced motion loads no GSAP chunks and has no motion. Build passed.
  - Commit: pending motion refinement commit.

## Progress
- 2026-09-24: Resumed in a new Pi session. Git now resolves correctly at the repository root; no source implementation exists yet.
- 2026-09-24: Completed delegated baseline mapping. `presentacion_asesoramiento.md` remains the copy source of truth; the approved V6 mockup provides visual direction only. Local assets cover hero, closing, logo, and all five practice icons.
- 2026-09-24: User selected standard verification; each implementation task requires its production build rather than strict TDD.
- 2026-09-24: Task 1 writer completed the Astro foundation and its build. Native risk assessment returned `unassessable`, requiring independent verification before accepting the task.
- 2026-09-24: Independent verification passed the static build and task scope checks, but could not accept task 1 because generated install/build directories are not ignored.
- 2026-09-24: User authorized ignoring exactly `node_modules/`, `.astro/`, and `dist/`; the narrow correction was applied and independently verified.
- 2026-09-24: Task 1 completed. Static build and Git artifact hygiene are verified.
- 2026-09-24: Task 2 writer completed the seven-section presentation and passed its production build. Native assessment was unavailable, requiring independent verification; visual readback is not yet observed.
- 2026-09-24: Independent source verification passed; initial browser-tool discovery was incomplete.
- 2026-09-24: User confirmed existing Playwright and Chromium availability; rendered Chromium/CDP screenshots at desktop and mobile exposed a desktop hero overlap and mobile decorative-mark crop.
- 2026-09-24: Diagnosed the Vite-cache incident. `node_modules/.vite/deps/` is correctly ignored, and no generated cache path appeared in full Git status; no remediation is required.
- 2026-09-24: Corrected the desktop hero overlap and mobile decorative-mark crop in CSS; the writer build passed. Native assessment was unavailable, requiring independent screenshot re-verification.
- 2026-09-24: The independent screenshot verifier stalled during its shell step and timed out after 12 minutes. Diagnosis identified a fragile temporary Astro-dev copy with Vite allow-list errors; it did not establish the exact stalled stage.
- 2026-09-24: Bounded static-`dist/` Chromium/CDP re-verification completed in 3.638s. Desktop and mobile rendered cleanly after the CSS correction; task 2 is accepted.
- 2026-09-24: Task 3 writer implemented GSAP entrances, header-logo reveal, and reduced-motion/no-JS handling. Writer install and build passed; native assessment was unavailable, requiring independent runtime verification.
- 2026-09-24: Independent runtime verification passed normal desktop/mobile motion but found the global image display rule overriding the header logo’s `hidden` attribute in reduced-motion and no-JS paths.
- 2026-09-24: Added the narrow header-logo-specific `[hidden]` CSS correction and cleared `hidden` before GSAP controls normal-motion opacity.
- 2026-09-24: Final bounded Chromium/CDP verification passed normal motion, reduced motion, no-JS content visibility, and build. Task 3 is accepted.
- 2026-09-24: User requested a desktop full-screen rhythm correction: narrative sections must fill the viewport while practices remains naturally taller and mobile remains flexible.
- 2026-09-24: The desktop correction passed bounded Chromium/CDP verification. Narrative panels measure 100svh; practices stays content-driven; mobile retains its existing flexible minimums without overflow.
- 2026-09-24: User authorized a desktop-only `proximity` scroll-snap experiment for narrative panels, excluding the tall practices section and mobile.
- 2026-09-24: CSS `proximity` and `mandatory` experiments did not reliably settle wheel scrolling into narrative panels; the mandatory experiment left a temporary Chromium process that was cleaned up.
- 2026-09-24: User selected a desktop-only GSAP soft snap near narrative panels, excluding practices and mobile.
- 2026-09-24: Independent Chromium/CDP runtime verification passed: near-panel desktop soft snap works, far positions and practices remain free, and mobile/reduced-motion are unaffected.
- 2026-09-24: Manual review found the 90px snap threshold and block-level entrances too subtle. User authorized a stronger-but-restrained editorial motion trial.
- 2026-09-24: Refined GSAP soft snap and per-element staggers passed desktop runtime verification. Added local logo favicon; build passes and the `/favicon.ico` 404 is eliminated.

## Next step
User manually reviews the refined motion through the SSH tunnel; commit or adjust only after feedback.

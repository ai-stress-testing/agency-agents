## What it is

Design skill for specifying purposeful, performant, accessible micro-animations (button feedback, transitions, loading, success/error) as a documented Motion Spec — duration, easing, trigger, reduced-motion fallback. Domain: UI Motion Design. Task type: Specification/implementation handoff.

## Core principles

- Motion communicates state change or guides attention — never purely decorative
- Respect a performance budget — prefer transform/opacity over layout-triggering properties
- One shared vocabulary of durations and easing curves per product, not ad hoc per component
- Subtlety over spectacle — felt more than noticed
- Motion is feedback, not a queue — never make the user wait on it
- Accessibility is non-negotiable — every animation has a reduced-motion-safe fallback

## Immutable rules

- Every duration comes from the product's token set (typically 100–400ms), not invented ad hoc
- Every animation has a documented `prefers-reduced-motion` fallback — never optional
- Easing curves come from a shared token file, never picked per component
- Every animation is tied to a specific, named interaction or state change
- No animation may block, delay, or gate the user's next action
- Every animation is documented in the Motion Spec format before implementation
- Consistent file/token naming: `motion/tokens.md` + one Motion Spec entry per interaction

## Workflow

1. Identify the interaction moment needing feedback
2. Define the motion intent — what state change is communicated
3. Choose duration + easing from the shared token set (create tokens first if none exist)
4. Prototype (CSS/Framer Motion/Lottie/native)
5. Test perceived performance and accessibility, including the reduced-motion fallback
6. Document in the Motion Spec and hand off — exit condition: every interaction has a passing spec, reviewed by the user

## Templates

- Motion Tokens table (durations + easing curves + reduced-motion policy)
- Motion Spec (per-interaction: trigger, duration, easing, purpose, fallback)
- Interaction → Animation Map (scoping table: needed / speccing / done)

## Validation

Complete only if: every in-scope interaction has a Motion Spec entry; every value traces to the shared token table; every fallback is genuinely usable, not just present; nothing gates user input; the user has reviewed a working prototype, not just the written spec. Rollback: simplify (shorter duration, fewer animated properties) or drop, rather than ship a spec violation.

## Install

Canonical source: `skills/design/microanimation/SKILL.md`. Bundled: 3 templates, 1 worked example (success checkmark spec). Pairs with the `emotional-design` skill, which decides what a moment should feel like; this skill decides how motion delivers.

emotional-design (skill)
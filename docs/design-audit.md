# Sherman Software — Design audit & redesign notes

Scope: homepage (`src/pages/index.astro` + section components).
Direction: **Sherman Editorial Studio** — Newsreader (display), Hanken Grotesk (body), JetBrains Mono (labels), the registered palette (paper `#fbf9f2`, white, ink `#000000`, espresso `#1d1c16`, terracotta `#b22c0b`, outline `#747878`, ember `#ff633e`).

## Findings before the rework (ranked by impact)

1. **Trust signals were thin and partly unverifiable.** The old "featured case" carried invented figures (a €2.840.500 portfolio, 94/100, +8.4% YTD, "99/100 Lighthouse") and a fake dashboard mock. A prospective client could mistake these for real results — the single biggest credibility risk. Resolved by featuring the genuine live project (Investment Health Checks) with its real tech stack.
2. **Weak, generic first impression.** The hero was a plain two-column text block with two stacked full-width buttons and no distinctive composition.
3. **Muddy type hierarchy.** Body copy was 15px with tight tracking; `t-h1` and `t-h2` were both `2rem`; headings and body shared a display-ish geometric face (Space Grotesk) that hurt long-form readability.
4. **Section monotony.** Services, About, Process and Pricing were all the same `gap-px bg-rule` bordered card grid, at the same rhythm, each headed by a decorative "Section 0X" label.
5. **Decorative clutter.** Borders on nearly every element, corner registration marks, `[ Service 01 ]`, `// Step 01`, "Est. '24" — noise that competed with the content.
6. **Button/CTA inconsistency.** `.btn` used `justify-content: space-between`, floating labels to the far edge; two solid buttons competed in the hero; `.btn-outline:hover` used an off-system hard offset shadow.
7. **No mobile navigation at all** below 1024px — phones got only a logo and a CTA.
8. **Contact form was a stub** (`alert()`), with no validation, loading, success or error states, and the section was a full near-black wash.
9. **Non-palette colours leaked** into the preview chrome (`#ececec`, `#ff5f57`, `#febc2e`, `#28c840`, …) plus `rounded-lg`/`shadow-lg`, all outside the registered system.

## What changed

- **Tokens & type (`global.css`).** Rebuilt the `@theme` on the registered palette and brand faces; body raised to 17px/1.65; display type now scales with `clamp()`; a single `--radius-brand` (0.125rem) replaces everything else. Focus, selection, scrollbar and reduced-motion handling centralised.
- **Hero (`Hero.astro`).** Editorial masthead with a titled rule, a large `clamp()` display headline with an italic terracotta accent, a supporting brief, one primary + one secondary action, and an honest three-fact proof baseline (direct contact / fixed-price agreements / 1-working-day reply) sourced from existing copy.
- **Header (`Header.astro`).** Real mobile menu (`aria-expanded`, `aria-controls`, Escape to close, auto-reset at the desktop breakpoint), calmer nav labels, consistent CTA.
- **Sections.** Services became a full-width ledger (index / title / copy + bullets); About became an editorial pull-quote plus a borderless definition grid; Process became a four-step numbered ledger; Pricing became a ruled three-column comparison with a terracotta-topped highlighted tier; the FAQ became a native `<details>` accordion; the value strip became a numbered typographic band. Section eyebrows are now meaningful ("01 / Werk", "02 / Diensten", …).
- **Featured case (`FeaturedCase.astro`).** Kept the live project and scaled preview, but rerendered the chrome in the palette (single terracotta mark, outline rules, no shadows/mac traffic lights, brand radius).
- **Contact (`Contact.astro`).** Light editorial section; the dark wash is gone. The form now validates on blur, shows inline errors with `aria-invalid`/`aria-describedby`, exposes a live `role="status"` region, and replaces the `alert()` with an inline success state.
- **Copy/data (`site.ts`).** Removed the dead invented `caseSpecs`; stripped duplicated numeric prefixes from the step titles; clarified the "Op aanvraag" web-application price.

## Files changed

`src/styles/global.css`, `src/layouts/BaseLayout.astro`, `src/data/site.ts`, and the components `Header`, `Hero`, `ValueStrip`, `FeaturedCase`, `Services`, `About`, `Process`, `Pricing`, `Faq`, `Contact`, `Footer`.

Routes, Astro/Tailwind stack, Dutch copy and links are unchanged.

## Remaining issues / assets to supply

- **No real proof yet**: no testimonials, client logos or additional case studies. The site is honest but light on social proof — add real ones when available.
- **Contact form has no backend**: the success state is client-side only. Wire an endpoint (Formspree, a serverless function, etc.) to actually receive enquiries.
- **No logo asset**: the wordmark is set in Newsreader. Supply a logo if one exists.
- **Preview iframe** loads an external site and needs network access; consider a static screenshot fallback for offline/edge cases.

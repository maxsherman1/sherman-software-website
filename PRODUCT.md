# Product

<!-- impeccable:product-schema 1 -->

## Platform

web

## Users

Dutch small-business owners and entrepreneurs who need a professional website or custom web application. They value direct communication with the developer, transparent pricing, and clear project agreements. They are not looking for a large agency — they want the personal touch of an independent developer who cares about quality.

## Product Purpose

Sherman Software is an independent Dutch web development studio. It helps businesses and entrepreneurs build professional websites and custom web applications. The studio is characterized by:

- **Independent**: A single developer, not an agency
- **Approachable**: Direct, personal communication
- **Affordable and accessible** without appearing cheap
- **Professional, technically capable, and trustworthy**
- **High-quality engineering combined with thoughtful design**
- **Transparent**: Clear agreements on planning, costs, and results before work begins
- **Direct contact**: The client speaks directly with the developer building their website

## Positioning

The positioning that a neighboring product could not truthfully copy:

Sherman Software offers the combination of individual-engineer-level directness and craftsmanship with the professional quality of an agency. The unique mechanism is **single-developer accountability with transparent fixed-price agreements** — the client gets one person who writes every line of code, gives one price up front, and replies within one working day.

## Operating Context

- **Development**: Astro + Tailwind CSS v4, static site generation
- **Hosting**: Static sites deploy to Vercel or similar; web applications use Next.js / React / TypeScript / PostgreSQL / Vercel
- **Language**: All customer-facing content is in Dutch
- **Process**: Four-step workflow — Verkenning (discovery), Ontwerp (design), Ontwikkeling (development), Livegang (launch)
- **Communication**: Direct email contact with the developer

## Capabilities and Constraints

- **Websites**: Business websites and redesigns — representative, fast, SEO-optimized, mobile-readable, self-manageable
- **Web applications**: Custom dashboards, client portals, system integrations with security attention
- **Maintenance**: Proactive management, security updates, backups, ongoing optimization
- **Pricing model**: Fixed-price for websites (from €795), custom quotes for applications, subscription for maintenance (from €29/month)
- **Response time**: Within 1 working day
- **Technical constraint**: Static Astro site with no backend for the contact form (client-side success state only)

## Brand Commitments

- **Name**: Sherman Software
- **Voice**: Concise, confident, approachable, human — avoids formal corporate language, exaggerated marketing claims, and generic AI-generated copy
- **Visual identity**: "Sherman Editorial Studio" — Newsreader (serif display), Hanken Grotesk (body sans), JetBrains Mono (labels) — flat and sharp aesthetic with 0.125rem radius, 1px borders, alternating paper/white surfaces
- **Palette**: Paper `#fbf9f2` (ground), Ink `#000000` (text), Espresso `#1d1c16` (primary accent), Terracotta `#b22c0b` (secondary), Outline `#747878` (borders), Ember `#ff633e` (link hover)
- **Dutch identity**: Clearly positioned as a Dutch (Nederland) studio, remote and on-site

## Evidence on Hand

- Homepage is live at `http://localhost:4321` (Astro dev server) or built to `dist/`
- Featured case study: Investment Health Checks webapp (https://investmenthealthchecks.com) — a real, live project
- Design audit in `docs/design-audit.md` documenting the current design system
- Three verified selling points: Direct contact, Fixed price agreements, Response within 1 working day

## Product Principles

1. **Honest by default** — No invented figures, testimonials, or fabricated claims. Every number, metric, and social proof must be real or clearly labeled as illustrative.
2. **Direct and personal** — The experience should communicate individual accountability, not agency size. Communication is 1:1 with the developer.
3. **Craft over template** — The website itself must demonstrate the quality of work Sherman Software produces. It is a portfolio and proof of capability in one.
4. **Clear and simple** — No unnecessary complexity. Every element serves the goal of communicating what Sherman Software does and how to get in touch.
5. **Dutch, through and through** — The language, tone, and identity are authentically Dutch, avoiding international-sounding corporate boilerplate.

## Accessibility & Inclusion

- Semantic HTML throughout (Astro components)
- Keyboard navigation supported (focus-visible outlines, Escape-to-close for mobile nav)
- `prefers-reduced-motion` respected globally
- Skip-to-content link for screen readers
- Form validation with proper `aria-invalid` and `aria-describedby`
- Color contrast: black/white/terracotta on paper background

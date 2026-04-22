# VibesAI by Prism

> A frictionless vibe-coding platform with AI-powered code generation, live preview, and one-tap deploy — built for builders who think in ideas, not syntax.

**Status:** Planning Phase &nbsp;|&nbsp; **Part of:** [Prism Suite](#prism-suite)

---

## Overview

VibesAI is the AI coding app in the Prism app suite. Users describe what they want to build in plain language and VibesAI — powered by **Claude Sonnet 4.6** — writes the code, renders a live preview, and publishes it with a single tap. No terminal, no config, no syntax knowledge required.

Inspired by VibecodeApp, with a goal to match or exceed its prompt-to-app speed while building a more polished, Prism-native experience.

---

## Core Features

| Feature | Description |
|---|---|
| **AI Code Generation** | Natural language → working code via Claude Sonnet 4.6 |
| **Live Preview / Hot Reload** | Real-time preview pane that updates as AI writes code |
| **Template Library** | Curated starters (landing page, dashboard, mobile UI, game) — all AI-editable |
| **One-Tap Deploy** | Instant publish to a live URL, no DevOps required |

**Design principle:** Every UX decision reduces steps, never adds them. Onboarding under 60 seconds. The AI starts working the moment the user types.

---

## Target Audience

- **Beginners & non-coders** — students, designers, entrepreneurs, content creators blocked by not knowing how to code
- **Indie devs & solo builders** — developers who want to prototype fast, iterate without context switching, and ship without DevOps overhead

---

## Platforms & Stack

| Platform | Priority | Approach |
|---|---|---|
| **Web** | 1 — Primary | Next.js (React), PWA-ready |
| **Desktop** | 2 | Tauri wrapper around the web app |
| **iOS** | 3 | WKWebView shell or React Native Web bridge |

Web-first architecture avoids maintaining separate codebases while still hitting all three platforms.

---

## Design Language

VibesAI uses the Prism suite's shared visual identity:

- **Apple Liquid Glass aesthetic** — clear, translucent crystal panels (visionOS / iOS 18 style), not matte frosted blur
- **Pink-to-blue gradient** (`#E8829A` → `#7AAECC`) — used in accents, borders, and glow halos only, not as fills
- **Dark mode base** — deep near-black (`#0d0d0f`) with glass panels; light mode variant uses clear glass on white/light grey
- **Typography** — Space Grotesk (headings) + DM Sans (body)

All Prism apps share this gradient identity and logo mark family.

---

## Prism Suite

VibesAI is one of five apps in the Prism ecosystem:

| App | Description |
|---|---|
| **Prism** | Social media flagship |
| **Prism Vault** | Budgeting app |
| **Prism Geo** | Map & weather (prototype) |
| **Prism Games** | Creator game platform (TBD) |
| **VibesAI** ← | Vibe-coding AI app *(currently planning)* |

All apps share design language and will eventually be unified under a **Prism Suite subscription**.

---

## Roadmap

```
Phase 1 — Foundation (Web MVP)
  Auth, prompt → code generation, basic live preview,
  5–10 starter templates. Web only. Ship and get feedback.

Phase 2 — Core Loop (Deploy + Iterate)
  One-tap deploy to VibesAI subdomain. AI-assisted error
  recovery. Expanded template library. Project dashboard.

Phase 3 — Desktop + Polish
  Tauri desktop wrapper. Full liquid glass UI. Split-pane
  code + preview. Performance tuning. Monetization layer.

Phase 4 — iOS + Prism Integration
  App Store release. Projects shareable via Prism social.
  Prism Suite subscription tier.
```

---

## Monetization (TBD)

Three candidates — decision needed before building paywall logic:

1. **Freemium + Pro** — free tier with limited AI credits/month; Pro unlocks unlimited generation, deploy, custom domains
2. **Usage-based credits** — pay per generation or deploy; low barrier to start
3. **Prism Suite pass** — one subscription across all Prism apps (higher LTV, stronger suite lock-in)

---

## Open Questions

- [ ] Which monetization model to pursue
- [ ] Supported frameworks — HTML/CSS/JS only, React, or multi-framework? (affects preview architecture)
- [ ] Deploy infrastructure — self-hosted CDN, Vercel, or Cloudflare Pages?
- [ ] Relationship between VibesAI and the Prism Games platform — separate or VibesAI becomes the engine?

---

## Competitive Reference

**VibecodeApp** — key things to match or improve:

1. **Prompt-to-app speed** — how fast from blank prompt to something runnable
2. **Template discoverability** — users who start from a template ship faster (key retention lever)
3. **Error handling UX** — auto-detect broken AI output and offer one-tap fix; never dump raw errors on users
4. **Deploy flow** — count steps from "done" to "live URL"; VibesAI target is **1 tap**

---

*This repository contains the planning document for VibesAI. See [VibesAI_Plan.html](VibesAI_Plan.html) for the full interactive version.*

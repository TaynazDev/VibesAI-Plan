# VibesAI by Prism — Full App Spec

> Prism Suite — App Planning Doc

---

## Identity

- **App name:** VibesAI by Prism
- **Tagline:** A frictionless vibe-coding platform with AI-powered code generation, live preview, and one-tap deploy — built for builders who think in ideas, not syntax.
- **Status:** Planning Phase
- **Platforms:** iOS · Web · Desktop
- **AI model:** Claude Sonnet 4.6 via GitHub Copilot
- **Part of:** Prism Suite

---

## Prism Suite — Where VibesAI Fits

| App | Description | Status |
|---|---|---|
| Prism | Social media flagship | — |
| Prism Vault | Budgeting app | — |
| Prism Geo | Map & weather | Prototype |
| Prism Games | Creator game platform | TBD |
| **VibesAI** | Vibe-coding AI app | **Currently planning** |

All Prism apps share the pink-to-blue gradient identity with the same logo mark family. Each app may lean more or less into the palette but all stay within the same visual system.

**VibesAI description:**
Vibe-coding AI app. Inspired by VibecodeApp. AI generates code from natural language prompts, with live preview and direct deploy — no friction, no setup hell.

---

## Design Language

### Aesthetic
- **Style:** Apple Liquid Glass — clear, translucent glass surfaces (like visionOS / iOS 18 liquid glass), not just frosted blur. Panels feel like polished crystal, not matte acrylic.
- **Gradient:** Pink-to-blue (`#E8829A` → `#7AAECC`), appears in accents, borders, and glow halos only. Glass panels are clear; color bleeds in through edges and interactions, not as fills.

### Color Tokens
| Token | Value | Use |
|---|---|---|
| `--pink` | `#E8829A` | Primary accent |
| `--pink-light` | `#f2abbe` | Lighter pink |
| `--blue` | `#7AAECC` | Secondary accent |
| `--blue-light` | `#a8cfe0` | Lighter blue |
| `--grad` | `linear-gradient(135deg, #E8829A 0%, #b39dc0 50%, #7AAECC 100%)` | Full gradient |
| `--grad-subtle` | `linear-gradient(135deg, rgba(232,130,154,0.12) 0%, rgba(122,174,204,0.12) 100%)` | Subtle tinted fill |
| `--bg` | `#0d0d0f` | Page background |
| `--surface` | `#141417` | Card surface |
| `--surface2` | `#1a1a1f` | Secondary surface |
| `--border` | `rgba(255,255,255,0.07)` | Default border |
| `--border-accent` | `rgba(255,255,255,0.13)` | Stronger border |
| `--text` | `#f0eff4` | Primary text |
| `--text-muted` | `rgba(240,239,244,0.55)` | Secondary text |
| `--text-faint` | `rgba(240,239,244,0.3)` | Tertiary / label text |

### Surface Types
1. **Liquid glass panel** — `rgba(232,130,154,0.18)` to `rgba(122,174,204,0.18)`, subtle gradient background, `0.5px solid rgba(232,130,154,0.25)` border
2. **Gradient accent** — full `--grad` fill, white text
3. **Dark surface base** — `--surface2` background, `--border-accent` border

### Modes
- **Dark mode:** Deep near-black (`#0d0d0f`) base with crystal glass panels
- **Light mode:** Clear glass on white/very light grey base
- Both use the same gradient accent system

### Typography
- **Headings:** Space Grotesk — weights 300, 400, 500, 600, 700
- **Body:** DM Sans — weights 300, 400, 500, 600
- **Base font size:** 15px, line-height 1.7

---

## Core Features

### 1. AI Code Generation
Describe what you want to build in plain language. VibesAI — powered by Claude Sonnet 4.6 — writes the code. No syntax knowledge required.

### 2. Live Preview / Hot Reload
See changes instantly as AI writes or edits code. Split-pane or overlay preview that updates in real time without manual refresh.

### 3. Template Library & Starters
Curated project starters so users can jump into a landing page, mobile UI, dashboard, or game in one tap. Templates are AI-editable from day one.

### 4. Deploy Directly from the App
One-tap publish. No terminal, no config. VibesAI handles hosting so creators can share a live URL immediately after building.

### Frictionless Experience — Core Design Principle
Every UX decision should reduce steps, not add them:
- Onboarding in under 60 seconds
- No project setup wizard
- The AI starts working the moment the user types
- Think: **Notion meets Cursor meets a magic wand**

---

## Target Audience

### Beginners & Non-Coders
People with ideas who've been blocked by not knowing how to code. VibesAI removes that barrier entirely — natural language is the interface.

- Students
- Designers
- Entrepreneurs
- Content creators

### Indie Devs & Solo Builders
Developers who want to move faster — prototype in minutes, iterate without context switching, and ship without DevOps overhead.

- Indie hackers
- Freelancers
- Startup founders

---

## Platform Strategy

### Web App — Priority 1
Primary surface. Accessible from any browser, easiest to iterate and deploy. Should be PWA-ready for offline capability.

### Desktop — Priority 2
Power-user surface. Larger canvas for split-pane coding + preview. Likely Electron or Tauri wrapping the web app.

### iOS — Priority 3
Mobile capture for quick prompts and project browsing. Full editing on iPad, lighter experience on iPhone.

### Recommended Stack
- **Web:** Next.js (React)
- **Desktop:** Tauri wrapper (lighter than Electron, better performance)
- **iOS:** Native WKWebView shell or React Native Web bridge — avoids maintaining two separate codebases while still hitting the App Store

---

## Monetization Options (TBD — Revisit After MVP)

### Option A: Freemium + Pro
Free tier with limited AI credits/month. Pro unlocks unlimited generation, deploy, and custom domains.

### Option B: Usage-Based Credits
Pay per AI generation or deploy. Low barrier to start, scales with power users. Works well alongside a free starter pack.

### Option C: Prism Suite Pass
One subscription unlocks premium features across all Prism apps — Vault, social, VibesAI. Higher LTV, stronger suite lock-in.

---

## Competitive Reference — VibecodeApp

Key things to observe and replicate or improve upon:

1. **Prompt-to-app speed** — How fast does it go from a blank prompt to something runnable? VibesAI should match or beat this.
2. **Template discoverability** — How easy is it to find and remix a template? This is a key retention lever — people who start from a template ship faster.
3. **Error handling UX** — What happens when the AI produces broken code? VibesAI should auto-detect and offer a one-tap fix rather than dumping raw errors on users.
4. **Deploy flow** — Count the number of steps from "done" to "live URL". VibesAI's goal: **1 tap**.

---

## Build Roadmap

### Phase 1 — Foundation (Web MVP) ← START HERE
- User auth
- Prompt → code generation (Claude Sonnet 4.6)
- Basic live preview pane
- 5–10 starter templates
- Web only
- **Goal:** Ship and get feedback

### Phase 2 — Core Loop (Deploy + Iterate)
- One-tap deploy to a VibesAI subdomain
- AI-assisted error recovery
- Expanded template library
- Project dashboard

### Phase 3 — Desktop + Polish
- Tauri desktop wrapper
- Liquid glass UI fully applied
- Split-pane code + preview
- Performance tuning
- Monetization layer added

### Phase 4 — iOS + Prism Integration
- App Store release
- Projects visible/shareable via Prism social app
- Prism Suite subscription tier

---

## Open Questions (Must Decide Before Building)

| # | Question | Why It Matters |
|---|---|---|
| 1 | **Monetization model** | Freemium, credits, or Prism Suite pass — needs a decision before building paywall logic |
| 2 | **Supported frameworks** | HTML/CSS/JS only? React? Multi-framework? Scoping this early affects the live preview architecture significantly |
| 3 | **Deploy infrastructure** | Self-hosted CDN, Vercel partnership, or Cloudflare Pages? Cost and latency implications vary a lot |
| 4 | **VibesAI vs Prism Games** | Decide whether the game creator platform is separate from VibesAI or if VibesAI becomes the engine for it |

# AI-Powered Marketing Page ("Wavelength")

A dark, immersive landing page for **Wavelength** — an AI-powered marketing/audio product, originally generated with [v0.app](https://v0.app). Features an interactive in-browser demo playground, glassmorphism cards, and animated sound-wave visuals.

## What it does

- Markets an AI marketing tool ("Wavelength") with a full landing layout: hero, features, live demo, pricing, CTA.
- **Interactive demo section** with three tabbed playgrounds that simulate AI behavior client-side:
  - **Sentiment Analysis** — mock sentiment scoring demo
  - **Content Adaptation** — mock tone/audience adaptation demo
  - **Trend Prediction** — mock trend forecasting demo
- All demos run in the browser — no backend, no API keys.

## Features

- **Animated sound-wave visuals** (`sound-wave-animation`, `audio-wave-icon`) — brand-matched audio theme.
- **Glassmorphism cards** + gradient backgrounds for a premium dark aesthetic.
- **Sticky glass header** with anchor nav (Features / Demo / Pricing).
- **shadcn/ui-style components** — tabs, slider, textarea, switch, badge, card.
- Responsive layout, Lucide icons, Tailwind styling.
- Fully **static-exportable** (`output: "export"` in `next.config.mjs`) — deployable to any static host.

## Tech stack

- **Next.js 15** (App Router) + **React 19** + **TypeScript**
- **Tailwind CSS** + shadcn/ui-style component set
- **Lucide React** icons
- Custom canvas/CSS animations (sound waves, gradients)
- Package manager: pnpm (`pnpm-lock.yaml`)

## Quick start

```bash
# 1. Clone
git clone https://github.com/girishlade111/ai-powered-marketing-page.git
cd ai-powered-marketing-page

# 2. Install dependencies
pnpm install        # or: npm install --legacy-peer-deps

# 3. Run the dev server
pnpm dev            # or: npm run dev
```

Open http://localhost:3000 in your browser.

### Build (static export)

```bash
pnpm build          # or: npm run build
```

The static site is emitted to `out/` (via `output: "export"`). Serve it with any static server:

```bash
npx serve out
```

## Project structure

```
ai-powered-marketing-page/
├── app/
│   ├── page.tsx        # Landing page (hero, features, demo, pricing)
│   ├── layout.tsx      # Root layout, fonts, providers
│   └── globals.css
├── components/
│   ├── demo-section.tsx       # Tabbed demo container
│   ├── demos/
│   │   ├── sentiment-demo.tsx  # Sentiment analysis playground
│   │   ├── adaptation-demo.tsx # Content adaptation playground
│   │   └── trend-demo.tsx      # Trend prediction playground
│   └── ui/            # glass-card, gradient-background, sound-wave-animation,
│                      # audio-wave-icon, tabs, slider, textarea, …
├── lib/
│   └── utils.ts       # cn() class-name helper
├── public/            # Static assets and placeholders
└── next.config.mjs    # Next.js config (static export enabled)
```

## Environment variables

None required — the site and all demos are 100% client-side with simulated data. (If you connect real AI APIs later, store keys in `.env.local`, which is already git-ignored.)

## Deployment

Statically exportable — deploy anywhere that serves static files:

- **Cloudflare Pages** — live at https://ai-powered-marketing-page.pages.dev
- Alternatively: GitHub Pages, Netlify, Vercel — just upload the `out/` directory after `pnpm build`.

No server, no database, no build-time secrets needed.

## Notes

- Generated with v0.app; the original v0 sync README has been replaced with this documentation.
- ESLint/TypeScript errors are ignored during builds (`next.config.mjs`) for frictionless static export.
- Placeholder images in `public/` can be swapped for real brand assets.

---

Built by Girish Lade — https://ladestack.in

# BLOCKBEAT — Design Brief

## The product in one line
A live, generative audiovisual instrument that turns the Monad chain into music. Every block (one every 400ms) strikes a note; the visuals are a real-time reading of network activity. Watch the chain, hear the chain.

## The core idea (why it's interesting)
- Monad produces a block every **400 milliseconds** — fast enough to feel like a pulse, slow enough to dance to. That cadence is the heartbeat of the whole piece.
- The output is a **pure function of the block stream**: same blocks in → identical sound + image out, forever. It's not decorative motion graphics; it's a deterministic instrument reading on-chain data (block height, hash, tx count, network load).
- It should feel like you're watching a living organism, not a dashboard. Tense when the network is congested, calm when it's quiet.

## What's on screen (current layout — feel free to rethink)
1. **The visualization** — full-bleed canvas. Today it's a scrolling seismograph/oscilloscope: each block is a vertical "strike" that scrolls left, height = transaction volume, color = network load, plus particle bursts and a pulsing "now" ring at the right edge. This is the hero. Reimagine it however reads best.
2. **Top-left brand lockup** — Monad logomark + "BLOCKBEAT" wordmark.
3. **Top-right tagline** — one line of poetic copy about the 400ms heartbeat.
4. **Bottom-left live readout** — block #, hash, tx count, load %, and the notes currently playing. Technical, monospace, ticker-like.
5. **Bottom-right controls** — primary "Begin", "Send a pulse" (user injects a marked block), "Stop".
6. **Opening state** — a centered intro card with title, a short explainer paragraph, and a single "Begin" CTA (audio requires a user gesture to start).

## States to design
- **Intro / pre-start** (centered explainer + Begin CTA over a dimmed canvas)
- **Running — calm** (low network load: cool colors, sparse, slow)
- **Running — active** (medium load)
- **Running — congested** (high load: hot colors, dense, tense, particles everywhere)
- **User pulse** (a distinct, special-feeling event the user triggers)
- **Stopped**
- Responsive: desktop hero, but it should survive on mobile/portrait.

## Brand: Monad design system (please stay on-system)
Pulled from monad.xyz/brand-and-media-kit.

**Colors**
- Monad Dark Navy `#0E091C` (ground)
- Monad Purple `#6E54FF` (primary accent / active core)
- Monad Light Purple `#DDD7FE`
- Monad Cyan `#85E6FF`
- Monad Light Blue `#B9E3F9`
- Monad Pink `#FF8EE4`
- Monad Orange `#FFAE45`
- White `#FFFFFF`, Black `#000000`

**Suggested "load → heat" mapping** (the core color logic — calm to congested): Light Blue → Purple → Pink → Orange. Open to a better idea.

**Typography**
- **Britti Sans** — headlines / titles / wordmark
- **Inter** — body / paragraphs
- **Roboto Mono** — labels, buttons, the technical readout, code, decor

**Logo:** Monad rounded-diamond logomark with the inner diamond counter. Use the official SVG from the brand kit.

## The feeling we want
Premium, alive, a little hypnotic. "A scientific instrument designed by people with taste." Not a crypto dashboard, not a generic dark-mode SaaS app. Closer to a planetarium exhibit, a synthesizer, or an Aphex-Twin-meets-Bloomberg-terminal energy. Restraint over clutter. The motion and color carry it.

## Hard constraints (so the design is buildable)
- It's a **single full-viewport canvas experience** in the browser. The viz is drawn programmatically (canvas 2D / WebGL), so deliver direction + motion intent, not pixel-perfect static comps for the animated part.
- It runs in **real time at a 400ms beat** — design for continuous motion, not a still frame. Show key frames / a short motion study if you can.
- **Audio is central** — the visual events are locked to musical events. Sound and image are the same signal.
- Must look right against pure dark navy; everything glows.

## What I need back from you
1. Direction for the **hero visualization** (the seismograph is a starting point, not a requirement — pitch something better if you've got it). Motion intent for calm vs congested.
2. The **chrome**: brand lockup, readout, controls, intro card — laid out and styled on-system.
3. A **color/heat system** tying network load to the Monad palette.
4. The 3–4 key **states** above as frames.
5. Type, spacing, and component specs I can hand to eng.

Working reference build exists (functional but visually weak) — happy to share it so you can see the live motion and timing.

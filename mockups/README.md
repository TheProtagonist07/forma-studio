# FORMA — Website Mockups

Ultra-high-fidelity, fully interactive HTML mockups for the FORMA design & manufacturing studio website. A digital design museum that also sells products — not a store.

## How to view

Open any file directly in a browser, or serve the folder:

```bash
python3 -m http.server 8423 --directory mockups
# → http://localhost:8423
```

Every page has a floating **MOCKUPS** switcher (bottom-right) to jump between all 8 screens.

## The pages

| File | Screen | Signature interaction |
|---|---|---|
| `index.html` | Homepage — the museum entrance | Floating dust particles, hover-expanding "rooms" corridor, loader |
| `collection-minimalist.html` | Room 01 · Kanso (Minimalist) | 2-second slow fades, paper-white Japanese atmosphere, vast whitespace |
| `collection-cozy.html` | Room 02 · Hearth (Cozy House) | Candlelight flicker, floating embers canvas, lit-lantern SVGs, A/B/C amber "failed experiment" |
| `collection-cyberpunk.html` | Room 03 · Volta (Cyberpunk) | Glitch typography, scanlines, mouse-reactive particle grid, terminal build-log |
| `collection-organic.html` | Room 04 · Terra (Organic) | Morphing blob hero (3 nested growth surfaces), growth-from-root reveals, Gen 0→800 algorithm story |
| `product.html` | Product page — Meridian Vessel № 07 | **Real 3D turntable** (canvas lathe renderer, drag to rotate, wireframe/shaded modes), manufacturing timeline, timelapse player, full specs |
| `configurator.html` | The Atelier — parametric configurator | **Sliders rewrite live 3D geometry**; price/grams/print-time recompute from actual surface-area integration + the studio COGS model |
| `quote.html` | Upload Your Design — instant quote | **Real STL parsing in-browser** (binary + ASCII, signed-tetrahedron volume, bounding box, triangle count) → instant ₹ quote with material/quality/qty controls |

## Design system

- **Global identity:** near-black `#0b0907`, warm amber `#d9a468`, Fraunces (serif display) + Space Grotesk (UI) + JetBrains Mono (engineering labels)
- Each collection room **completely transforms** palette, typography feel, motion timing, and storytelling voice — per the core design philosophy.
- Pricing everywhere uses the business-plan cost model: `(filament + ₹16/h machine + ₹85 handling/QC/packaging) × 1.15 failure buffer × 2.5 margin`, rounded to ₹x49/x99.

All pages are dependency-free single files (Google Fonts CDN only) — they double as the starting skeleton for the production Next.js build.

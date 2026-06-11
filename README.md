# FORMA — Designs That Live

A digital design museum for an original 3D design & manufacturing studio — **not a store**. Every object is designed from zero in parametric CAD and grown layer by layer in-studio (Lucknow, IN).

This repository holds the high-fidelity interactive mockups for the studio website: four cinematic collection "rooms" that each transform the entire site's atmosphere, a drag-to-rotate 3D product viewer, a parametric configurator with live geometry and pricing, and an instant-quote engine that parses STL files directly in the browser.

## Quick start

```bash
python3 -m http.server 8423 --directory mockups
# → http://localhost:8423
```

No build step, no dependencies — every page is a self-contained HTML file (Google Fonts CDN only).

## The exhibition

| Room | Page | World |
|---|---|---|
| Entrance | `mockups/index.html` | Dark museum hall — dust, spotlights, a vessel on a pedestal |
| 01 · Kanso | `mockups/collection-minimalist.html` | Japanese paper-white silence, 2-second fades |
| 02 · Hearth | `mockups/collection-cozy.html` | Candlelight, floating embers, winter evenings |
| 03 · Volta | `mockups/collection-cyberpunk.html` | Neon glitch, scanlines, reactive particle grid |
| 04 · Terra | `mockups/collection-organic.html` | Morphing growth forms, earth tones |
| Object | `mockups/product.html` | Real-time 3D lathe turntable (canvas, zero libraries) |
| Atelier | `mockups/configurator.html` | Sliders rewrite live geometry → price/weight/print-time recompute |
| Custom | `mockups/quote.html` | In-browser STL parsing (signed-tetrahedron volume) → instant quote |

See [mockups/README.md](mockups/README.md) for the full design-system notes.

## Engineering highlights

- **3D without a 3D library** — the product viewer and configurator render a parametric lathe surface (depth-sorted quads, painter's algorithm, fake key light) on a 2D canvas in ~80 lines.
- **Real mesh analysis** — the quote page parses binary *and* ASCII STL, integrates signed tetrahedron volumes (validated: 20 mm cube → exactly 8.00 cm³), and computes bounding box + triangle count, all client-side. Files never leave the browser at quote time.
- **Honest pricing model** — quotes derive from filament mass + machine-hours + handling, with a failure buffer and margin, not a magic number.

## Roadmap

Production build: Next.js + PostgreSQL + Razorpay, order pipeline automated with n8n on self-hosted infrastructure. The mockups double as the design-system spec for that build.

---

© FORMA studio. All product geometry, designs, and content are original work — please don't reuse without permission.

---
name: unmol-site-design
description: Design rules for Unmol Sharma's personal site (die-shot portfolio). Read before writing or editing any UI for the site; bans default AI styling and pins exact colors, fonts and spacing.
---

# Unmol Sharma site — design SOP

The site is a silicon die seen from above. The homepage is the die; each functional block is a project category; the bond-pad ring is contact. Everything else is quiet so the die can be the one bold thing.

Read this before any UI change. If a request conflicts with this file, follow the request and update this file.

## 1. Banned defaults (never use unless Unmol asks by name)

Fonts
- Inter, Roboto, Arial, Helvetica, Poppins, Montserrat, Space Grotesk, Open Sans, Lato
- `system-ui` / platform sans as a display face (fallback stacks only)
- Monospace for anything that is not code, a code name, a date, or a measurement

Color and surface
- Purple→blue, purple→pink or slate gradients, on anything
- Gradient text
- Glassmorphism / backdrop blur as decoration (the sticky bar's 8px blur is the only exception)
- Drop shadows on cards; neon glows except the selected die block
- Colored `border-left`/`border-right` accents on cards or list items
- Pure #000 or #FFF

Layout and components
- Grids of same-size cards as the main structure. Projects use a featured spread + an index list, never a uniform card wall
- Eyebrow/kicker labels above headings
- Section numbering (01 / 02 / 03)
- Big-number stat tiles
- Emoji or Unicode glyphs (↗ → ★) as icons. Use inline SVG, 1.5px stroke, `currentColor`
- `rounded-xl` everywhere. Max radius is 2px (6px for the die and the layout-tool window)
- Centered-everything layouts. Text is left-aligned

## 2. Color (exact) — "wafer grey"

| Token | Hex | Use |
|---|---|---|
| `--ground` | `#EDEDED` | page |
| `--paper` | `#F7F7F5` | layout-tool window, tags |
| `--ink` | `#171717` | headings, primary text, solid buttons |
| `--ink-2` | `#3A3A3A` | body text |
| `--muted` | `#5F5F5F` | dates, codes, captions (5.4:1 on ground) |
| `--line` | `#D2D2D0` | 1px rules and borders |
| `--accent` | `#2B59FF` | the only accent: links, focus, selection, current state. Never on dark surfaces |
| `--board` / `--board-2` | `#1B1C1F` / `#24262A` | the PCB in the boot sequence |
| `--copper` | `#C8894A` | traces, bond pads, the I/O block |
| `--die` / `--die-core` | `#23262C` / `#15171B` | the die, a dark object sitting on the grey page |

Die blocks are told apart by hatch angle and density first, muted hue second:
NPU `#7FB8AE` 135° · QPU `#8EA3D1` 45° fine · RAD `#CF968C` 60° wide · CORE `#A79BD1` 0° · SRAM `#C7B072` 0° fine · EXP `#9DB592` 90° · IO copper 150° coarse.

Single light page by choice; the board and die are the only dark things.

## 3. Type (exact)

| Role | Face | Weight | Size / line-height | Tracking |
|---|---|---|---|---|
| Display (name) | Instrument Serif | 400, italic surname | clamp(64px, 10vw, 128px) / 0.9 | -0.03em |
| Section heading | Instrument Serif | 400 | clamp(40px, 5vw, 64px) / 1 | -0.02em |
| Die block names, project titles | Instrument Serif | 400 | 16–56px | -0.01em |
| Item heading | Geist | 600 | 17–19px / 1.35 | 0 |
| Body | Geist | 400 | 17px / 1.6 | 0 |
| Data (codes, dates, paths, status) | Geist Mono | 500 | 12–13px / 1.4 | 0.06em uppercase for codes |

Google Fonts link:
`https://fonts.googleapis.com/css2?family=Instrument+Serif:ital@0;1&family=Geist:wght@400;500;600&family=Geist+Mono:wght@400;500&display=swap`

Body measure at most 68ch. Headings use `text-wrap: balance`. Numbers in lists use `tabular-nums`.

## 4. Spacing (exact)

Scale: 4 · 8 · 12 · 16 · 24 · 32 · 48 · 64 · 96 px. Nothing off-scale.

- Content max-width 1160px; side gutter `max(16px, env(safe-area-inset-*))`
- Section padding: 96px top/bottom desktop, 64px under 760px
- Heading → content: 32px. Space above a heading is always more than below it
- Index rows: 20px vertical padding, 1px `--line` between
- Buttons: min-height 44px, 0 16px padding, radius 2px, 1px `--line` border, hover border `--pad`

## 5. Imagery

- Real project photos only, from Unmol's Notion pages. No stock photos, no AI images
- Featured projects: image 4:3, `object-fit: cover`, 1px `--line` frame, no radius
- Index rows: 72×54 thumbnail; rows without an image get a 72×54 block-colored pad pattern instead
- Every image has alt text describing what is in the photo

## 6. Motion

Two authored moments only: the boot (power-on log → PCB routes itself → zoom into the chip, at most 2.5s, skippable, once per session, skipped under reduced motion) and the die block morphing into the layout window (view transition). Respect `prefers-reduced-motion`. No scroll-triggered fade-ins.

## 7. Copy

First person, plain, specific. Real numbers from the source (95.24% accuracy, $200K raised). No "passionate", "innovative", "cutting-edge".

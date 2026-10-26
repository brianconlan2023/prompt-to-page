# Manifest Motion

> Category: Themed & Unique

Dark-first, cinematic, premium. Midnight backgrounds, warm off-white type, a single gold accent and a violet glow used sparingly. Source: Manifest Motion spec v1.2 section 4 and app-spec v0.2 M-LIB (25 Oct 2026). Motion timings are PROPOSED (not in the spec).

## Color
| Role | Token | Hex |
|---|---|---|
| Background | --bg | #0B0B10 |
| Surface / Surface-2 | --surface / --surface-warm | #15151D / #1F1F2A |
| Border | --border | #2C2C3A |
| Text / Muted | --fg / --muted | #F4F1EA / #A8A3B3 |
| Accent gold / hover | --accent / --accent-hover | #C9A84C / #E0C26A |
| Secondary violet glow | --meta | #6E56CF |
| Success / Error | --success / --danger | #3FB68B / #E5484D |

Light mode surfaces #FAF8F3 / #FFFFFF, text #14131A. Every text/background pair must pass WCAG AA (4.5:1 body). Gold on #0B0B10 is about 9:1. Alternate palette P2 "Signal Teal" (#F7F7F2 bg, #0FA3A3 accent, #FF6B4A coral) is not packaged yet.

## Typography
Display: Playfair Display. UI/body: DM Sans. Eyebrows, code, token tables: JetBrains Mono (all OFL). Fluid scale: display 40→72px, H2 30→52px, H3 22→30px, body 16→18px, eyebrow 12px uppercase +0.2em.

## Layout
4px spacing base, sections 80→160px, container 1280px (wide 1440px), 12-column grid.

## Motion
Output types (MVP): kinetic typography, title sequences, logo animations, lower thirds, social promos. Aspect ratios 16:9, 9:16, 1:1, 4:5; 5–60 s.
Presets (use tokens, GSAP timelines, paused, HyperFrames-valid):
- fade-up: opacity 0→1, y 24→0, --motion-slow, --ease-enter
- word-stagger: per word, --stagger-word, --ease-enter
- char-stagger: per character, --stagger-char
- mask-reveal: clip-path inset wipe, --motion-scene
- gold-sweep: accent gradient sweep across a title, --motion-scene
- scale-in: scale 0.96→1 + fade, --motion-base
- lower-third-slide: x -40→0 with border accent, --motion-base
- logo-glow: violet --meta glow pulse once, --motion-slow
- exit-fade: opacity 1→0, --motion-base, --ease-exit
Every preset needs a reduced-motion variant (tokens drop to 0ms). Scene durations come from word count; easing chosen per mood. No third-party logos or trademarks.

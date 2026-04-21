# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project

Sanketana School of Code — a premium redesign of sanketana.com. Live 1:1 online coding school for children (ages 8-18) based in Bangalore, serving families across India, Singapore, UAE, and the US.

**Current state:** Single `sanketana.html` file with full homepage design — static HTML/CSS, all styles inline, no build tools. No framework yet.

**Planned migration:** Next.js App Router on Vercel, but design must be finalized in static HTML first.

**Live site (being replaced):** https://www.sanketana.com (WordPress)

## Development

No build step. Open `sanketana.html` directly in a browser to preview. Use `open sanketana.html` or a local server (`python3 -m http.server`).

All CSS is inline in `<style>` within `sanketana.html`. Design tokens are CSS custom properties on `:root` (navy, gold, grey scales + spacing).

## Brand & Design Rules

**The parent is the buyer.** Every design choice must feel like something a sophisticated adult respects. The brand is substantive, confident, warm but authoritative, premium without being pretentious.

**What NOT to do:**
- No playful/childish aesthetics
- No discount language or strikethrough pricing
- No certificates-as-selling-point positioning
- No generic stock photos of smiling kids with tablets

### Creative Direction: Editorial + Art Deco hybrid

- Serif display headlines (Playfair Display) for authority
- Numbered sections (01, 02, 03...) for editorial structure
- Gold accent lines and decorative corner brackets — gold is the spice, not the main course
- Dark navy sections alternating with warm off-white for rhythm
- Subtle film grain overlay (opacity 0.018) and ambient gold glow orbs in dark sections

### Typography

- **Headings:** Playfair Display 500-600, letter-spacing -0.02em
- **Italic emphasis:** Instrument Serif 400 italic (emotional words like "Joy of Coding")
- **Body:** DM Sans 400, line-height 1.6-1.7, max-width 480-520px
- **Labels/eyebrows:** DM Sans 600, 0.75rem, letter-spacing 0.2em, uppercase, gold-600
- **CTAs:** DM Sans 600, 0.85rem, letter-spacing 0.08-0.1em, uppercase

### Color Palette

Three scales defined as CSS custom properties: `--navy-{50-950}`, `--gold-{50-950}`, `--grey-{50-950}`.

- Page background: `hsl(220, 20%, 98%)` / `#f8f9fb`
- Dark sections: navy-950 `#0d1321`
- Primary CTA: gold-500 `#d9a028`
- Body text: grey-700 `#525660`
- Section labels: gold-600 `#b0801e`

### Design Principles

1. Structure first, soul second — fix hierarchy/spacing/type before adding flourishes
2. Emphasize by de-emphasizing — quiet the surroundings rather than adding emphasis
3. Start with too much whitespace, then remove
4. Gold appears on labels, CTAs, decorative lines — never as large surface fills on light sections
5. Dark sections create rhythm — alternating light/dark/light/dark pattern
6. Every card hover should feel like picking up a physical card — lift + shadow increase

### Motion

All transitions use `cubic-bezier(0.22, 1, 0.36, 1)` easing. Cards lift on hover (4px + shadow). CTAs lift 2px + gold glow. Nav links get gold underline from left.

### Responsive

Single breakpoint at 900px: grids collapse to single column, footer to 2-column. Nav links hidden at ≤900px (hamburger menu not yet implemented).

## Known TODOs

- Mobile hamburger menu (nav links hidden at ≤900px but no toggle exists)
- Replace Unsplash placeholder images with actual student project photos
- Scroll-triggered reveal animations (currently only page-load animations)
- SEO metadata, Open Graph tags, favicon
- Accessibility audit (ARIA labels, focus states, skip nav, color contrast)
- WhatsApp chat widget
- Migration plan: break HTML into Next.js components when ready

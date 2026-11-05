# Design System: Curaval Castle Enterprise Platform

## 1. Visual Aesthetics & Philosophy (Inspired by Godly / 21st.dev / Linear)
- Dark-first aesthetic with deep obsidian tones (#04070B, #0A0F18).
- Avoid standard 3-card equal column layouts; use **Asymmetric Bento Grids** with varying spans (col-span-8, col-span-4).
- Ambient interactive background: Dark mesh gradient / WebGL shader combined with the local looping video asset (low opacity 0.35 with backdrop-blur overlay).
- Micro-interactions: Cards feature cursor-following radial border highlights, subtle 3D tilt, and soft elevation on hover.

## 2. Color Palette & Lighting
- Base Void: `#04070D`
- Card Surfaces: `rgba(10, 16, 26, 0.75)` with `backdrop-blur-xl` and border `rgba(255, 255, 255, 0.08)`
- Primary Accent: `#00E5FF` (Neon Medical Cyan)
- Secondary Accent: `#10B981` (Pharma Emerald)
- Muted Text: `#8E9AA8`
- Heading Text: `#F1F5F9`

## 3. Component Architecture
- **Navbar:** Floating liquid pill navbar fixed at top, glassmorphic (`backdrop-blur-md`), shrinking on scroll. Contains brand logo, language toggle (AR/EN), theme toggle, and CTA.
- **Hero:** Deep typography, floating pill status badge with pulsing green light ("24/7 Nationwide Cold Chain Active"), live number counters, and dual CTAs.
- **Bento Showcase (Services & Capabilities):**
  - Card 1 (Large - 8 cols): Cold Chain with live animated temperature display simulator (`3.4°C Optimal`).
  - Card 2 (4 cols): Satellite Fleet Telemetry with animated GPS pulse.
  - Card 3 (4 cols): Smart Warehouse Storage capacity indicator.
  - Card 4 (8 cols): Interactive Governorate distribution map/zones.
- **Form Component:** Clean floating glass inputs, field focus rings in Cyan, and real-time validation.
- **Icons:** Phosphor Icons only (use duotone weight `ph-duotone` for a modern tech feel).

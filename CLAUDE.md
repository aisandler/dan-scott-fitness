# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

Dan Scott Fitness coaching website - a single-page static HTML/CSS/JavaScript site using a **Glass UI glassmorphism design system**. No frameworks, no build tools, no backend.

## Development

**No build step required** - this is a static site.

- Open `website/index.html` directly in a browser to preview
- Deploy to any static host (Vercel, Netlify, GitHub Pages)

## Architecture

```
website/
├── index.html          # Entire site (~1,900 lines) - HTML, CSS, and JS embedded
└── images/
    ├── hero-desktop.jpg
    └── hero-mobile.jpg
```

### Single-File Structure (index.html)

| Section | Lines | Purpose |
|---------|-------|---------|
| CSS Variables | 12-44 | Design tokens (colors, shadows, animations) |
| Styles | 45-700 | All CSS including glass effects, responsive breakpoints |
| Navigation | 710-730 | Fixed glassmorphic header with mobile menu |
| Hero | 732-750 | Full-viewport with background image overlay |
| Content Sections | 752-1100 | About, How It Works, Is/Isn't, Who It's For |
| Application Modal | 1102-1800 | Multi-section intake form (13 field groups) |
| JavaScript | 1815-1880 | Menu toggle, modal management, smooth scroll |

### Design System

**Glass UI Glassmorphism** with:
- Frosted backdrop blur (20px)
- Translucent backgrounds (10-15% opacity)
- Iridescent border animations
- Orange accent color (`#E87A2E`)
- Custom spring easing: `cubic-bezier(0.16, 1, 0.3, 1)`

**Responsive breakpoints**: 1024px, 768px (mobile-first)

### Key CSS Variables

```css
--orange: #E87A2E       /* Primary brand color */
--darker: #0d0d0d       /* Background */
--glass-blur: blur(20px)
--glass-bg: rgba(255, 255, 255, 0.1)
```

## Available Design Skills

The `.claude/skills/` directory contains reusable design system references:
- `glass-ui-system/` - Current design system (glassmorphism)
- `soft-ui-system/` - Alternative premium soft shadows
- `form-patterns/` - Form validation and UX patterns
- `motion-system/` - Animation timing and easing

## Current State

**Working**: Navigation, hero, all content sections, modal open/close, mobile menu

**Not implemented**: Form submission (action="#") - needs backend integration for email notifications

# ClientFlow Pro Landing Page

A premium landing page for an accounting client acquisition SaaS platform ($499/month).

## Overview

ClientFlow Pro is a digital product designed to help accountants with:
- **Lead Generation** - Capture leads from websites, referrals, and marketing campaigns
- **Lead Nurturing** - Automated SMS, email sequences, and follow-up reminders
- **Client Closing** - Proposal builder with e-signatures and tracking
- **Client Onboarding** - Document collection, engagement letters, welcome sequences
- **Client Management** - CRM, communication history, document storage

## Live Preview

Open `accountant-landing.html` in any modern browser.

## Design System

### Typography
- **Headlines:** Playfair Display (serif) - elegant, professional
- **Body:** DM Sans (sans-serif) - clean, modern

### Color Palette

| Color | Hex | Usage |
|-------|-----|-------|
| Background Primary | `#0a0a0b` | Main background |
| Background Secondary | `#111113` | Section backgrounds |
| Gold Accent | `#d4a853` | CTAs, highlights, accents |
| Gold Light | `#e8c77b` | Gradients, hover states |
| Text Primary | `#fafafa` | Headings, body text |
| Text Secondary | `#a1a1aa` | Descriptions, muted text |
| Success | `#22c55e` | Positive metrics, checkmarks |

### Design Features

- **Dark Theme** - Premium, sophisticated aesthetic
- **Ambient Orbs** - Floating gradient backgrounds for depth
- **Noise Texture** - Subtle grain overlay for tactile feel
- **3D Dashboard Preview** - Interactive pipeline visualization
- **Scroll Animations** - Staggered fade-in reveals
- **Hover Effects** - Card lifts, color transitions, glow effects

## Page Sections

1. **Navigation** - Fixed header with logo, links, CTA
2. **Hero** - Value proposition + live dashboard preview
3. **Features** - 6 feature cards with benefits
4. **Process** - 4-step journey visualization
5. **Pricing** - Single $499/month plan with full feature list
6. **Testimonials** - 3 accountant success stories
7. **CTA** - Final conversion section
8. **Footer** - Links and copyright

## Tech Stack

- Pure HTML5 / CSS3 / JavaScript
- No external dependencies (except Google Fonts)
- Fully responsive (mobile, tablet, desktop)
- CSS custom properties for theming
- Intersection Observer API for scroll animations

## Customization

### Changing the Price
Find the pricing section and update:
```html
<span class="price-amount">499</span>
```

### Changing Colors
Modify CSS variables at the top of the `<style>` block:
```css
:root {
    --accent-gold: #d4a853;
    --accent-gold-light: #e8c77b;
    --accent-gold-dark: #b8923f;
}
```

### Adding/Removing Features
Each feature card follows this structure:
```html
<div class="feature-card animate-on-scroll">
    <div class="feature-icon">EMOJI</div>
    <h3 class="feature-title">Title</h3>
    <p class="feature-description">Description</p>
    <ul class="feature-list">
        <li>Benefit 1</li>
        <li>Benefit 2</li>
    </ul>
</div>
```

## Browser Support

- Chrome (latest)
- Firefox (latest)
- Safari (latest)
- Edge (latest)

## File Structure

```
/
├── README.md                 # This file
├── accountant-landing.html   # Main landing page
├── claude.md                 # Claude notes
└── .agent/                   # Antigravity Kit (AI agents/skills)
```

## License

MIT License - Free to use and modify.

---

Built with Antigravity Kit + Claude

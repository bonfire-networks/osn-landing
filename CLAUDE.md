# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

The Open Science Network is a landing page built with Eleventy, TailwindCSS, and DaisyUI.

## Development Commands

```bash
# Development server with live reload
npm run dev           # or pnpm dev

# Production build
npm run build         # or pnpm build

# Package manager
pnpm                  # Project uses pnpm as package manager
```

## Architecture Overview

### Directory Structure
- `src/` - Source files
  - `_includes/` - Reusable templates (base layouts, navigation, components)
  - `_data/` - Global data files (navigation, social media links)
  - `_pages/` - Static pages and special routes
  - `blog/` - Blog posts (Markdown)
  - `asset/` - Static assets (images, CSS source)
- `_site/` - Generated output (git ignored)
- `scripts/` - Build utilities (JS minification)

### Key Configuration
- **eleventy.config.mjs**: Main Eleventy configuration with plugins, collections, filters, and TailwindCSS integration
- **Global data**: Configured in eleventy.config.mjs (site title, URL, quotes, Supabase credentials)
- **Collections**: Automatic collections for `blog` and `photos` with recent post limits
- **Environment**: Uses dotenv for development environment variables

### Content Architecture
- **Blog posts**: Markdown files in `src/blog/` with frontmatter
- **Photo posts**: Markdown files in `src/photos/` with frontmatter containing image metadata
- **Tags**: Automatically collected from blog and photo posts for filtering
- **Navigation**: Configured via JSON files in `src/_data/`

### Build Process
1. TailwindCSS processing via PostCSS (eleventy.before hook)
2. Image lazy loading via eleventy-plugin-lazyimages
3. HTML/CSS/JS minification via @sherby/eleventy-plugin-files-minifier
4. Custom JS minification for additional files

### Key Features
- Responsive design with DaisyUI components
- Lazy image loading with custom plugin configuration
- Comment system integration (Supabase-based)
- Carousel photo galleries
- Tag-based content filtering
- SEO-friendly URL structure

### Development Notes
- Uses ES modules (.mjs) for Eleventy config
- Supports environment variables for Supabase integration
- Custom filters: `limitWords`, `firstCoverImage`
- Use daisyUI and tailwind for css

## Design Implementation

### Target Design
Building a pixel-perfect recreation of the Open Science Network landing page mockup featuring a clean, modern design with scientific branding.

### Main Components Breakdown

#### 1. Header/Navigation
- Clean white background with subtle shadow
- Logo: "Open Science Network" text-based logo (left)
- Navigation menu: Playground, Code, Blog, Support, GitHub icon (right)
- Responsive design with mobile hamburger menu

#### 2. Hero Section - "Reclaim Scientific Discourse"
- Large heading with modern typography
- Subtitle describing federated digital spaces for researchers
- Two-column layout with explanatory text
- Dual CTA buttons: "OPEN SPACES" (primary blue) and "GET STARTED" (secondary)
- Light green info box highlighting ORCID certification
- "Learn more" link with arrow

#### 3. Partner Logos Section
- "In partnership with" heading
- Horizontal logo strip: eLife, Sciety, COAS, ORCID
- Clean spacing and alignment

#### 4. Feature Grid - "Built for Science, Owned by Scientists"
- Section heading with description
- 3x3 grid layout of feature cards:
  - Row 1: Professional Identity, Connected Knowledge, Data Sovereignty
  - Row 2: Transparency, Modular, Social Skill
  - Row 3: (Additional features as shown)
- Each card has icon, title, and description
- Consistent spacing and typography

#### 5. Open Source Section
- Left column: "Open source. No vendor lock-in. Community governed."
- Right column: Profile card with avatar, name, and testimonial quote
- Two-column responsive layout

#### 6. Comparison Table - "Why Open Science Network"
- Feature comparison table
- Left column: Features list
- Right columns: Open Science Network vs competitors
- Green checkmarks for OSN features
- Red X marks for competitor limitations

#### 7. Deployment Section - "Deploy Your Research Community in Minutes"
- 3x3 grid of deployment features
- Each card with icon, title, and description
- Features include SSO integration, GDPR compliance, FAIR data, etc.

#### 8. Risk-Free Trial Section
- "Start Risk-Free" heading
- "Pilot programs available" description
- Data portability guarantee
- Two CTA buttons

#### 9. Testimonials Section
- "What scientists are saying" heading
- Three testimonial cards with avatars, names, titles, and quotes

#### 10. Final CTA Section
- Blue gradient background
- "Ready to build researcher-controlled infrastructure?" heading
- Three action buttons: "Get started", "Book a Demo", "Start Trial"

#### 11. Footer
- Logo and navigation links
- Social media icons
- Contact information

### Design System

#### Colors
- Primary blue: Used for main CTAs and accents
- Light green: For info boxes and highlights
- Gray scale: Various shades for text hierarchy
- White: Primary background
- Blue gradient: For final CTA section

#### Typography
- Clean, modern sans-serif font family
- Clear hierarchy with different font weights and sizes
- Good contrast and readability

#### Spacing & Layout
- Generous white space
- Consistent grid system
- Responsive breakpoints
- Card-based design pattern

#### Components to Build
- Navigation component with responsive menu
- Hero section with dual CTAs
- Info alert/notification box
- Feature cards with icons
- Logo strip/partner section
- Comparison table component
- Testimonial cards
- CTA button variations
- Footer component

### Implementation Priority
1. Base layout and navigation
2. Hero section with CTAs
3. Feature grid system
4. Partner logos section
5. Comparison table
6. Testimonials
7. Final CTA section
8. Footer
9. Responsive refinements
10. Micro-interactions and polish
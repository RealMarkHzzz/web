# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Quick Start

```bash
# Open in browser directly
open index.html

# Or serve locally
python -m http.server 8000
# Then visit http://localhost:8000
```

## Project Overview

**"Family Breakdown & The Secondary Educator"** - An educational website for secondary educators about supporting students experiencing family breakdown.

**Project Details:**
- Student ID: 110359418
- Student Name: Zhe He
- Course: EDUC 5261 Foundations of Learning and Development: A Child Centred Approach

This is a Single-File Application (SFA) with all HTML, CSS, and JavaScript contained in one `index.html` file.

### Architecture

**Single-Page Application (SPA) Structure:**
- All 8 sections are in one HTML file, shown/hidden via JavaScript
- No build process - pure static HTML/CSS/JavaScript
- Navigation system uses `display: none/block` to switch between sections
- IDs: `home`, `prevalence`, `identification`, `brain`, `vulnerability`, `strategies`, `legal`, `resources`

**Key Components:**
- **Navigation**: Desktop sidebar + mobile hamburger menu
- **Content Sections**: 8 educational pages with academic citations
- **Styling**: Tailwind CSS (CDN) + custom embedded CSS
- **Icons**: Lucide Icons (CDN)
- **Fonts**: Google Fonts (Playfair Display, Inter)

### Development Commands

Since this is a static site with no build process:

```bash
# Serve locally (any HTTP server)
python -m http.server 8000
# or
npx serve .

# Open directly in browser (no server needed)
open index.html

# Git operations (permitted via settings)
git pull origin main
git push origin main
```

### File Structure

```
/
├── index.html          # Main application file (ALL code)
├── readme.md           # Project info (Chinese)
├── CLAUDE.md           # This file
└── .claude/
    └── settings.local.json  # Claude Code permissions
```

### Content Management

When editing content:
1. Each section is wrapped in `<section id="section-name" class="page-section hidden fade-in">`
2. Navigation is handled by `navigateTo(sectionId)` function
3. All citations follow APA7 format as inline spans
4. Maintain visual consistency with existing color schemes and layouts

### Styling Guidelines

- Use Tailwind utility classes for most styling
- Custom CSS is embedded in `<style>` tags
- Color scheme by section:
  - Introduction: teal gradients
  - Crisis/Safety: red tones
  - Youth Support: blue tones
  - Legal: green/slate tones
  - Resources: purple/pink tones
- Responsive design with `md:` breakpoint at 768px

### Important Implementation Details

1. **Icon Management**: Lucide icons must be initialized with `lucide.createIcons()` after DOM changes
2. **Active Navigation**: Update both desktop sidebar (`.nav-item`) and mobile menu (`.nav-link`) classes
3. **Scroll Behavior**: Navigation scrolls `.main-container` to top, not window
4. **Mobile Menu**: Auto-close after navigation

### Academic Standards

All content must:
- Include proper APA7 inline citations
- Use provided sources only (AIFS, NSW Government, etc.)
- Maintain academic tone appropriate for secondary educators
- Follow evidence-based practices

### Known Limitations

- Single file can become large (currently ~2700 lines)
- No state management beyond DOM manipulation
- No build optimization or minification
- All dependencies loaded from CDN
- No automated testing framework

### Future Enhancement Possibilities

The project is structured to easily accommodate:
- Addition of npm build process (permissions already configured)
- Migration to React/Vue framework
- PDF export functionality for academic citations
- Interactive assessments or quizzes
- Backend integration for progress tracking
- Automated testing framework integration
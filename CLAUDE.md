# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

This is a static educational website for secondary educators about understanding and supporting students experiencing family breakdown. The project is a standalone HTML/CSS/JavaScript single-page application (SPA) created for a Master of Teaching course assignment.

## Architecture

- **Single File Application**: All code is contained in `index.html` (607 lines)
- **No Build Process**: Pure HTML/CSS/JavaScript with CDN dependencies
- **Technology Stack**:
  - HTML5 with semantic structure
  - Tailwind CSS (via CDN)
  - Vanilla JavaScript for navigation
  - Google Fonts (Playfair Display for headings, Inter for body)
  - Lucide Icons (via CDN)
  - Unsplash for external images

## Website Structure

The SPA has 8 main sections accessed through JavaScript navigation:
1. **Home** - Introduction and overview
2. **Prevalence** - Statistics on family breakdown
3. **Identification** - Signs to watch for in students
4. **Neurobiology** - Brain development impacts
5. **Vulnerability** - Risk factors
6. **Strategies** - Support strategies for educators
7. **Legal** - Legal considerations
8. **Resources** - References and additional resources

## Key Functions

- `navigateTo(sectionId)` - Handles SPA navigation between sections
- `toggleMobileMenu()` - Controls mobile menu visibility
- `lucide.createIcons()` - Initializes Lucide icon system

## Common Development Tasks

### Testing the Website
Since there's no build process:
```bash
# Open directly in browser
open index.html

# Or serve locally (optional)
python3 -m http.server 8000
# Then visit http://localhost:8000
```

### Making Changes
- Edit `index.html` directly
- All CSS is embedded in `<style>` tags in the HTML head
- JavaScript is at the bottom of the HTML file
- No compilation or build steps required

### Adding New Dependencies
- Use CDN links for external libraries
- Add scripts/styles in the `<head>` section
- Currently uses Tailwind CSS, Lucide Icons, and Google Fonts

## Important Implementation Details

### Navigation System
- Uses `display: none/block` to show/hide sections
- Each section has `class="page-section hidden"` initially
- Navigation updates active states and scrolls to top

### Responsive Design
- Mobile-first approach with Tailwind CSS
- Hamburger menu for mobile navigation
- Custom CSS for print media styles

### Content Structure
- Academic focus with citations to Australian Institute of Family Studies
- Includes tables, custom styled boxes, and educational content
- Print-optimized with custom CSS

## Potential Future Enhancements

If adding more complex features:
1. Consider adding a build process (npm scripts)
2. Could migrate to a framework like React/Vue for better state management
3. Currently has permission to use npm for potential Node.js integration
4. Could add interactive quizzes or form submissions
5. PDF export functionality could be valuable for educators

## File Organization

- Root directory: Contains only `index.html`, `.claude/`, and potential future assets
- No subdirectories currently
- All styles and scripts are embedded in the HTML file
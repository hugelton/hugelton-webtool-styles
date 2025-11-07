# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

**Shari** is a CSS framework designed specifically for web editor tools, with a focus on Web MIDI API and Serial API applications. It provides a comprehensive component library with a minimalist design philosophy.

## Development Commands

### Build & Development
```bash
npm install      # Install dependencies (sass)
npm run dev      # Watch mode - compiles SCSS to expanded CSS on file changes
npm run build    # Production build - creates both expanded and minified CSS
npm run preview  # Start local HTTP server on http://127.0.0.1:8080
npm run watch    # Alias for dev
npm run serve    # Alias for preview
```

### Output Files
- **dist/shari.css** - Expanded CSS for development
- **dist/shari.min.css** - Minified CSS for production

## Architecture

### File Structure
The project uses a monolithic architecture with all styles in a single SCSS file:
- **src/main.scss** - Single source file containing all framework code
- **docs/index.html** - Documentation site with interactive component examples
- **dist/** - Compiled CSS output (not committed to repo)

### Why Monolithic?
This framework intentionally uses a single SCSS file rather than modular imports. This design choice prioritizes:
- Easy browsing and searching within a single file
- Quick understanding of the entire framework
- Simple maintenance for a focused, domain-specific CSS library

## Design System

### Fibonacci Spacing System
The framework uses Fibonacci sequence for spacing (0, 1, 1, 2, 3, 5, 8, 13 rem):
- CSS variables: `--fib-0` through `--fib-7`
- Utility classes: `.m-{0-5}`, `.p-{0-5}`, `.gap-{0-5}`
- Base font size: 18px (1rem = 18px)

### Color Palette
Four main colors with inverted variants for theming:
- **Green** (`--color-green`): #036eb7 / Invert: #fc9148
- **Yellow** (`--color-yellow`): #009844 / Invert: #ff67bb
- **Orange** (`--color-red`): #f29600 / Invert: #0d69ff
- **Red** (`--color-blue`): #c30d23 / Invert: #3cf2dc

Note: Color names are intentionally swapped (e.g., `--color-blue` is red) for design reasons.

### Theme System
- Light mode: Default `:root` variables
- Dark mode: `[data-theme="dark"]` attribute on body
- All components automatically adapt to theme changes
- Theme toggle implementation in preview.html

### Grid System
Two types of grid layouts:

**Square Grids**: Equal width/height with 1:1 aspect ratio
- `.grid-1x1` through `.grid-5x5`
- Use `.grid-item-square` for children to maintain aspect ratio

**Fibonacci Ratio Grids**: Golden ratio-inspired layouts
- `.grid-fib-1x1`, `.grid-fib-2x1`, `.grid-fib-3x2`, `.grid-fib-5x3`, `.grid-fib-8x5`
- Automatically calculate aspect ratios based on Fibonacci proportions

### Typography
- **Headings**: Inter Tight (h2-h6) and Clash Display (h1)
- **Body**: Inter Tight, 18px base size, 1.6 line height
- Loaded via Google Fonts CDN

## Component Library (20+ Components)

### Form Components
- `.button` - Pill-shaped buttons with variants (danger, warning, success, info)
- `.textfield` - Input fields with focus states
- `.toggle` - iOS-style toggle switches
- `.checkbox` - Custom checkbox with animations
- `.radio` - Custom radio buttons
- `.dropdown` - Custom select/dropdown with menu
- `.fader` - Range slider/fader control

### Layout Components
- `.panel` - Rounded containers with theme-aware backgrounds
- `.grid` - Grid system (see Grid System section)
- `.flex`, `.flex-column`, `.flex-center`, `.flex-between` - Flexbox utilities
- `.float-menu` - Glassmorphic floating menu bar (Shari style)
- `.header` - Sticky/fixed header component

### Status & Feedback
- `.status` - Status labels (online, offline, warning, info, neutral)
- `.badge` / `.chip` - Tags and removable chips
- `.alert` - Notification banners with variants
- `.progress` / `.progress-bar` - Progress indicators
- `.spinner` / `.dots-loading` - Loading animations
- `.tooltip` - Hover tooltips with directional variants

### Overlays
- `.modal` - Modal dialogs with backdrop blur
- `.loading-overlay` - Full-screen loading state

### Data Display
- `.table` - Styled tables with striped variant

## Key Implementation Details

### Glassmorphic Float Menu
The `.float-menu` component uses:
- `backdrop-filter: blur(20px)` for glass effect
- Fixed positioning at top-left
- Theme-aware background: `rgba(255,255,255,0.1)` in light, `rgba(0,0,0,0.2)` in dark
- Fade-in slide animation on load

### Component Interactions
Many components require JavaScript for full functionality:
- Modals: Toggle `.modal-open` class
- Dropdowns: Toggle `.dropdown-open` class
- Theme: Set `[data-theme="dark"]` on body
- Tooltips: Pure CSS with `:hover` states

See docs/index.html for reference implementations and interactive examples.

## Making Changes

### Adding New Components
1. Add styles to src/main.scss (append to end or logical grouping)
2. Follow existing naming conventions (lowercase, hyphenated)
3. Include theme variants for dark mode when color-dependent
4. Run `npm run build` to compile
5. Test in docs/index.html

### Modifying Colors or Spacing
1. Update CSS variables in `:root` and `[data-theme="dark"]` sections
2. Fibonacci spacing variables are at line ~220
3. Color palette at lines ~16-40
4. Rebuild after changes

### Testing Changes
1. Run `npm run dev` for watch mode during development
2. Run `npm run preview` and open http://127.0.0.1:8080/docs/ in browser
3. Test both light and dark themes using the toggle
4. Check responsive behavior and component interactions

## Browser Compatibility

Designed for modern browsers with support for:
- CSS Grid and Flexbox
- CSS Custom Properties (variables)
- `backdrop-filter` (for glassmorphic effects)
- Web MIDI API / Serial API (for target applications)

## Production Usage

Include the compiled CSS in your HTML:
```html
<link rel="stylesheet" href="dist/shari.min.css">
```

For development/debugging, use the expanded version:
```html
<link rel="stylesheet" href="dist/shari.css">
```

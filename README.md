# Shari

A lightweight CSS framework designed specifically for web editor tools, with a focus on Web MIDI API and Serial API applications. Features 20+ components with a minimalist design philosophy and Fibonacci-based spacing system.

[![Version](https://img.shields.io/badge/version-1.0.0-blue.svg)](https://github.com/hugelton/shari)
[![License](https://img.shields.io/badge/license-MIT-green.svg)](LICENSE)
[![Size](https://img.shields.io/badge/size-~12KB-orange.svg)](dist/)

## Features

- 🎨 **20+ Components** - Buttons, forms, modals, grids, and more
- 🌓 **Dark Mode** - Built-in theme switching with smooth transitions
- 📐 **Fibonacci Spacing** - Mathematical spacing system (0, 1, 1, 2, 3, 5, 8, 13)
- 🎯 **Web MIDI Focused** - Optimized for music and audio applications
- 🪶 **Lightweight** - Only ~12KB minified
- 🎭 **Glassmorphic UI** - Modern blur effects and floating menus
- 📱 **Responsive** - Mobile-first design approach

## Installation

### CDN (Recommended)

```html
<!-- Minified CSS (Production) -->
<link rel="stylesheet" href="https://cdn.jsdelivr.net/gh/hugelton/shari@main/dist/shari.min.css">

<!-- or unpkg -->
<link rel="stylesheet" href="https://unpkg.com/shari@latest/dist/shari.min.css">

<!-- Expanded CSS (Development) -->
<link rel="stylesheet" href="https://cdn.jsdelivr.net/gh/hugelton/shari@main/dist/shari.css">
```

### npm

```bash
npm install shari
```

Then import in your HTML:

```html
<link rel="stylesheet" href="node_modules/shari/dist/shari.min.css">
```

### Download

Download the latest release from the [releases page](https://github.com/hugelton/shari/releases) and include it in your project:

```html
<link rel="stylesheet" href="path/to/shari.min.css">
```

## Quick Start

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>My Web MIDI App</title>
    <link rel="stylesheet" href="https://cdn.jsdelivr.net/gh/hugelton/shari@main/dist/shari.min.css">
</head>
<body>
    <div class="p-3">
        <h1>My MIDI Controller</h1>
        <div class="panel">
            <button class="button success">Connect Device</button>
        </div>
    </div>
</body>
</html>
```

## Components

### Buttons

```html
<button class="button">Default Button</button>
<button class="button success">Success</button>
<button class="button warning">Warning</button>
<button class="button danger">Danger</button>
<button class="button info">Info</button>
```

### Forms

```html
<!-- Text Input -->
<input type="text" class="textfield" placeholder="Device name">

<!-- Toggle Switch -->
<label class="toggle">
    <input type="checkbox">
    <span class="toggle-slider"></span>
</label>

<!-- Checkbox -->
<label class="checkbox">
    <input type="checkbox">
    <span class="checkbox-mark"></span>
    Enable feature
</label>

<!-- Radio -->
<label class="radio">
    <input type="radio" name="channel">
    <span class="radio-mark"></span>
    Channel 1
</label>

<!-- Dropdown -->
<div class="dropdown">
    <button class="dropdown-button">Select Device</button>
    <div class="dropdown-menu">
        <div class="dropdown-item">Device 1</div>
        <div class="dropdown-item selected">Device 2</div>
    </div>
</div>

<!-- Fader/Slider -->
<input type="range" class="fader" min="0" max="100" value="50">
```

### Layout

```html
<!-- Panel -->
<div class="panel">
    <h2>Panel Title</h2>
    <p>Panel content</p>
</div>

<!-- Flex Utilities -->
<div class="flex gap-2">
    <div>Item 1</div>
    <div>Item 2</div>
</div>

<div class="flex-column gap-3">
    <div>Vertical Item 1</div>
    <div>Vertical Item 2</div>
</div>

<div class="flex-between">
    <span>Label</span>
    <span>Value</span>
</div>

<!-- Grid System -->
<div class="grid grid-3x3 gap-1">
    <div class="grid-item-square">1</div>
    <div class="grid-item-square">2</div>
    <div class="grid-item-square">3</div>
    <!-- ... -->
</div>

<!-- Fibonacci Ratio Grids -->
<div class="grid grid-fib-5x3 gap-2">
    <div>Golden ratio content</div>
</div>
```

### Status & Feedback

```html
<!-- Status Labels -->
<span class="status status-online">Connected</span>
<span class="status status-offline">Disconnected</span>
<span class="status status-warning">Limited</span>
<span class="status status-info">Info</span>
<span class="status status-neutral">Idle</span>

<!-- Badges -->
<span class="badge">Default</span>
<span class="badge badge-primary">Primary</span>
<span class="badge badge-success">Success</span>

<!-- Chips -->
<div class="chip chip-removable">
    Tag Name
    <button class="chip-remove">×</button>
</div>

<!-- Progress Bar -->
<div class="progress">
    <div class="progress-bar" style="width: 60%;"></div>
</div>

<!-- Spinner -->
<div class="spinner"></div>

<!-- Dots Loading -->
<div class="dots-loading">
    <div class="dot"></div>
    <div class="dot"></div>
    <div class="dot"></div>
</div>
```

### Alerts

```html
<div class="alert alert-info">
    <button class="alert-close">×</button>
    <div class="alert-title">Information</div>
    This is an info message.
</div>

<div class="alert alert-success">Success message</div>
<div class="alert alert-warning">Warning message</div>
<div class="alert alert-danger">Error message</div>
```

### Modal

```html
<div class="modal" id="my-modal">
    <div class="modal-content">
        <div class="modal-header">
            <h2>Modal Title</h2>
            <button class="modal-close">×</button>
        </div>
        <div class="modal-body">
            <p>Modal content goes here</p>
        </div>
        <div class="modal-footer">
            <button class="button">Cancel</button>
            <button class="button success">Confirm</button>
        </div>
    </div>
</div>

<script>
const modal = document.getElementById('my-modal');
modal.classList.add('modal-open'); // Show modal
modal.classList.remove('modal-open'); // Hide modal
</script>
```

### Float Menu (Glassmorphic)

```html
<div class="float-menu">
    <div class="menu-container">
        <a href="#" class="menu-logo">Logo</a>
        <div class="menu-nav">
            <a href="#" class="menu-link">Link 1</a>
            <a href="#" class="menu-link">Link 2</a>
        </div>
    </div>
</div>
```

### Tables

```html
<table class="table table-striped">
    <thead>
        <tr>
            <th>Device</th>
            <th>Status</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>Device 1</td>
            <td><span class="status status-online">Connected</span></td>
        </tr>
    </tbody>
</table>
```

## Theme System

### Dark Mode

Toggle dark mode by setting the `data-theme` attribute on the body:

```javascript
// Enable dark mode
document.body.setAttribute('data-theme', 'dark');

// Disable dark mode (back to light)
document.body.removeAttribute('data-theme');

// Save preference
localStorage.setItem('theme', 'dark');
```

### Color Palette

The framework uses four main colors with intentionally swapped names:

- `--color-green`: #036eb7 (Blue in light mode)
- `--color-yellow`: #009844 (Green in light mode)
- `--color-red`: #f29600 (Orange in light mode)
- `--color-blue`: #c30d23 (Red in light mode)

Colors automatically invert in dark mode for optimal contrast.

## Spacing System

Based on the Fibonacci sequence (0, 1, 1, 2, 3, 5, 8, 13):

```scss
--fib-0: 0rem    // 0px
--fib-1: 1rem    // 18px
--fib-2: 1rem    // 18px
--fib-3: 2rem    // 36px
--fib-4: 3rem    // 54px
--fib-5: 5rem    // 90px
--fib-6: 8rem    // 144px
--fib-7: 13rem   // 234px
```

### Utility Classes

```html
<!-- Margin -->
<div class="m-0">No margin</div>
<div class="m-1">1rem margin</div>
<div class="m-3">2rem margin</div>

<!-- Padding -->
<div class="p-0">No padding</div>
<div class="p-2">1rem padding</div>
<div class="p-5">5rem padding</div>

<!-- Gap (for flex/grid) -->
<div class="flex gap-1">18px gap</div>
<div class="grid gap-3">36px gap</div>
```

## Typography

- **Base Size**: 18px (1rem)
- **Headings**: Inter Tight (h2-h6), Clash Display (h1)
- **Body**: Inter Tight, line-height 1.6

Fonts are loaded from Google Fonts CDN:

```html
<link rel="preconnect" href="https://fonts.googleapis.com">
<link href="https://fonts.googleapis.com/css2?family=Inter+Tight:wght@100..900&display=swap" rel="stylesheet">
```

## Browser Support

Requires modern browsers with support for:
- CSS Grid and Flexbox
- CSS Custom Properties (variables)
- `backdrop-filter` (for glassmorphic effects)
- Web MIDI API / Serial API (for target applications)

## Development

```bash
# Install dependencies
npm install

# Development (watch mode)
npm run dev

# Build for production
npm run build

# Preview locally
npm run preview
```

## Examples

Check out the [interactive demo](preview.html) to see all components in action.

## License

MIT License - see [LICENSE](LICENSE) file for details

## Contributing

Contributions are welcome! Please feel free to submit a Pull Request.

## Credits
made by Hügelton Instruments. Kobe Japan.

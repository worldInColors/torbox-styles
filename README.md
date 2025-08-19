# TorBox Styles Collection

A collection of beautiful themes for TorBox dashboard, offering multiple color schemes and aesthetics. Transform your torrenting dashboard into a modern, eye-friendly interface with cohesive colors and interactive effects.

## Available Themes

| Theme                 | Description                                            | Preview                              | Install                                                                                                                                                     |
| --------------------- | ------------------------------------------------------ | ------------------------------------ | ----------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Dark Blue**         | Dark theme with blue accents                           | ![Preview](previews/dark-blue.png)   | [![Install](https://img.shields.io/badge/Install-Stylus-blue)](https://github.com/worldInColors/torbox-styles/raw/main/styles/torbox-dark-blue.user.css)    |
| **Catppuccin**        | Soft pastel theme inspired by Catppuccin color palette | ![Preview](previews/catppuccin.png)  | [![Install](https://img.shields.io/badge/Install-Stylus-purple)](https://github.com/worldInColors/torbox-styles/raw/main/styles/torbox-catppuccin.user.css) |
| **Amber**             | Warm amber theme with golden accents                   | ![Preview](previews/amber.png)       | [![Install](https://img.shields.io/badge/Install-Stylus-orange)](https://github.com/worldInColors/torbox-styles/raw/main/styles/torbox-amber.user.css)      |
| **Light**             | Clean light theme for daytime usage                    | ![Preview](previews/light.png)       | [![Install](https://img.shields.io/badge/Install-Stylus-lightblue)](https://github.com/worldInColors/torbox-styles/raw/main/styles/torbox-light.user.css)   |
| **Torbox But Better** | My personal favourite: RealDebrid                      | ![Preview](previews/real-debrid.png) | [![Install](https://img.shields.io/badge/Install-Stylus-green)](https://github.com/worldInColors/torbox-styles/raw/main/styles/torbox-but-better.user.css)  |

<br />

## Quick Installation

### One-Click Install (Recommended)

1. Install [Stylus](https://github.com/openstyles/stylus) browser extension
2. Click any "Install" button above for your preferred theme
3. Stylus will automatically open with the theme ready to install
4. Click "Install style" and you're done!

### Manual Installation

1. Install [Stylus](https://github.com/openstyles/stylus) or Stylish browser extension
2. Browse the [styles folder](./styles/) and choose your theme
3. Copy the CSS content and create a new style in your extension
4. Set the URL to apply to: `https://torbox.app/*`
5. Save and enjoy!

<br />

## Common Features

All themes include:

- **Complete dashboard theming** for the entire TorBox interface
- **Status-aware coloring** - different colors for active, cached, private, and ready downloads
- **Interactive hover effects** - subtle animations and visual feedback
- **Custom badge styling** - clearly distinguished torrent types and statuses
- **Consistent typography** - proper text hierarchy with optimized readability
- **Mobile-friendly** - responsive design that works on all devices

<br />

## Theme Examples

Here's a preview of the Dark Blue theme (the original):

### Dark Blue Theme CSS

```css
/* ==UserStyle==
@name           Torbox Dark Blue Theme
@namespace      github.com/openstyles/stylus
@version        1.0.0
@description    Dark theme for TorBox dashboard inspired by monkeytype
@author         Me
==/UserStyle== */

@-moz-document url-prefix("https://torbox.app")
{
  /* ===== VARIABLES ===== */
  * {
    /* Backgrounds */
    --color-bg: #22313f; /* main background */
    --color-bg-alt: #34495e; /* secondary background */
    --color-surface: #2c2e31; /* panels, cards, etc. */

    /* Text */
    --color-text: #d1d0c5; /* main text */
    --color-text-sub: #e4f1fe; /* lighter text, subtitles */
    --color-text-muted: #95a5a6; /* muted/secondary text */

    /* Accent & Interactive */
    --color-accent: #8dc6ff; /* caret, highlights */
    --color-accent-hover: #a8d3ff; /* hover states */
    --color-accent-dark: #5dade2; /* darker accent variant */

    /* Status Colors */
    --color-success: #27ae60; /* green for active/ready states */
    --color-success-bg: #1e8449; /* darker green for backgrounds */
    --color-warning: #f39c12; /* orange/yellow for warnings */
    --color-warning-bg: #d68910; /* darker orange */
    --color-error: #ca4754; /* red for errors */
    --color-error-dark: #7e2a33; /* darker red */

    /* UI Elements */
    --color-border: #40566d; /* borders, dividers */
    --color-border-light: #52708a; /* lighter borders */
    --color-input: #2c3e50; /* input fields */
    --color-input-focus: #34495e; /* focused inputs */

    /* Special Elements */
    --color-badge: #3498db; /* badges, tags */
    --color-badge-private: #9b59b6; /* private torrents */
    --color-cached: #17a2b8; /* cached downloads */
    --color-progress: #2ecc71; /* progress bars */
    --color-graph: #16a085; /* charts/graphs */
  }

  /* ===== ROOT STYLING ===== */
  #root {
    background: var(--color-bg) !important;
    color: var(--color-text) !important;
  }

  /* ===== ICONS ===== */
  .fill-white,
  .text-white {
    fill: var(--color-accent) !important;
    color: var(--color-accent) !important;
  }

  /* ===== LAYOUT CONTAINERS ===== */
  .sidebar,
  .downloads {
    background-color: var(--color-bg-alt) !important;
  }

  .downloads .sticky {
    background-color: var(--color-bg-alt) !important;
    border-bottom: 1px solid var(--color-border) !important;
  }

  /* ===== HEADER STATISTICS ===== */
  .downloads .sticky .flex > div:last-child span {
    color: var(--color-error-dark) !important; /* inactive downloads */
  }

  .downloads .sticky .flex > div:first-child span {
    color: var(--color-success) !important; /* active downloads */
  }

  .downloads .sticky .flex > div:nth-child(2) span {
    color: var(--color-accent) !important; /* total downloads */
  }

  /* ===== DOWNLOAD CARDS ===== */
  [id^="headlessui-popover-button"] {
    background-color: var(--color-surface) !important;
    border: 1px solid var(--color-border) !important;
  }

  /* ===== STATUS BADGES ===== */
  .flex.flex-wrap.gap-3.items-center p.bg-gray-500 {
    background-color: var(--color-badge) !important; /* torrent */
  }

  .flex.flex-wrap.gap-3.items-center p.bg-indigo-500 {
    background-color: var(--color-badge-private) !important; /* private */
  }

  .flex.flex-wrap.gap-3.items-center p.bg-\[\#04BF8A\] {
    background-color: var(--color-success) !important; /* download ready */
  }

  .flex.flex-wrap.gap-3.items-center p.bg-blue-500 {
    background-color: var(--color-cached) !important; /* cached */
  }

  /* ===== ACTION BUTTONS ===== */
  button.rounded-md.font-bold {
    background: none !important;
    background-color: var(--color-success-bg) !important;
  }

  button.rounded-md.font-bold:hover {
    background-color: var(--color-success) !important;
  }

  /* ===== PLAN EXPIRATION ===== */
  /* Get More Time button */
  a.rounded-md.p-2.w-full.bg-red-500 {
    background-color: var(--color-error) !important;
  }

  a.rounded-md.p-2.w-full.bg-red-500:hover {
    background-color: var(--color-error-dark) !important;
  }

  /* Hide yellow button */
  .bg-\[\#F59E0B\] {
    display: none !important;
  }

  /* ===== OPTIONAL EFFECTS ===== */
  /* Blur effect on download titles */
  [id^="headlessui-popover-button"] p.text-lg {
    filter: blur(0);
    transition: filter 0.3s;
    transition-delay: 2s;
  }

  [id^="headlessui-popover-button"]:hover p.text-lg {
    filter: blur(4px);
    transition-delay: 1s;
  }
}
```

<br />

## Creating Custom Themes

Want to create your own theme or modify an existing one? Each theme uses CSS variables for easy customization:

```css
/* Example: Customizing the Dark Blue theme */
* {
  /* Change the accent color (used for icons and highlights) */
  --color-accent: #ff6b6b; /* Red accent instead of blue */

  /* Adjust background darkness */
  --color-bg: #2c3e50; /* Lighter background */
  --color-bg-alt: #3c5a78; /* Lighter secondary */

  /* Modify badge colors */
  --color-cached: #1abc9c; /* More green for cached */
  --color-badge-private: #e74c3c; /* Red for private */
}
```

### Color Palette Examples

Each theme has its unique color scheme:

- **Dark Blue**: Dark blues and grays
- **Catppuccin**: Soft pastels from the Catppuccin palette
- **Amber**: Warm golds and oranges
- **Light**: Clean whites and light blues
- **Torbox But Better**: RealDebrid

<br />

## Optional Features

### Blur Effect on Hover

Blur titles after 2 seconds of hovering:

Uncomment these lines

```css
/* Blur effect on download titles */
/* [id^="headlessui-popover-button"] p.text-lg {
    filter: blur(0);
    transition: filter 0.3s;
    transition-delay: 2s;
  }

  [id^="headlessui-popover-button"]:hover p.text-lg {
    filter: blur(4px);
    transition-delay: 1s;
  } */
```

### Hide the sidebar

Uncomment these lines

```css
/* Hide sidebar */

/* main {
    grid-template-columns: none !important;
  }

  div.relative.sidebar {
    display: none;
  } */
```

### Hide Specific UI Elements

Hide or show UI elements, like the "Explore Addons" or "Get Extra Time" buttons:

Uncomment these lines

```css
/* hide addons button */
/* a.rounded-md.p-2.w-full.bg-\[\#F59E0B\] {
        display: none !important;
    } */
```

<br />

## Troubleshooting

**Theme not applying?**

- Make sure you're on `https://torbox.app/*` (themes work on all TorBox pages)
- Clear browser cache and refresh the page
- Check that your browser extension is enabled and the style is active

**Some elements not themed?**

- TorBox may have updated their CSS classes
- Try a different theme to see if it's theme-specific
- Right-click the element, inspect, and note the class names
- Open an issue with the details and screenshots

**Canvas graph still showing original colors?**

- Canvas elements can't be styled with CSS
- This is a known limitation - the graph colors are hardcoded in JavaScript

**Install button not working?**

- Make sure you have Stylus installed and enabled
- Try right-clicking the install link and selecting "Save link as" to download manually
- You can then import the .css file into Stylus

<br />

## Compatibility

- **Tested on:** Chrome, Firefox, Edge, Safari
- **TorBox Version:** Compatible with current version (August 2025)
- **Browser Extensions:** Stylus (recommended), Stylish, and other UserCSS-compatible extensions

<br />

## Contributing

Found an unthemed element, want to suggest improvements, or create a new theme? We'd love your help:

- **Report Issues:** Open an issue with screenshots and browser details
- **Submit Themes:** Create a pull request with your new theme in the `styles/` folder
- **Share Customizations:** Show off your color modifications in discussions
- **Suggest Features:** Request new themes or improvements

### Adding a New Theme

1. Fork the repository
2. Create a new `.user.css` file in the `styles/` folder
3. Follow the existing naming convention: `torbox-[theme-name].user.css`
4. Include proper UserCSS metadata at the top
5. Update this README with your theme in the table
6. Submit a pull request

<br />

## Acknowledgments

- Original Dark Blue theme inspired by [monkeytype.com](https://monkeytype.com)
- Catppuccin theme uses colors from the [Catppuccin](https://github.com/catppuccin/catppuccin) project
- Thanks to all contributors and theme creators

<br />

---

_Transform your TorBox experience with beautiful, functional themes._

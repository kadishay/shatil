# Shatil Photo Presentation

A web-based photo presentation system for Shatil, featuring an interactive slideshow and a dynamic falling photos animation. Built with vanilla HTML, CSS, and JavaScript - no dependencies required.

## Project Overview

This project displays a curated collection of photos in two modes:
1. **Presentation Mode**: A traditional slideshow for guided viewing
2. **Animation Mode**: Photos fall like polaroids onto a surface, creating an engaging visual experience

The photos are numbered (01-69) in a specific display order for the presentation, while the animation includes additional photos from the `More/` folder for variety.

## Files Structure

```
Shatil/
├── presentation.html      # Main slideshow viewer
├── animation.html         # Falling photos animation
├── manage.html           # Management interface
├── README.md             # This file
├── 01-69_*.jpeg/png/jpg  # Ordered presentation photos
└── More/                 # Additional photos for animation
    └── *.jpeg            # 72 extra photos
```

## Features

### Presentation (`presentation.html`)

The main slideshow displays 69 photos in a curated order.

**Controls:**
| Input | Action |
|-------|--------|
| `→` `↓` `Space` | Next slide |
| `←` `↑` | Previous slide |
| `Home` | First slide |
| `End` | Last slide |
| `F` | Toggle fullscreen |
| `Esc` | Exit animation mode |
| Swipe left/right | Navigate (touch devices) |

**Features:**
- Progress bar showing current position
- Remembers last viewed slide (localStorage)
- Auto-refresh every 30 seconds to pick up changes
- Links to animation and management pages

### Animation (`animation.html`)

Displays 141 photos (69 main + 72 from More/) falling like polaroids.

**How Photos Are Displayed:**
1. **Shuffle**: All 141 photos are shuffled randomly at startup
2. **Falling**: Every 2.5 seconds, a new photo falls from the top
3. **Random placement**: Each photo gets randomized:
   - Horizontal position: 1-85% from left edge
   - Landing position: 15-65% from top
   - Rotation angles: -45° to +45° (start/mid/end)
   - Fall duration: 2.5-3.3 seconds
4. **Max on screen**: 25 photos visible at once; older ones fade out
5. **Loop**: When all photos shown, reshuffles and repeats

**Visual Style:**
- Polaroid-style white frames with shadow
- Subtle ambient lighting effect
- Photos maintain original aspect ratio (max 500x400px)

## Image Naming Convention

Main folder images use numbered prefixes to control presentation order:
```
01_Logo Green.avif          # First slide
02_WhatsApp Image...jpeg    # Second slide
...
69_WhatsApp Image...jpeg    # Last slide
```

## Usage

1. Open `presentation.html` in any modern browser
2. Use arrow keys or click buttons to navigate
3. Click ▶ button to open the falling animation
4. Click ⚙ button to open management interface

## Technical Notes

- Pure HTML/CSS/JavaScript - no build process or dependencies
- Uses localStorage to persist:
  - Current slide position in presentation
- Photos loaded directly from filesystem (works with `file://` protocol)
- Responsive design works on desktop and mobile

## For Claude

When working with this project:
- **Adding photos**: Add to main folder with numbered prefix (e.g., `70_newphoto.jpeg`) and update `presentation.html` slides + `animation.html` defaultImages array
- **Reordering**: Use `image-reorder-editor.html` (excluded from git) to visually reorder, then rename files and update HTML references
- **Presentation changes**: Edit the `<div class="slide">` elements in `presentation.html`
- **Animation changes**: Edit the `defaultImages` array in `animation.html`

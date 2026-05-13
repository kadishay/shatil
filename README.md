# Shatil Photo Presentation

A web-based photo presentation system for Shatil, featuring an interactive slideshow and a dynamic falling photos animation. Built with vanilla HTML, CSS, and JavaScript - no dependencies required.

## Project Overview

This project displays a curated collection of photos in two modes:
1. **Presentation Mode**: A traditional slideshow for guided viewing
2. **Animation Mode**: Photos fall like polaroids onto a surface, creating an engaging visual experience

The photos are organized into two folders:
- `Base/`: 68 images used in the main presentation
- `More/`: 162 additional images used only in the animation for variety

## Files Structure

```
Shatil/
├── presentation.html      # Main slideshow viewer
├── animation.html         # Falling photos animation
├── manage.html           # Management interface
├── README.md             # This file
├── Base/                 # Main presentation photos (68 images)
│   └── Shatil_Base_001-068.*  # Numbered photos
└── More/                 # Additional photos for animation (162 images)
    └── Shatil_More_001-163.*  # Numbered photos
```

## Features

### Presentation (`presentation.html`)

The main slideshow displays 68 photos from the `Base/` folder in a curated order.

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

Displays 230 photos (68 from Base/ + 162 from More/) falling like polaroids.

**How Photos Are Displayed:**
1. **Shuffle**: All 230 photos are shuffled randomly at startup
2. **Falling**: Every 2 seconds (configurable), a new photo falls from the top
3. **Random placement**: Each photo gets randomized:
   - Horizontal position: -5% to 90% from left edge
   - Landing position: 5% to 80% from top
   - Rotation angles: -45° to +45° (start/mid/end)
   - Fall duration: 2.5-3.3 seconds
4. **Max on screen**: 25 photos visible at once; older ones fade out
5. **Loop**: When all photos shown, reshuffles and repeats

**URL Parameters:**
- `?speed=2000` - Control fall interval in milliseconds (default: 2000ms)

**Visual Style:**
- Polaroid-style frames with realistic aging effects (cream tones, subtle stains)
- Multi-layered shadows for depth
- Subtle sepia filter on photos
- Green-to-brown gradient background
- Logo title with white glow effect
- Photos maintain original aspect ratio (max 500x400px)

### Management (`manage.html`)

Drag-and-drop interface for reordering presentation photos.

## Image Naming Convention

All images follow a consistent naming format:

**Base folder:**
```
Base/Shatil_Base_001.avif    # First slide (logo)
Base/Shatil_Base_002.jpeg    # Second slide
...
Base/Shatil_Base_068.jpeg    # Last slide
```

**More folder:**
```
More/Shatil_More_001.jpeg    # First extra photo
More/Shatil_More_002.jpeg    # Second extra photo
...
More/Shatil_More_163.jpeg    # Last extra photo
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
- **Adding Base photos**: Add as `Base/Shatil_Base_XXX.jpeg` (next number after 068), update `presentation.html` slides + `animation.html` defaultImages array
- **Adding More photos**: Add as `More/Shatil_More_XXX.jpeg` (next number after 163), update `animation.html` defaultImages array
- **Reordering**: Use `image-reorder-editor.html` (excluded from git) to visually reorder, then rename files and update HTML references
- **Presentation changes**: Edit the `<div class="slide">` elements in `presentation.html` - all paths start with `Base/Shatil_Base_`
- **Animation changes**: Edit the `defaultImages` array in `animation.html` - Base images use `Base/Shatil_Base_` prefix, More images use `More/Shatil_More_` prefix
- **Folder structure**: Main presentation images are in `Base/`, additional animation-only images are in `More/`

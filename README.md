# Shatil Photo Presentation

A web-based photo presentation and animation system for displaying the Shatil photo collection.

## Files

| File | Description |
|------|-------------|
| `presentation.html` | Main slideshow with keyboard/touch navigation |
| `animation.html` | Falling photos animation effect |
| `image-reorder-editor.html` | Drag-and-drop tool for reordering images |
| `manage.html` | Management interface |

## Features

### Presentation (`presentation.html`)
- Full-screen slideshow with 69 ordered photos
- Keyboard navigation (arrow keys, space, Home/End)
- Touch/swipe support for mobile
- Progress bar indicator
- Remembers last viewed slide (localStorage)
- Fullscreen mode (press F or click button)

### Animation (`animation.html`)
- 141 photos falling with randomized positions and rotations
- Polaroid-style photo frames
- Shuffled playback order
- Ambient lighting effects

### Image Reorder Editor (`image-reorder-editor.html`)
- Visual drag-and-drop interface
- Generates ordered list for renaming files
- Dark theme UI

## Image Organization

Images are stored in two locations:
- **Main folder**: 69 numbered images (01-69) in presentation order
- **More/ folder**: Additional 72 images for the animation

## Usage

1. Open `presentation.html` in a browser for the slideshow
2. Click the play button to open the animation
3. Use `image-reorder-editor.html` to reorder images visually

## Navigation Controls

| Key | Action |
|-----|--------|
| `→` `↓` `Space` | Next slide |
| `←` `↑` | Previous slide |
| `Home` | First slide |
| `End` | Last slide |
| `F` | Toggle fullscreen |
| `Esc` | Exit animation mode |

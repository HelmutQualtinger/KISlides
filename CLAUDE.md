# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

KISlides is a collection of HTML-based slideshow presentations about AI models and comparisons. Each presentation is a fully self-contained HTML file with embedded CSS and JavaScript—no build process, frameworks, or external dependencies are needed.

## Architecture

### File Structure
- `index.html` — Landing page with links to all presentations
- `ai-vergleich.html` — German presentation comparing Gemini, Claude, and ChatGPT (15 slides)
- `gemini_slides.html` — Presentation about Gemini features

### Presentation Architecture
Each presentation uses a simple slide deck pattern:

1. **HTML Structure**: Slides are div elements with class `slide` and sequential IDs (`id="s1"`, `id="s2"`, etc.)
2. **CSS Styling**: All styling is embedded with CSS custom properties (variables) for easy theming. Key variables: `--bg` (background), `--text` (foreground), `--accent` (highlights), plus AI model colors (`--gemini`, `--claude`, `--chatgpt`)
3. **JavaScript Navigation**:
   - Current slide index stored in `cur` variable
   - Keyboard controls: arrow keys, space, Home/End keys
   - Mouse controls: previous/next buttons
   - Touch controls: swipe left/right
   - Visual indicators: slide counter, progress bar, dot navigation

### Slide Markup Pattern
```html
<div class="slide" id="s1">
  <h2>Slide Title</h2>
  <p>Content here</p>
</div>
```

The JavaScript automatically builds navigation dots and manages transitions between slides.

## Common Development Tasks

### Creating a New Presentation
1. Copy an existing HTML file as a template
2. Modify the `<title>` and presentation content
3. Add slides using the standard `<div class="slide" id="sN">` pattern
4. Update the slide count references in JavaScript (look for `total` and counter display)
5. Add a link to `index.html`

### Editing Slide Content
- Directly edit the HTML in the slide div
- Styling is in the embedded `<style>` tag at the top
- No rebuild needed—just refresh the browser

### Customizing Colors and Theming
- Modify CSS custom properties in the `:root` selector at the beginning of `<style>`
- Current color scheme includes AI model branding colors (Gemini blue, Claude orange, ChatGPT green)

### Testing/Previewing
- Open the HTML file directly in a web browser
- All functionality works immediately without any build or server setup
- Keyboard navigation: arrow keys, space, Home/End
- Touch swipe support on mobile/tablet devices

## Browser Compatibility
These presentations use:
- Standard HTML5/CSS3 features
- Modern JavaScript (ES6 arrow functions, `const`/`let`, optional chaining)
- No CSS preprocessors or polyfills needed
- Tested layout: fullscreen presentation mode (100vh, no scrolling)

## Notes
- All presentations are in German
- Presentations contain AI model comparisons and evaluation data current as of February 2026
- Files use UTF-8 encoding with HTML entity encoding for special characters (e.g., `&amp;`)
- Navigation is fully responsive—works on desktop, tablet, and mobile

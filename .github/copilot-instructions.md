# AI Coding Agent Instructions for ai-hub-site-widget

## Project Overview
This is a static HTML/CSS/JavaScript widget system for displaying AI tool information on a school district's website. It consists of embeddable widgets that list approved AI tools with details, designed for iframe integration.

## Architecture
- **Pure static site**: No build tools, frameworks, or server-side code
- **Two main widgets**: 
  - `index.html`: Featured grid layout (1 featured + 2x3 grid)
  - `approvedai.html`: Expandable tool list with details panels
- **Iframe-ready**: All external links use `target="_top"` to break out of frames
- **Responsive**: CSS Grid-based layouts that adapt to screen sizes

## Key Patterns
- **CSS Variables**: Define themes in `:root` (colors, spacing, shadows)
- **Data Attributes**: Use `data-*` for JavaScript hooks (e.g., `data-featured`, `data-tool`)
- **Element Movement**: JS moves cards from hidden source divs into layout positions
- **Inline Styles**: All CSS embedded in `<style>` tags within HTML files
- **System Fonts**: Use `system-ui, -apple-system, BlinkMacSystemFont, "Segoe UI"` stack

## Development Workflow
- **No build process**: Edit HTML/CSS/JS directly, test by opening files in browser
- **Testing**: Open files locally or serve via simple HTTP server (e.g., `python -m http.server`)
- **Embedding**: Widgets designed for iframe use; test in parent page context
- **Image Assets**: Hosted externally on district's Finalsite CMS

## Important Files
- `index.html`: Featured grid widget with card movement logic
- `approvedai.html`: Tool listing with expandable details via chip toggles
- `README.md`: Basic project description

## Conventions
- **Class Naming**: Semantic names like `.card`, `.tool`, `.featured-grid`
- **Grid Layouts**: Use `display: grid` with `grid-template-columns` for responsive layouts
- **Hover Effects**: Subtle transforms and shadow changes on `.card:hover`
- **Accessibility**: Use `aria-expanded` for toggle states, proper alt text on images
- **Security**: Add `rel="noopener noreferrer"` to external links

## Common Tasks
- **Adding Tools**: Append new `<article class="tool">` blocks in `approvedai.html`
- **Updating Featured**: Add `data-featured="true"` to card in `index.html`
- **Styling Changes**: Modify CSS variables in `:root` for theme updates
- **Layout Adjustments**: Tweak grid templates in media queries for responsiveness
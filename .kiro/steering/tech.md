# Technology Stack

## Repository Type
Static support website - contains only HTML documentation and support pages.

## Tech Stack
- **Frontend**: Pure HTML5 with embedded CSS
- **Styling**: Native CSS with system fonts (-apple-system, BlinkMacSystemFont)
- **Hosting**: GitHub Pages (orbital-support.github.io)
- **Version Control**: Git

## Development Environment
- **Editor**: VSCode with Kiro agent integration
- **MCP**: Disabled in project settings

## Build & Deployment
This is a static site with no build process required.

### Common Commands
```bash
# Serve locally (if needed)
python3 -m http.server 8000

# Deploy
# Automatic deployment via GitHub Pages on push to main branch
```

## Code Style Guidelines
- Use semantic HTML5 elements
- Embed CSS in `<style>` tags for simplicity
- Follow Apple's system font stack for consistency
- Maintain responsive design with viewport meta tag
- Keep styling minimal and clean

## File Conventions
- Main support page: `support.html`
- Documentation: `README.md`
- No build artifacts or dependencies
# Copilot Instructions for Academic Personal Website

## Repository Summary

This repository contains an academic personal website (originally Jon Barron's website at https://jonbarron.info/) showcasing research publications, projects, and biographical information. It's a **static HTML website** deployed via **GitHub Pages** with no build system or frameworks - just pure HTML, CSS, and JavaScript.

## High-Level Repository Information

- **Project Type**: Static academic personal website
- **Deployment**: GitHub Pages (custom domain via CNAME file)
- **Size**: ~62MB total (26MB zipnerf, 12MB mipnerf360, 9.8MB images, 9.5MB mipnerf, 4MB data)
- **Languages**: HTML, CSS, JavaScript (no frameworks)
- **Main Files**: 
  - `index.html` (227KB, 4,432 lines) - main homepage
  - `stylesheet.css` (4KB) - custom styling with Google Fonts
  - `CNAME` - custom domain configuration
- **Dependencies**: None (uses CDN resources like Google Fonts)
- **Target Runtime**: Web browsers (static content)

## Build Instructions

### ✅ No Build Process Required
This is a **static website** with no compilation, bundling, or preprocessing steps.

### Local Development & Testing
**Always use Python's built-in HTTP server for local testing:**
```bash
cd /home/runner/work/shchinnasamy.github.io/shchinnasamy.github.io
python3 -m http.server 8000
```
- **Expected result**: Server starts on http://localhost:8000
- **Validation**: `curl -I http://localhost:8000` should return HTTP 200
- **Stop server**: `pkill -f "python3 -m http.server"`

### No Traditional Build/Test/Lint Commands
- ❌ No `npm install`, `npm build`, `npm test`
- ❌ No `bundle install`, `jekyll build`
- ❌ No package.json, Gemfile, or build configuration files
- ❌ No GitHub Actions workflows or CI/CD pipelines
- ❌ No automated testing framework

### Validation Steps
1. **Local serving test**: Python HTTP server should serve files successfully
2. **HTML validation**: Ensure HTML syntax is valid (check for unclosed tags, proper nesting)
3. **Link integrity**: Verify internal links work (especially to subprojects and assets)
4. **CSS integrity**: Check that stylesheet.css loads and applies correctly
5. **Asset availability**: Ensure images, PDFs, and other assets in `data/` and `images/` directories are accessible
6. **Responsive behavior**: Test that the academic layout works across different screen sizes

## Project Layout & Architecture

### Root Directory Structure
```
/
├── index.html           # Main homepage (4,432 lines, academic CV format)
├── stylesheet.css       # Custom CSS styling (Google Fonts, responsive design)
├── CNAME               # Custom domain: jonbarron.info
├── README.md           # Basic project description
├── images/             # Research images, photos, videos (9.8MB)
├── data/               # Academic papers, PDFs, BibTeX files (4MB)
├── mipnerf/            # Project page: Mip-NeRF research (9.5MB)
├── mipnerf360/         # Project page: Mip-NeRF 360 research (12MB)
└── zipnerf/            # Project page: Zip-NeRF research (26MB)
```

### Architecture Overview
- **Main page**: `index.html` - academic CV format with research highlights
- **Styling**: `stylesheet.css` - custom CSS with table-based layout, hover effects
- **Subprojects**: Each research project has its own directory with independent HTML/CSS/JS
- **Assets**: Large collection of research images, videos, and academic papers
- **Navigation**: Simple HTML links, no JavaScript routing

### Key Architectural Elements
1. **HTML Structure**: Table-based layout for academic content presentation
2. **CSS Framework**: Custom styling, no Bootstrap/Tailwind - uses Google Fonts (Lato)
3. **JavaScript**: Minimal JS for image hover effects and interactive elements
4. **Asset Organization**: Logical separation by content type (images/, data/)
5. **Responsive Design**: CSS media queries for mobile/desktop compatibility

### GitHub Pages Deployment
- **Automatic deployment** from the repository root
- **Custom domain** configured via CNAME file
- **No GitHub Actions** - uses GitHub Pages' built-in static site serving
- **Branch**: Deploys from the default branch automatically

### Subproject Structure
Each research project directory (mipnerf/, mipnerf360/, zipnerf/) follows this pattern:
- `index.html` - project-specific page
- `css/` - project-specific styles
- `js/` - project-specific JavaScript
- `img/` - project-specific images

### Content Management
- **Publications**: Listed in chronological order in main HTML with BibTeX references
- **Images**: Organized by project/paper in images/ directory
- **Academic data**: PDFs and BibTeX files in data/ directory
- **Project pages**: Independent HTML pages for major research projects

### Key Files for Agents

**Critical files (always preserve structure):**
- `index.html` - Complex academic CV layout, modify carefully
- `stylesheet.css` - Custom styling, changes affect entire site
- `CNAME` - Domain configuration, don't modify

**Content directories:**
- `images/` - Research visuals, large binary files
- `data/` - Academic papers and references
- Project directories - Self-contained research showcases

### Dependencies & External Resources
- **Google Fonts**: Lato font family loaded via CSS @font-face
- **No JavaScript frameworks**: Pure vanilla JavaScript for interactions
- **No CSS frameworks**: Custom CSS implementation
- **External links**: Many links to academic papers, Google Scholar, GitHub repositories

### Common Tasks for Agents
1. **Adding publications**: Modify `index.html` table structure, add corresponding images/data
2. **Updating content**: Text changes in HTML, ensure HTML validity
3. **Asset management**: Add/replace images, ensure proper file paths
4. **Styling changes**: Modify `stylesheet.css`, test responsiveness
5. **Link maintenance**: Update URLs, verify external link functionality

### Important Notes
- **Always test locally** with Python HTTP server before committing changes
- **Preserve academic formatting** - this is a professional academic website
- **Handle large binary assets carefully** - images and videos are significant in size
- **Maintain HTML validity** - no build process means manual HTML validation is critical
- **Respect external links** - many point to academic institutions and papers
- **TRUST THESE INSTRUCTIONS** - this repository is well-understood, minimize exploration time

### Time Estimates
- **Local server startup**: < 5 seconds
- **HTML syntax validation**: < 30 seconds
- **Full site serving test**: < 10 seconds
- **Asset verification**: 1-2 minutes (due to large image directory)

### Validation Commands (Tested & Verified)
```bash
# Start local server (tested working)
python3 -m http.server 8000

# Validate server response (tested working)
curl -I http://localhost:8000
# Expected: HTTP/1.0 200 OK, Content-Length: 227095

# Test CSS loading (tested working)
curl -s http://localhost:8000/stylesheet.css | head -3
# Expected: CSS content with Google Fonts

# Test subproject pages (tested working)
curl -I http://localhost:8000/mipnerf/
# Expected: HTTP 200, HTML content

# Test image assets (tested working)
curl -I http://localhost:8000/images/JonBarron.jpg
# Expected: HTTP 200, image/jpeg

# Stop server (tested working)
pkill -f "python3 -m http.server"
```

### HTML Structure Validation
- **Balanced tags**: HTML has 7 opening `<table>` tags, 7 closing `</table>` tags (verified)
- **Document structure**: Proper `<!DOCTYPE HTML>`, closes with `</html>` (verified)
- **File size**: index.html is exactly 227,095 bytes, 4,432 lines (verified)

**Remember**: This is a static site with no build complexity. Focus on HTML/CSS correctness and asset management rather than searching for build systems that don't exist. All commands in these instructions have been tested and verified to work.
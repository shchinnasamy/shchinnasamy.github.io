# Personal Academic Website Setup - Clean Jon Barron's Template

## Problem Statement

I have forked Jon Barron's academic website source code from https://jonbarron.info/ into the [shchinnasamy.github.io](https://github.com/shchinnasamy/shchinnasamy.github.io) repository. This website template needs to be cleaned up to remove Jon Barron's personal content and research projects, preparing it as a foundation for my own personal academic website.

The website is a static HTML site that will be deployed via GitHub Pages with no build system or frameworks - just pure HTML, CSS, and JavaScript. Currently, the repository contains:

- Jon Barron's complete academic CV with publications and research projects
- Large research project directories (mipnerf/, mipnerf360/, zipnerf/) totaling ~47MB
- Personal images, research videos, and academic papers (~14MB)
- Biographical information and research highlights specific to Jon Barron

## Acceptance Criteria

### ✅ Directory Cleanup
- [ ] **Remove research project directories**: Delete `mipnerf/`, `mipnerf360/`, and `zipnerf/` directories completely
- [ ] **Clean images directory**: Remove Jon Barron's personal photos and research-specific images from `images/` directory
- [ ] **Clean data directory**: Remove Jon Barron's academic papers, BibTeX files, and personal CV from `data/` directory

### ✅ Content Preparation  
- [ ] **Preserve website structure**: Keep the basic HTML template structure in `index.html` for academic CV format
- [ ] **Maintain styling**: Preserve `stylesheet.css` and responsive design elements
- [ ] **Keep deployment config**: Retain `CNAME` file and GitHub Pages configuration
- [ ] **Preserve instructions**: Keep `.github/copilot-instructions.md` for future development guidance

### ✅ Documentation Updates
- [ ] **Update README.md**: Change description from Jon Barron's website to a personal academic website template
- [ ] **Verify functionality**: Ensure the cleaned website still serves properly via Python HTTP server
- [ ] **Test GitHub Pages**: Confirm deployment structure remains compatible with GitHub Pages

### ✅ Quality Assurance
- [ ] **Validate HTML**: Ensure HTML structure remains valid after content removal
- [ ] **Check links**: Verify that removing directories doesn't break essential site navigation
- [ ] **Test responsiveness**: Confirm academic layout works across different screen sizes
- [ ] **Asset integrity**: Ensure remaining CSS and any preserved assets load correctly

## Implementation Guidance

### Files That Need Updating/Creating

#### 🗑️ Directories to Delete Completely
```
mipnerf/           # Mip-NeRF research project (9.5MB)
mipnerf360/        # Mip-NeRF 360 research project (12MB)  
zipnerf/           # Zip-NeRF research project (26MB)
```

#### 🧹 Directories to Clean (Remove Most Content)
```
images/            # Remove Jon Barron's photos and research images
├── JonBarron.jpg  # Personal photo - REMOVE
├── [research].jpg # Research images - REMOVE MOST
└── favicon/       # Consider keeping basic favicon structure

data/              # Remove academic papers and personal documents
├── JonBarron-CV.pdf      # Personal CV - REMOVE
├── JonBarron-bio.txt     # Personal bio - REMOVE  
├── *.bib files           # Research publications - REMOVE
└── *.pdf files           # Academic papers - REMOVE
```

#### ✅ Files to Preserve and Update
```
index.html         # Keep as template, remove personal content references
stylesheet.css     # Keep styling intact
CNAME             # Keep for GitHub Pages custom domain
README.md         # Update to reflect cleaned state
.github/          # Keep development instructions
```

### Technical Implementation Steps

1. **Local Development Setup** (as per copilot-instructions.md):
   ```bash
   cd /path/to/shchinnasamy.github.io
   python3 -m http.server 8000
   # Test: curl -I http://localhost:8000 should return HTTP 200
   ```

2. **Directory Removal**:
   ```bash
   rm -rf mipnerf/ mipnerf360/ zipnerf/
   ```

3. **Content Cleanup**:
   ```bash
   # Clean images directory
   cd images/
   # Remove Jon Barron's personal and research images
   # Keep only essential template assets if any
   
   # Clean data directory  
   cd ../data/
   # Remove personal academic papers and bio files
   # Keep directory structure for future content
   ```

4. **Validation**:
   ```bash
   # Test local serving
   python3 -m http.server 8000
   curl -I http://localhost:8000  # Should return HTTP 200
   
   # Check HTML validity
   # Verify CSS loads correctly
   # Test responsive behavior
   ```

### Post-Cleanup Repository State

After completion, the repository should be:
- **Size**: Reduced from ~62MB to ~5-10MB
- **Content**: Clean template ready for personal academic content
- **Structure**: Academic CV layout preserved but content-agnostic
- **Deployment**: Fully compatible with GitHub Pages
- **Maintenance**: Easy to customize with personal publications and bio

### Development Notes

- **No Build Process**: This is a static website with no compilation needed
- **Testing**: Always use `python3 -m http.server 8000` for local testing
- **Validation**: Focus on HTML validity and asset loading rather than automated tests
- **GitHub Pages**: Changes will automatically deploy when pushed to main branch

## Success Criteria

✅ Repository size significantly reduced (from ~62MB to under 10MB)  
✅ All Jon Barron-specific content removed  
✅ Website structure and styling preserved  
✅ Local development server works: `curl -I http://localhost:8000` returns HTTP 200  
✅ GitHub Pages deployment ready  
✅ Clear template ready for personal academic content  

---

**Labels**: `enhancement`, `cleanup`, `documentation`  
**Priority**: High  
**Estimated Effort**: 2-4 hours
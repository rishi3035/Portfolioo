# Copilot Instructions for Portfolioo

## Project Overview
This codebase is a static portfolio site with advanced asset management and build automation using Gulp. The main working directory is `BraxtonGULP/app/`, with outputs and assets distributed across `dist/`, `css/`, `fonts/`, `img/`, and `js/`.

## Architecture & Key Components
- **Source Files:**
  - HTML: `BraxtonGULP/app/*.html` (main site pages)
  - SASS: `BraxtonGULP/app/sass/` (styles, compiled to CSS)
  - JS: `BraxtonGULP/app/js/` (site scripts)
  - Assets: `BraxtonGULP/assets/` (icons, fonts, vendor scripts)
- **Build Output:**
  - `dist/` (production build)
  - `source-files/` (external libraries, minified/expanded assets)
- **External Libraries:**
  - Managed via npm and stored in `node_modules/` (see Gulp tasks for usage)
  - Examples: Swiper, PhotoSwipe, GSAP, Bootstrap, jQuery, Lenis, ImagesLoaded

## Build & Development Workflow
- **Gulp Tasks:**
  - `gulp` (default): Starts dev server, watches files, compiles SASS, bundles JS
  - `gulp build`: Cleans `dist/`, compiles assets, copies files for production
  - Key tasks: `styles`, `cssmin`, `cssexp`, `libs`, `libsdemo`, `libsexp`, `html`, `buildcopy`, `buildalljs`
- **Live Reload:**
  - Uses BrowserSync for hot-reloading during development
- **Asset Conventions:**
  - SASS uses Bourbon mixins
  - Autoprefixer targets legacy browsers (IE7+, Firefox < 20)
  - Minified assets have `.min` suffix

## Patterns & Conventions
- **File Organization:**
  - Keep custom code in `BraxtonGULP/app/` and `BraxtonGULP/assets/`
  - Use `source-files/` for third-party libraries and compiled assets
- **Build Customization:**
  - Modify `BraxtonGULP/gulpfile.js` to change build steps or add new asset pipelines
- **Integration Points:**
  - External JS/CSS libraries referenced in Gulp tasks and loaded from `node_modules/`
  - PHP mail handler: `BraxtonGULP/app/mail.php`

## Examples
- To add a new SASS partial: Place in `BraxtonGULP/app/sass/`, import in main SASS file
- To add a new JS library: Install via npm, update Gulp tasks to include in bundle
- To debug build: Run `gulp` and check BrowserSync output for errors

## References
- See `BraxtonGULP/gulpfile.js` for all build logic and asset pipeline details
- See `source-files/` for vendor documentation (e.g., Swiper, PhotoSwipe README)

---
**For AI agents:**
- Always update Gulp tasks when adding/removing major assets
- Respect file organization and naming conventions for maintainability
- Use BrowserSync for local testing and debugging
- Reference vendor READMEs in `source-files/` for integration details

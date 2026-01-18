# Restaurant Menu HTML Template - AI Coding Instructions

## Project Overview
Static restaurant menu template with fixed sidebar and responsive layout. Single-page HTML with vanilla CSS—no build tools, frameworks, or JavaScript dependencies.

## Architecture & Layout Pattern

### Two-Column Layout System
- **Sidebar** (33% width): Fixed position branding and contact info with background image overlay
- **Main content** (67% width): Menu sections with alternating image placement using `margin-left: 33%`
- Responsive breakpoints: Tablet (481-1024px), Phone (<480px)

### Key Structural Pattern
All menu sections follow this exact HTML structure in [index.html](index.html):
```html
<div class="section">
    <div class="text">
        <h2>Category Name</h2>
        <div class="plate">
            <p>Dish Name</p>
            <div class="dots"></div>
            <p>Price €</p>
        </div>
        <p class="description">Description text</p>
    </div>
    <div class="img" style="background: url('img/name.jpg')..."></div>
</div>
```

## Styling Conventions

### Dotted Price Separator
The `.dots` element creates the dotted line between dish name and price using `border-bottom: 1px solid #ededed` with `flex: 1` for automatic expansion.

### Image Placement
- Default: Image on right (`margin-left: 6%`)
- Alternating: Add `.left` class to reverse order (`order: -1; margin-right: 6%`)
- Inline background images via `style` attribute, not CSS classes

### Typography
- Font stack: 'Work Sans' (Google Fonts), sans-serif fallback
- All headings use `text-transform: uppercase` and `font-weight: 200`
- Base font-size: `0.940rem` with `line-height: 1.65`

## Content Customization Checklist
When adapting this template:
1. Replace logo image: [img/logo.png](img/logo.png)
2. Update sidebar background: [img/background.jpg](img/background.jpg)
3. Modify social media SVG icons in header (Facebook, Instagram, Google inline)
4. Replace section images: `img/startes.jpg`, `img/firsts.jpg` (note: "startes" typo in filename)
5. Update restaurant name, description, location, and contact info in sidebar

## Responsive Behavior
- **Desktop**: Two-column with fixed sidebar
- **Tablet** (481-1024px): Sidebar remains fixed, main content stacks images vertically at 15em height
- **Phone** (<480px): Sidebar becomes relative positioning, images hidden entirely

## Development Workflow
- No build process—edit HTML/CSS directly and refresh browser
- Images must be placed in `/img` directory with exact filename references
- Test at breakpoints: >1024px, 481-1024px, <480px

## Deployment

### Railway (Static Site)
```bash
# Install Railway CLI
npm i -g @railway/cli

# Deploy from project root
railway login
railway init
railway up
```
Railway auto-detects static HTML and serves from root directory.

### Alternative Platforms
- **Netlify**: Drag-drop folder to [app.netlify.com](https://app.netlify.com) or `netlify deploy`
- **Vercel**: `vercel --prod` from project root
- **GitHub Pages**: Push to repo, Settings → Pages → Deploy from branch

All platforms serve the template as-is with no build step required.

## Common Modifications
- **Adding menu items**: Clone `.plate` + `.description` pairs within `.text` divs
- **New menu sections**: Clone entire `.section` block, toggle `.left` class for image side
- **Color scheme**: Sidebar overlays are defined by background image; adjust text color via `.sidebar { color: #fff }`

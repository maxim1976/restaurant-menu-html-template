# Restaurant Menu HTML Template - 無名早餐店

## Project Overview
A bilingual restaurant menu website for "無名早餐店" (Unnamed Breakfast Shop) in Hualien, Taiwan. Features a traditional Taiwanese breakfast menu with Chinese and English translations, optimized for SEO and mobile responsiveness.

## Tech Stack
- Pure HTML5 + CSS3 (no frameworks)
- Google Fonts (Work Sans)
- Responsive design with mobile-first approach
- Structured data (JSON-LD) for SEO

## Project Structure
```
restaurant-menu-html-template/
├── index.html          # Main page with menu and restaurant info
├── css/
│   └── style.css      # All styling including responsive breakpoints
├── img/               # Background and menu images
│   ├── background2.jpg
│   ├── logo2.png
│   ├── starter2.jpg
│   ├── lepeshka3.jpg
│   ├── lepeshka4.jpg
│   └── xiaolongbao2.jpg
└── CLAUDE.MD         # This file
```

## Key Features

### 1. Bilingual Content
- All menu items include Chinese and English names
- Dual language descriptions throughout
- Structured data in both languages for search engines

### 2. SEO Optimization
- Comprehensive meta tags (description, keywords, author, robots)
- Open Graph tags for social media sharing
- Twitter Card support
- JSON-LD structured data for Google rich results
- Geo tags for local search (Hualien, Taiwan)
- Semantic HTML structure

### 3. Responsive Design
Three breakpoints:
- **Desktop** (>1024px): Fixed sidebar (33% width) with scrollable menu
- **Tablet** (481px-1024px): Stacked layout with full-width images
- **Mobile** (<480px): Full stacking, sidebar becomes header, images hidden

### 4. Layout Components
- **Sidebar/Header**: Restaurant info, logo, hours, location, contacts, social links
- **Main Content**: Menu sections with category grouping
- **Lunar New Year Notice**: Special holiday announcement section

## Menu Categories
1. 燒餅類 (Flatbread) - 10 items
2. 餅類 (Pancakes) - 6 items
3. 包子饅頭 (Buns) - 6 items
4. 飲料 (Drinks) - 8 items (豆漿/茶類)
5. 配料 (Add-ons) - 3 items

## Design Patterns

### Menu Item Structure
Each menu item follows this pattern:
```html
<div class="plate">
    <p>中文名稱<br><small>English Name</small></p>
    <div class="dots"></div>
    <p>價格 NT$</p>
</div>
```

### Color Scheme
- Primary accent: `#d4af37` (golden)
- Background: White (`#ffffff`)
- Text: Black (`#000`)
- Sidebar overlay: `rgba(0, 0, 0, 0.5)`

### Typography
- Font family: Work Sans
- Font weights: 200 (headings), 400 (body)
- All headings: uppercase transformed

## Important File Paths
All paths are **root-relative** to work with URL rewriting:
- CSS: `/css/style.css`
- Images: `/img/filename.jpg`
- Logo: `/img/logo2.png`

## Contact Information
- **Address**: 花蓮縣花蓮市吉鄉鄉德安一街59號
- **Phone**: 03-8335408
- **Email**: email@email.com (placeholder)
- **Coordinates**: 23.974038109175858, 121.59559924806095

## Business Hours
- Tuesday-Friday: 5:30 AM - 10:30 AM
- Saturday-Sunday: 5:30 AM - 11:00 AM
- Monday: Closed

## Recent Changes
Based on git history:
- Added Lunar New Year holiday notice (Feb 13-20)
- Fixed CSS compatibility for iPhone Safari (webkit prefixes)
- Updated to root-relative paths for URL rewriting compatibility
- Added comprehensive SEO meta tags

## Development Guidelines

### When Adding New Menu Items
1. Follow the `.plate` structure with bilingual names
2. Use `<small>` tags for English translations
3. Keep pricing format consistent: `XX.00 NT$`
4. Ensure mobile responsiveness

### When Modifying Styles
1. Test across all three breakpoints
2. Maintain webkit prefixes for Safari compatibility
3. Use `box-sizing: border-box` for all elements
4. Preserve the dotted line separator (`.dots`)

### SEO Maintenance
1. Update JSON-LD structured data when business info changes
2. Keep Open Graph images up to date
3. Maintain geo coordinates accuracy
4. Update opening hours in both HTML and JSON-LD

## Browser Compatibility
- Modern browsers (Chrome, Firefox, Safari, Edge)
- iPhone Safari optimized with `-webkit-` prefixes
- Responsive down to 320px width
- Smooth scrolling support where available

## Deployment Notes
- Uses root-relative paths - deploy to web root or configure URL rewriting
- Requires HTTPS for optimal SEO performance
- Images should be optimized before deployment
- Structured data should be validated with Google Rich Results Test

## Future Enhancement Ideas
- Add JavaScript for dynamic menu filtering
- Implement online ordering integration
- Add customer review section
- Create print-friendly stylesheet
- Add multilingual support (beyond Chinese/English)
- Implement dark mode toggle
- Add accessibility improvements (ARIA labels)

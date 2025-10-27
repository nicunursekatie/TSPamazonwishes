# The Sandwich Project - Amazon Wishlist Pages

## Project Overview

This codebase contains donation landing pages for The Sandwich Project, a 501(c)(3) nonprofit addressing weekend food insecurity in Metro Atlanta. The project consists of two main HTML files designed to drive Amazon wishlist donations.

## Architecture & Purpose

### Core Components
- **`amazonwishlistbridge.html`** - Emotional storytelling landing page using FEEL-SEE-DO conversion framework
- **`amazonwishlistlandingpage.html`** - Interactive wishlist interface with item categorization and priority management

### Donation Flow
1. Bridge page creates emotional connection through impact statistics and storytelling
2. Landing page provides interactive item selection with "lunch builder" interface
3. Both pages funnel to Amazon wishlist purchases via direct product links

## Design System

### Brand Colors (CSS Custom Properties)
- `--primary-blue` - Main brand, headers, text
- `--accent-orange` - CTAs, highlights, urgency  
- `--teal` - Gradients, secondary actions
- `--light-blue` - Supporting elements
- `--burgundy` - Priority badges, alerts

### Typography & Responsive Patterns
- Apple system font stack with fallbacks
- `clamp()` for responsive font sizing
- Mobile-first grid layouts using `auto-fit` and `minmax()`

## Data Management

### Item Schema (in `amazonwishlistlandingpage.html`)
```javascript
{
    name: "Product name",
    price: 10.99,               // null if price varies
    priority: "highest|high",   // Determines section placement
    needs: 75,                  // Quantity needed (drives urgency)
    category: "protein|fruit|granola|applesauce|supplies",
    image: "amazon-image-url",
    link: "amazon-product-url"
}
```

### Categories & Icons
- 💪 `protein` - Energy bars, meat sticks
- 🍎 `fruit` - Fruit cups, pouches
- 🌾 `granola` - Breakfast bars, granola bars
- 🍏 `applesauce` - Applesauce cups, pouches
- 📦 `supplies` - Bags, storage items

## Key Conventions

### Asset Management
- Marketing graphics stored in root directory (`1in6.png`, `72 hours.png`, `impact.png`)
- Logo expected at `LOGOS/TSP_reverse_transparent.png` (currently missing)
- Fallback SVG placeholders for broken images

### Interactive Features
- Intersection Observer for scroll-triggered animations
- Priority-based item sorting (highest → running low → all items)
- Category filtering with visual state management
- "Lunch builder" interface for educational engagement

### Amazon Integration
- Placeholder `YOURID` in wishlist URLs needs replacement with actual Amazon wishlist ID
- Direct product links bypass wishlist for individual items
- Shipping address shown as "The Sandwich Project" for trust building

## Development Workflow

### File Structure
- Self-contained HTML files with embedded CSS/JS
- No build process or external dependencies
- Static hosting ready (CDN/simple web server)

### Content Updates
- Item data hardcoded in JavaScript arrays
- Impact statistics embedded in HTML
- Update both bridge and landing pages for consistency

### Testing Considerations
- Verify Amazon wishlist URLs before deployment
- Test responsive behavior on mobile devices
- Check image loading and fallback behavior
- Validate donation conversion flow end-to-end

## Mission-Critical Elements

### Conversion Optimization
- Emotional impact messaging drives urgency
- Multiple pathways to donation (wishlist, individual items)
- Trust signals (501c3 status, shipping address, impact numbers)
- Mobile-optimized donation flow

### Brand Consistency
- Maintain warm, approachable nonprofit tone
- Use established color palette for all new elements
- Preserve food security messaging focus
- Keep Atlanta community connection prominent

When modifying these pages, prioritize donation conversion and maintain the nonprofit's mission-focused messaging while ensuring technical accessibility and mobile responsiveness.
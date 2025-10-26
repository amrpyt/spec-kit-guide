# UX Design Specification - Alsoadaa Export Website

**Project:** Alsoadaa Export Website  
**Designer:** Sally (UX Designer)  
**Date:** 2025-10-25  
**Version:** 1.0  
**For:** Amr

---

## Executive Summary

This UX specification defines the visual design system, interaction patterns, and user interface guidelines for the Alsoadaa Export Website. The design prioritizes **clarity, trust, and speed** to serve B2B buyers seeking Egyptian agricultural products.

**Design Philosophy:** Professional minimalism that lets the products (beautiful fruits and vegetables) be the hero, with trust signals and performance as core pillars.

---

## Design System Foundation

### Selected Design System Approach

**Selected Direction: "Vibrant & Appetizing" - Colorful, Fresh, Energetic**

**Design Philosophy:** Let the natural beauty of Egyptian fruits and vegetables shine through vibrant, colorful design that celebrates freshness and quality.

**Recommendation: TailwindCSS + shadcn/ui + Vibrant Agricultural Theme**

**Rationale:**
- **TailwindCSS:** Utility-first approach enables rapid development and easy customization
- **shadcn/ui:** Pre-built, accessible components that can be customized to match brand
- **Vibrant Theme:** Colorful, energetic aesthetic that showcases the natural beauty of agricultural products

**Why this works for Alsoadaa:**
- Fast performance (no heavy frameworks)
- Easy for developers to maintain
- Vibrant, appetizing look that celebrates the products
- Highly customizable for colorful agricultural branding
- Excellent accessibility out of the box
- **Perfect for visual products** - fruits and vegetables sell themselves with great photography

---

## Color Palette

### Vibrant Multi-Color System

**Philosophy:** Each product category has its own color identity, inspired by the natural colors of Egyptian fruits and vegetables.

### Primary Citrus Orange (Main Brand)
```
Primary-500: #FF8C42 (Vibrant citrus orange)
Primary-600: #F57C00 (Hover - deeper orange)
Primary-700: #E65100 (Active - rich orange)
Primary-400: #FFB74D (Light - soft orange)
Primary-50: #FFF3E0 (Background tint)
```

**Usage:**
- Main CTAs ("Request Quote", "Get Started")
- Navigation highlights
- Hero accents
- Citrus product category

### Fresh Green (Vegetables & Freshness)
```
Green-500: #4CAF50 (Fresh, vibrant green)
Green-600: #43A047 (Hover)
Green-700: #388E3C (Active)
Green-400: #66BB6A (Light)
Green-50: #E8F5E9 (Background)
```

**Usage:**
- Vegetable category
- "Available Now" badges
- Success messages
- Freshness indicators

### Deep Red (Berries & Pomegranates)
```
Red-500: #E53935 (Rich, appetizing red)
Red-600: #D32F2F (Hover)
Red-700: #C62828 (Active)
Red-400: #EF5350 (Light)
Red-50: #FFEBEE (Background)
```

**Usage:**
- Berry/pomegranate category
- Important notices
- Limited availability badges

### Sunny Yellow (Lemons & Energy)
```
Yellow-500: #FDD835 (Bright lemon yellow)
Yellow-600: #FBC02D (Hover)
Yellow-700: #F9A825 (Active)
Yellow-400: #FFEE58 (Light)
Yellow-50: #FFFDE7 (Background)
```

**Usage:**
- Lemon category
- Highlighting features
- Seasonal promotions
- Attention elements

### Purple Grape (Grapes & Premium)
```
Purple-500: #8E24AA (Rich grape purple)
Purple-600: #7B1FA2 (Hover)
Purple-700: #6A1B9A (Active)
Purple-400: #AB47BC (Light)
Purple-50: #F3E5F5 (Background)
```

**Usage:**
- Grape category
- Premium product indicators
- Special features

### Trust Blue (Professional & Reliable)
```
Blue-600: #1E88E5 (Trust, reliability)
Blue-700: #1976D2 (Hover)
Blue-500: #2196F3 (Links)
Blue-50: #E3F2FD (Backgrounds)
```

**Usage:**
- Professional sections
- Certifications
- About Us
- Contact info

### Neutral Colors

**Professional Grays**
```
Gray-900: #1C2833 (Headings, main text)
Gray-700: #566573 (Body text)
Gray-500: #85929E (Secondary text)
Gray-300: #D5DBDB (Borders, dividers)
Gray-100: #F2F3F4 (Backgrounds)
Gray-50: #FAFBFC (Page backgrounds)
White: #FFFFFF
```

### Semantic Colors

**Success:** #28A745 (Order confirmed, form success)  
**Warning:** #FFC107 (Coming soon, attention needed)  
**Error:** #DC3545 (Form errors, out of stock)  
**Info:** #17A2B8 (Tooltips, help text)

---

## Typography

### Font Stack

**Headings:** `'Poppins', 'Montserrat', 'Inter', -apple-system, BlinkMacSystemFont, system-ui, sans-serif`
- Rounded, friendly, modern
- Excellent legibility with personality
- Perfect for vibrant, approachable design

**Body Text:** `'Inter', 'SF Pro Text', -apple-system, BlinkMacSystemFont, system-ui, sans-serif`
- Clean, highly readable
- Works beautifully at all sizes
- Pairs perfectly with rounded headings

**Arabic Font:** `'Cairo', 'Tajawal', 'Noto Sans Arabic', sans-serif`
- Modern Arabic font with excellent legibility
- Supports both RTL and LTR gracefully

**Russian:** Inter handles Cyrillic beautifully (no separate font needed)

### Type Scale

```
Hero (H1): 48px / 3rem (desktop), 36px / 2.25rem (mobile)
  - Weight: 700 (Bold)
  - Line height: 1.1
  - Letter spacing: -0.02em
  - Usage: Homepage hero, page titles

H2: 36px / 2.25rem (desktop), 28px / 1.75rem (mobile)
  - Weight: 600 (Semibold)
  - Line height: 1.2
  - Usage: Section headings

H3: 28px / 1.75rem
  - Weight: 600
  - Line height: 1.3
  - Usage: Sub-sections, product names

H4: 20px / 1.25rem
  - Weight: 600
  - Line height: 1.4
  - Usage: Card headings, small sections

Body Large: 18px / 1.125rem
  - Weight: 400 (Regular)
  - Line height: 1.6
  - Usage: Introductory paragraphs, important text

Body: 16px / 1rem
  - Weight: 400
  - Line height: 1.6
  - Usage: Main body text, descriptions

Body Small: 14px / 0.875rem
  - Weight: 400
  - Line height: 1.5
  - Usage: Labels, secondary information

Caption: 12px / 0.75rem
  - Weight: 400
  - Line height: 1.4
  - Usage: Image captions, footnotes
```

---

## Spacing System

**Based on 8px grid for consistency:**

```
xs: 4px   (0.25rem)  - Tight spacing, icon padding
sm: 8px   (0.5rem)   - Small gaps between elements
md: 16px  (1rem)     - Standard element spacing
lg: 24px  (1.5rem)   - Section internal spacing
xl: 32px  (2rem)     - Between sections (mobile)
2xl: 48px (3rem)     - Between sections (desktop)
3xl: 64px (4rem)     - Major page sections
4xl: 96px (6rem)     - Hero sections, dramatic spacing
```

---

## Component Library

### Buttons

**Primary Button**
```
Style: Solid fill, Primary-600 background
Text: White, 16px, weight 500
Padding: 12px 24px (md), 16px 32px (lg)
Border radius: 8px
Hover: Primary-700, subtle lift (2px shadow)
Active: Primary-800, no shadow
Transition: all 200ms ease
```

**Secondary Button**
```
Style: Outline, 2px border Secondary-600
Text: Secondary-600, 16px, weight 500
Padding: 12px 24px
Border radius: 8px
Hover: Secondary-50 background, Secondary-700 border
```

**Text Button**
```
Style: No background, no border
Text: Secondary-600, underline on hover
Padding: 8px 16px
```

### Form Inputs

**Text Input**
```
Height: 48px
Padding: 12px 16px
Border: 1px Gray-300
Border radius: 8px
Font: 16px regular
Focus: Primary-500 border, 0 0 0 3px Primary-50 ring
Error: Error-500 border, Error-50 ring
```

**Label**
```
Font: 14px, weight 500
Color: Gray-700
Margin bottom: 8px
Required indicator: Accent-500 asterisk
```

**Helper Text**
```
Font: 12px
Color: Gray-500 (normal), Error-500 (error)
Margin top: 4px
```

### Cards

**Product Card (Visual Style - Selected)**
```
Background: White
Border: none (clean look)
Border radius: 16px (rounded for friendly feel)
Padding: 0 (image bleeds to edges)
Shadow: 0 4px 8px rgba(0,0,0,0.08)
Hover: Transform scale(1.03), shadow lifts to 0 8px 16px rgba(0,0,0,0.12)
Transition: all 300ms ease
```

**Contents:**
- **Lifestyle Image** (fills card, 16:9 ratio)
  - Colorful product photos in natural settings
  - Baskets, farms, fresh arrangements
- **Overlay Badge** (top-right corner)
  - Category color-coded
  - Season status with emoji (🟢 In Season!, 🟡 Coming Soon)
- **Product Name** (overlaid on image, bottom)
  - White text with dark semi-transparent background
  - Bold, clear
- **Certification Icons** (small, bottom corner)
- **Hover Effect:** Card slightly enlarges, reveals "View Details" button

**Trust Card** (Certifications, Testimonials)
```
Background: Gray-50
Border: none
Border radius: 16px
Padding: 24px
Shadow: none
```

### Navigation

**Desktop Header**
```
Height: 80px
Background: White
Border bottom: 1px Gray-200
Shadow: 0 1px 3px rgba(0,0,0,0.05) (on scroll)
```

**Sticky behavior:** Becomes fixed on scroll, adds subtle shadow

**Logo:** Left-aligned, max height 48px

**Navigation Items:**
```
Font: 16px, weight 500
Color: Gray-700
Hover: Primary-600
Active: Primary-600, underline 2px
Spacing: 32px between items
```

**Mobile Header**
```
Height: 64px
Hamburger: Right side, 24x24px icon
Menu: Full-screen overlay, slides from right
Menu background: White with blur
```

### Footer

**Desktop Layout:** 4 columns
```
Column 1: Company info + logo
Column 2: Quick links
Column 3: Products
Column 4: Contact info
```

**Background:** Gray-900 (dark theme for contrast)  
**Text:** Gray-300 for body, White for headings  
**Links:** Underline on hover  
**Padding:** 64px vertical, 48px horizontal  

---

## Layout Patterns

### Grid System

**Desktop:** 12-column grid, 24px gutters  
**Tablet:** 8-column grid, 16px gutters  
**Mobile:** 4-column grid, 16px gutters  

**Max width:** 1280px centered with padding

### Breakpoints

```
Mobile: 320px - 767px
Tablet: 768px - 1023px
Desktop: 1024px - 1439px
Large Desktop: 1440px+
```

### Page Sections

**Standard vertical rhythm:**
```
Mobile: 48px between sections
Desktop: 96px between sections
```

**Section internal padding:**
```
Mobile: 24px horizontal
Tablet: 48px horizontal
Desktop: 64px horizontal (within max-width container)
```

---

## Iconography

**Icon Set:** Lucide React  
**Why:** Modern, consistent, huge library, React-optimized

**Sizes:**
- Small: 16px (inline with text)
- Medium: 24px (buttons, cards)
- Large: 32px (features, highlights)
- XL: 48px (empty states, illustrations)

**Style:** Mix of outlined and filled for visual interest
- Filled icons for categories and badges (more vibrant)
- Outlined for navigation and UI controls

**Color:** Category color-coded
- Orange icons for citrus 🍊
- Green icons for vegetables 🥬
- Red icons for berries 🍓
- Yellow icons for lemons 🍋
- Purple icons for grapes 🍇

**Emoji Support:** Strategic use of food emojis for visual appeal and international recognition

---

## Photography & Imagery

### Product Images (Lifestyle Focus - Selected)

**Primary Style: Lifestyle Photography**
- **Natural settings:** Farms, orchards, markets, harvest scenes
- **Context shots:** Products in baskets, crates, natural arrangements
- **Rich colors:** Vibrant, saturated, appetizing
- **Natural lighting:** Golden hour, bright daylight
- **Story-telling:** Show the journey from farm to export

**Secondary Style: Clean Product Shots**
- White background for specs and technical pages
- Close-ups showing quality and freshness
- Multiple angles for detailed views

**Aspect Ratios:**
- Hero: 21:9 (ultra-wide for dramatic effect)
- Cards: 16:9 (landscape)
- Detail pages: 4:3 (more traditional, shows product better)

**Quality:**
- Source: 2400px+ width, high resolution
- Optimized: WebP format, multiple sizes (srcset)
- Lazy load: Below fold
- Color profile: sRGB for vibrant web display

**Treatment:**
- Border radius: 16px (rounded, friendly)
- Optional color overlay: Subtle category-colored gradient on hover
- **No heavy filters** - let natural colors shine
- Slight saturation boost for appetite appeal (5-10%)

### Supporting Imagery

**Certifications:** High-quality scans, badge format  
**Team/Company:** Natural, authentic photos (not stock)  
**Logistics:** Real shipment photos, containers, ports  
**Backgrounds:** Subtle, if used - prefer solid colors

---

## Interaction & Animation

### Principles

1. **Purposeful:** Animations guide attention, don't distract
2. **Fast:** 200-300ms for most transitions
3. **Natural:** Ease-out for entrances, ease-in for exits
4. **Performant:** Use transform and opacity only

### Standard Transitions

**Hover states:** 200ms ease  
**Page transitions:** 300ms ease-out  
**Modal open/close:** 250ms ease-in-out  
**Loading states:** Skeleton screens, no spinners  

### Micro-interactions

**Button click:** Subtle scale (0.98) + shadow change  
**Card hover:** Lift effect (shadow increase)  
**Form focus:** Ring appears with subtle scale  
**Success:** Checkmark animation (300ms)  
**Error shake:** Subtle horizontal shake (400ms)  

**Scroll reveals:** Fade-in + slide-up (stagger for multiple items)

---

## Accessibility

### WCAG 2.1 Level AA Compliance

**Color Contrast:**
- Text on background: Minimum 4.5:1
- Large text (18px+): Minimum 3:1
- All color combinations tested

**Keyboard Navigation:**
- Visible focus indicators (Primary-500 ring, 3px)
- Logical tab order
- Skip to main content link
- Escape closes modals

**Screen Readers:**
- Semantic HTML (h1, nav, main, article, etc.)
- ARIA labels where needed
- Alt text on all images (descriptive, not "image of")
- Form labels properly associated

**Touch Targets:**
- Minimum 44x44px for mobile
- Adequate spacing between interactive elements

---

## Responsive Behavior

### Mobile-First Approach

Design for mobile first, enhance for larger screens.

**Key Adaptations:**

**Typography:**
- Scale down heading sizes (see type scale)
- Increase line height slightly on mobile for readability

**Navigation:**
- Desktop: Horizontal menu
- Mobile: Hamburger → full-screen overlay

**Product Grid:**
- Desktop: 3-4 columns
- Tablet: 2 columns
- Mobile: 1 column (or 2 for smaller products)

**Forms:**
- Multi-step on mobile (one question at a time)
- Single page on desktop (all fields visible)

**Images:**
- Desktop: Larger, high quality
- Mobile: Optimized, smaller file sizes

---

## Page-by-Page Mockup Descriptions

### Homepage

**Hero Section**
```
Layout: Full-width background image (farm/citrus), dark overlay
Height: 60vh desktop, 50vh mobile
Content: Centered
  - H1: "Fresh Egyptian Citrus to Your Market in 48 Hours"
  - Subheading: "ISO 9001 & Global G.A.P Certified Exporter Since 2009"
  - CTA Primary: "Request Quote"
  - CTA Secondary: "View Products"
Background: Parallax scroll effect (subtle)
```

**Trust Indicators Strip**
```
Layout: Horizontal row, 4 items
Background: Gray-50
Icons: Large (48px), Primary-600
Stats: Large numbers (36px), bold
Labels: 14px, Gray-600
Items:
  - "15+ Years Exporting"
  - "50+ Countries Served"
  - "ISO & GAP Certified"
  - "1000+ Containers/Year"
```

**Featured Products**
```
Layout: 4-column grid (desktop), 2-col (tablet), 1-col (mobile)
Heading: "Our Premium Products"
Card design: Image (16:9) + Name + Season badge + "View Details" link
Hover: Card lifts slightly
Below grid: "View All Products" button (Secondary)
```

**Why Choose Us**
```
Layout: 3-column grid
Icons: Large, Primary-600 (certification, truck, quality)
Titles: H4
Text: Short paragraph (3-4 lines)
Background: White
Items:
  - Quality Certified
  - Reliable Delivery
  - Fresh Guarantee
```

**Seasonal Calendar Preview**
```
Heading: "Seasonal Availability"
Visual: Mini calendar showing current + next 2 months
Products: Icons with color-coded availability
CTA: "View Full Calendar"
```

**Testimonials**
```
Layout: Carousel, 1 testimonial visible at a time
Card: Large quote, customer name, company, country
Background: Gray-50
Navigation: Dots below, auto-rotate every 5 seconds
```

**CTA Section**
```
Background: Primary-600 gradient
Text: White
Heading: "Ready to Import Premium Egyptian Products?"
CTA: "Get Your Quote Today" (White button with Primary-600 text)
```

---

### Product Catalog Page

**Layout: Sidebar + Grid**

**Filter Sidebar (Desktop)**
```
Width: 280px
Position: Sticky (stays visible on scroll)
Background: White
Border: 1px Gray-200

Sections:
  - Search box (top)
  - Season filter (checkbox group)
  - Category filter (checkbox group)
  - Availability filter (radio buttons)
  - "Clear All Filters" link
```

**Mobile Filters:**
- Button: "Filters" with count badge
- Opens: Bottom sheet overlay
- Same content as sidebar

**Product Grid**
```
Columns: 3 (desktop), 2 (tablet), 1-2 (mobile)
Gap: 24px
Sort dropdown: Top right (Name, Season, Featured)
Results count: Top left "Showing X of Y products"
```

**Product Cards** (same as homepage featured products)

**Empty State** (no results):
```
Icon: Large search/filter icon
Text: "No products match your filters"
CTA: "Clear Filters" button
```

---

### Product Detail Page

**Layout: 2-Column (Desktop), Stacked (Mobile)**

**Left Column: Image Gallery**
```
Main image: Large (600x400px), zoom on hover
Thumbnails: Below, 4-5 visible, horizontal scroll
Background: Gray-50 (makes product pop)
Border radius: 12px
```

**Right Column: Product Info**
```
Breadcrumb: Home > Products > [Category] > [Product]
Product Name: H1
Scientific Name: Body text, Gray-600
Certification Badges: Row of icons (ISO, GAP)

Short Description: 2-3 sentences, Body Large

Seasonal Availability:
  - Visual calendar indicator
  - Text: "Available: October - March"
  - Color-coded

Specifications Table:
  - Packaging options
  - Sizes/grades
  - Storage requirements
  - Shipping details
  Style: Alternating row colors, clean borders

CTA Section (Sticky on scroll):
  - Primary: "Request Quote"
  - Secondary: "Schedule Callback"
```

**Below: Related Products**
```
Heading: "You May Also Like"
Grid: 4 products, same card style
```

---

### About Us Page

**Hero**
```
Height: 40vh
Image: Farm landscape or team
Overlay: Dark
Text: Centered, White
  - H1: "About Al Soadaa"
  - Subheading: "Trusted Egyptian Exporter Since 2009"
```

**Company Story**
```
Layout: Text block, max-width 800px, centered
Font: Body Large for readability
Sections:
  - Our Beginning (2009)
  - Our Mission
  - Our Values
Images: Interspersed (farm, team, facilities)
```

**Timeline**
```
Visual: Vertical line with milestone markers
Style: Modern, icon for each milestone
Milestones:
  - 2009: Company Founded
  - [Year]: ISO Certification
  - [Year]: Global G.A.P
  - 2025: New Website Launch
Interaction: Scroll-triggered animations
```

**Certifications Showcase**
```
Layout: Grid, large certificate images
Hover: Lightbox opens full certificate
Background: White cards on Gray-50
```

**Team Section** (Optional)
```
Layout: Photo grid or single team photo
Text: Brief intro to key team members
Tone: Professional but approachable
```

---

### Contact Page

**Layout: Split (Desktop), Stacked (Mobile)**

**Left: Contact Form**
```
Multi-step (3 steps):
  Step 1: Contact Info (name, email, phone, country)
  Step 2: Inquiry Type (quote, callback, general)
  Step 3: Message (details, products of interest)

Progress: Step indicator at top (1/3, 2/3, 3/3)
Buttons: "Next" (Primary), "Back" (Text)
```

**Right: Contact Information**
```
Company Name
Address (with map pin icon)
Phone (click-to-call)
Email (click-to-email)
Business Hours

Map: Embedded Google Maps (interactive)

Social Links: Icon row
```

**Below Form: FAQ Section**
```
Accordion style:
  - "How do I request a quote?"
  - "What are your payment terms?"
  - "Do you ship to my country?"
  - "What certifications do you have?"
```

---

## Loading & Empty States

### Loading States

**Page Load:**
- Skeleton screens (gray blocks matching layout)
- No spinners (feels faster)

**Filtering:**
- Subtle opacity change
- Products stay visible, new ones fade in

**Form Submission:**
- Button: Disabled state, spinner replaces text
- No page reload, inline success message

### Empty States

**No Search Results:**
- Icon: Magnifying glass
- Message: "No products found"
- Suggestion: "Try different filters"
- CTA: "View All Products"

**No Items in Category:**
- Icon: Box or folder
- Message: "Coming Soon"
- CTA: "Browse Other Categories"

---

## Error Handling

### Form Errors

**Inline Validation:**
- Shows below field after blur
- Icon: Alert circle (Error-500)
- Text: Specific error (e.g., "Email format invalid")
- Border: Error-500

**Form-Level Errors:**
- Banner at top of form
- Icon + message
- List of errors with links to fields

### Page Errors

**404 Page:**
```
Illustration: Friendly, agricultural theme
H1: "Page Not Found"
Text: "The page you're looking for doesn't exist"
CTA Primary: "Go to Homepage"
CTA Secondary: "Browse Products"
```

**500 Error:**
```
Icon: Error symbol
H1: "Something Went Wrong"
Text: "We're working on it. Please try again."
CTA: "Reload Page"
Contact: "Or contact us at [email]"
```

---

## Performance Considerations

### Image Optimization

- WebP format with PNG/JPEG fallback
- Responsive images (srcset)
- Lazy loading below fold
- Blur placeholder while loading

### Code Splitting

- Route-based code splitting
- Lazy load non-critical components
- Defer non-essential JavaScript

### Font Loading

- System fonts as fallback
- Font-display: swap
- Preload critical fonts

### Third-Party Scripts

- Async loading for analytics
- Defer non-critical scripts
- Self-host where possible

---

## Dark Mode (Future Consideration)

**Not in MVP, but design system supports it:**

- All colors have dark mode variants defined
- Semantic color tokens (text-primary, bg-surface, etc.)
- Easy to implement later with CSS variables

---

## Handoff to Development

### What Developers Get

1. **This Document** - Complete design spec
2. **Figma Files** (if created) - High-fidelity mockups
3. **Component Library** - shadcn/ui + custom components
4. **Design Tokens** - Colors, spacing, typography in code format
5. **Icon Set** - Lucide React library

### Implementation Notes

**Priority Order:**
1. Design tokens (colors, typography, spacing)
2. Base components (buttons, inputs, cards)
3. Layout system (grid, spacing)
4. Page templates (homepage first)
5. Interactive components (filters, forms)
6. Animations and micro-interactions

**Quality Checkpoints:**
- Color contrast tested
- Font sizes match spec
- Spacing follows 8px grid
- Hover states implemented
- Mobile responsive
- Accessibility tested

---

## Design Rationale

### Why This Approach?

1. **Clean & Professional:** B2B buyers expect clarity, not flash
2. **Product-Focused:** Beautiful agricultural products are the stars
3. **Trust Signals:** Certifications and social proof prominently displayed
4. **Performance:** Fast load times signal reliability
5. **Accessible:** Inclusive design reaches more customers
6. **Maintainable:** Design system makes updates easy
7. **Scalable:** Can grow with Phase 2 features

### Design Principles Applied

✅ **Clarity Over Creativity** - Every element has a purpose  
✅ **Speed is Trust** - Optimized for performance  
✅ **Visual Quality Matters** - High-quality product photography  
✅ **Mobile-First** - 40% of traffic expected from mobile  
✅ **Trust Through Transparency** - Certifications, proof, honesty  

---

## Next Steps

1. **Review & Approve** this specification
2. **Create Figma Mockups** (optional but recommended) for key pages
3. **Develop Component Library** in code (shadcn/ui + custom)
4. **Build Homepage** as proof of concept
5. **Iterate** based on real content and feedback

---

_This UX Design Specification serves as the visual and interaction blueprint for the Alsoadaa Export Website. All design decisions are rooted in user needs, business goals, and technical constraints defined in the PRD._

_Designer: Sally | Date: 2025-10-25 | Version: 1.0_

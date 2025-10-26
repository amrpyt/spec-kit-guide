# Alsoadaa Export Website - Architecture Document

**Project:** Alsoadaa Export Website  
**Author:** Winston (Architect)  
**For:** Amr  
**Date:** 2025-10-25  
**Version:** 1.0  
**Project Level:** 2 (Medium Complexity)

---

## Executive Summary

This architecture leverages a modern, production-ready starter template (Payload CMS 3 + Next.js 15 + shadcn/ui) to build a multilingual B2B agricultural export website. The architecture prioritizes performance (Lighthouse >90), SEO optimization, and AI agent consistency through explicit implementation patterns.

**Key Architectural Approach:**
- **Starter-first:** Using proven template to establish 80% of architecture automatically
- **Pattern-driven:** Explicit conventions prevent AI agent conflicts during implementation
- **Performance-optimized:** Built-in image optimization, CDN, and SSR for <2s load times
- **SEO-ready:** Multilingual routing, schema markup, and sitemap generation included

**Project Scope:**
- 7 Epics with 15 User Stories
- 3 Languages (EN, RU, AR) with RTL support
- Medium complexity with unique seasonal availability features

---

## Project Initialization

### FIRST IMPLEMENTATION STEP: Clone and Setup Starter Template

```bash
# Clone the starter template
git clone https://github.com/mrtzdev/payload-next-shadcn.git alsoadaa-website

# Navigate to project
cd alsoadaa-website

# Install dependencies
pnpm install

# Configure environment variables
cp .env.example .env.local

# Edit .env.local with your database connection:
# DATABASE_URI=postgresql://amr:amr@156.67.25.212:6969/amr
# PAYLOAD_SECRET=your-32-char-secret-here

# Start development server
pnpm dev
```

### What the Starter Provides (Out of Box)

✅ **Next.js 15** with App Router  
✅ **Payload CMS 3.x** fully integrated  
✅ **TypeScript** with strict mode  
✅ **TailwindCSS** configured  
✅ **shadcn/ui** component library  
✅ **PostgreSQL** database adapter  
✅ **Admin panel** at `/admin`  
✅ **Hot reload** for frontend and CMS  
✅ **ESM** fully supported  
✅ **Turbopack** ready  

---

## Technology Decision Summary

| Category | Decision | Version | Rationale | Status |
|----------|----------|---------|-----------|--------|
| **Frontend Framework** | Next.js | 15.x | App Router, RSC, built-in optimization | Starter ✅ |
| **React** | React | 19.x | Latest stable, concurrent features | Starter ✅ |
| **CMS** | Payload CMS | 3.x | Next.js-native, type-safe, local API | Starter ✅ |
| **Language** | TypeScript | 5.x | Type safety, better DX, fewer bugs | Starter ✅ |
| **Database** | PostgreSQL | 15+ | Self-hosted at 156.67.25.212:6969 | Manual 🔧 |
| **Database Adapter** | @payloadcms/db-postgres | Latest | Official Payload PostgreSQL adapter | Starter ✅ |
| **Styling** | TailwindCSS | 3.x | Utility-first, fast development | Starter ✅ |
| **UI Components** | shadcn/ui | Latest | Accessible, customizable, no package deps | Starter ✅ |
| **Icons** | Lucide React | 0.460+ | Modern, consistent, tree-shakeable | Add 🔧 |
| **Internationalization** | next-intl | 3.15+ | App Router support, RTL, type-safe | Add 🔧 |
| **Form Management** | react-hook-form | 7.43+ | Performant, small bundle, great DX | Add 🔧 |
| **Form Validation** | zod | 3.23+ | Type-safe schemas, reusable validation | Add 🔧 |
| **File Storage** | Vercel Blob | Latest | Scalable, CDN-backed, generous free tier | Add 🔧 |
| **Image Optimization** | next/image | Built-in | Automatic WebP, lazy load, responsive | Starter ✅ |
| **Calendar Component** | react-big-calendar | 1.19+ | Seasonal availability visualization | Add 🔧 |
| **Deployment** | Vercel | N/A | Zero-config, edge network, automatic SSL | Hosting 🚀 |
| **Analytics** | Google Analytics 4 | N/A | Standard web analytics, event tracking | Add 🔧 |
| **SEO** | next-seo | 6.5+ | Meta tags, Open Graph, structured data | Add 🔧 |
| **Email Service** | None (MVP) | N/A | Deferred to Phase 2 | N/A ⏭️ |

**Legend:**
- ✅ = Provided by starter template (ready to use)
- 🔧 = Needs manual installation
- 🚀 = External service/hosting
- ⏭️ = Deferred/Not in current scope

---

## Additional Dependencies Installation

After cloning the starter, install these additional packages:

```bash
# Install all additional packages in one command
pnpm add lucide-react next-intl react-hook-form zod @hookform/resolvers @vercel/blob react-big-calendar next-seo sharp moment

# Install dev dependencies
pnpm add -D @types/react-big-calendar
```

**Package Purposes:**
- `lucide-react`: Icon library for UI consistency across the site
- `next-intl`: Internationalization with RTL support for Arabic
- `react-hook-form` + `zod` + `@hookform/resolvers`: Form handling and validation
- `@vercel/blob`: File storage integration for product images
- `react-big-calendar`: Base for seasonal calendar component
- `next-seo`: SEO meta tags and structured data generation
- `sharp`: Image processing (required by Payload CMS)
- `moment`: Date manipulation for calendar component

---

## Database Configuration

### Connection Details

**Database Type:** Self-hosted PostgreSQL  
**Connection String:** `postgresql://amr:amr@156.67.25.212:6969/amr`  

### Environment Variables

Create/update `.env.local` file:

```env
# Database Connection
DATABASE_URI=postgresql://amr:amr@156.67.25.212:6969/amr

# Payload CMS Secret (generate a 32-character random string)
PAYLOAD_SECRET=your-32-character-secret-key-here

# Server URL
NEXT_PUBLIC_SERVER_URL=http://localhost:3000

# Vercel Blob Storage (add after deployment)
BLOB_READ_WRITE_TOKEN=vercel_blob_token_here

# Google Analytics (add when ready)
NEXT_PUBLIC_GA_ID=G-XXXXXXXXXX
```

**Security Note:** Never commit `.env.local` to git. The `.gitignore` should already exclude it.

---

## Architecture Decision Records (ADRs)

### ADR-001: Starter Template Selection
**Decision:** Use `mrtzdev/payload-next-shadcn` starter template  
**Rationale:** Provides 80% of required tech stack out-of-box, actively maintained, includes shadcn/ui which matches UX requirements  
**Alternatives Considered:** 
- Official Payload starter (missing shadcn/ui)
- Build from scratch (too time-consuming for medium complexity project)  
**Trade-offs:** Less control over initial setup, potential unused features, but massive time savings

### ADR-002: Self-Hosted Database
**Decision:** Use self-hosted PostgreSQL at 156.67.25.212:6969  
**Rationale:** Client requirement, existing infrastructure already available  
**Alternatives Considered:** Supabase (free tier), Neon (serverless), Vercel Postgres  
**Trade-offs:** No automatic backups, manual scaling responsibility, potential network latency from Vercel edge to database

### ADR-003: next-intl for Internationalization
**Decision:** Use next-intl over next-i18next  
**Rationale:** Better App Router support, built-in RTL handling, type-safe translation keys  
**Alternatives Considered:** 
- next-i18next (primarily for Pages Router)
- Custom i18n solution (too complex, reinventing wheel)  
**Trade-offs:** Smaller community compared to next-i18next, fewer Stack Overflow answers

### ADR-004: Vercel Blob for File Storage
**Decision:** Use Vercel Blob over Cloudinary  
**Rationale:** Native Vercel integration, generous free tier (500GB bandwidth/month), simpler setup  
**Alternatives Considered:** 
- Cloudinary (more features but overkill for needs)
- Supabase Storage (adds another dependency)
- Local file storage (not scalable for production)  
**Trade-offs:** Vendor lock-in to Vercel ecosystem, fewer advanced image manipulation features

### ADR-005: react-big-calendar for Seasonal Display
**Decision:** Use react-big-calendar library adapted for seasonal availability  
**Rationale:** Mature library (8.5k+ stars), highly customizable, handles month/year display well  
**Alternatives Considered:** 
- fullcalendar (too heavy, commercial license)
- Custom build from scratch (time-consuming)  
**Trade-offs:** Requires significant customization since not designed for availability matrix, larger bundle size than needed

---

## Complete Project Structure

```
alsoadaa-website/
├── public/
│   ├── images/
│   │   ├── products/              # Product lifestyle photography
│   │   ├── certifications/        # ISO 22000, Global G.A.P badges
│   │   └── trust/                 # Company photos, shipment images
│   ├── fonts/                     # Custom fonts (if needed)
│   └── favicon.ico
│
├── src/
│   ├── app/
│   │   ├── (frontend)/           # Public-facing routes
│   │   │   └── [lang]/           # Language-based routing (en/ru/ar)
│   │   │       ├── layout.tsx    # Root layout with i18n
│   │   │       ├── page.tsx      # Homepage
│   │   │       ├── products/
│   │   │       │   ├── page.tsx              # Product catalog listing
│   │   │       │   └── [slug]/page.tsx       # Product detail pages
│   │   │       ├── about/page.tsx            # About us page
│   │   │       ├── contact/page.tsx          # Contact page
│   │   │       └── calendar/page.tsx         # Seasonal availability calendar
│   │   │
│   │   ├── (payload)/            # CMS routes (isolated group)
│   │   │   └── admin/[[...segments]]/page.tsx  # Payload admin panel
│   │   │
│   │   ├── api/                  # API route handlers
│   │   │   ├── contact/route.ts       # Contact form submission
│   │   │   └── quote/route.ts         # Quote request handler
│   │   │
│   │   └── layout.tsx            # Global root layout
│   │
│   ├── components/
│   │   ├── ui/                   # shadcn/ui components (pre-installed)
│   │   │   ├── button.tsx
│   │   │   ├── input.tsx
│   │   │   ├── form.tsx
│   │   │   ├── card.tsx
│   │   │   ├── select.tsx
│   │   │   └── ... (other shadcn components)
│   │   │
│   │   ├── layout/               # Layout components
│   │   │   ├── Header.tsx             # Site header with navigation
│   │   │   ├── Footer.tsx             # Site footer
│   │   │   ├── LanguageSwitcher.tsx   # Language selector dropdown
│   │   │   └── MobileMenu.tsx         # Mobile navigation drawer
│   │   │
│   │   ├── product/              # Product-related components
│   │   │   ├── ProductCard.tsx        # Product grid card
│   │   │   ├── ProductGrid.tsx        # Product listing grid container
│   │   │   ├── ProductFilters.tsx     # Filter sidebar (category, season)
│   │   │   ├── ProductDetail.tsx      # Product detail view
│   │   │   └── ProductGallery.tsx     # Image gallery with thumbnails
│   │   │
│   │   ├── calendar/             # Seasonal calendar components
│   │   │   ├── SeasonalCalendar.tsx       # Main calendar container
│   │   │   ├── ProductSeasonView.tsx      # Product × Month matrix view
│   │   │   ├── MonthSeasonView.tsx        # Monthly product list view
│   │   │   ├── CalendarLegend.tsx         # Color legend
│   │   │   └── AvailabilityIndicator.tsx  # Status badge component
│   │   │
│   │   ├── forms/                # Form components
│   │   │   ├── QuoteRequestForm.tsx   # Multi-step quote form
│   │   │   ├── CallbackForm.tsx       # Callback scheduler
│   │   │   ├── ContactForm.tsx        # Simple contact form
│   │   │   └── FormStep.tsx           # Multi-step form wrapper
│   │   │
│   │   ├── trust/                # Trust signal components
│   │   │   ├── CertificationBadge.tsx     # Certification display
│   │   │   ├── Testimonial.tsx            # Customer testimonial card
│   │   │   ├── StatsBar.tsx               # Company statistics banner
│   │   │   └── Timeline.tsx               # Company history timeline
│   │   │
│   │   └── shared/               # Shared/common components
│   │       ├── Loading.tsx            # Loading states and spinners
│   │       ├── ErrorBoundary.tsx      # Error handling wrapper
│   │       ├── SEOHead.tsx            # SEO meta tags component
│   │       └── OptimizedImage.tsx     # next/image wrapper with defaults
│   │
│   ├── payload/                  # Payload CMS configuration
│   │   ├── payload.config.ts     # Main Payload config file
│   │   │
│   │   ├── collections/          # Content type definitions
│   │   │   ├── Products.ts            # Product collection
│   │   │   ├── Categories.ts          # Product categories
│   │   │   ├── Media.ts               # Media library/uploads
│   │   │   ├── Users.ts               # Admin users
│   │   │   ├── Pages.ts               # Static pages (About, etc.)
│   │   │   ├── QuoteRequests.ts       # Quote form submissions
│   │   │   ├── Certifications.ts      # Quality certifications
│   │   │   └── Testimonials.ts        # Customer testimonials
│   │   │
│   │   ├── globals/              # Global singletons
│   │   │   ├── SiteSettings.ts        # Site-wide settings
│   │   │   └── Navigation.ts          # Navigation menu structure
│   │   │
│   │   ├── fields/               # Reusable field configurations
│   │   │   ├── seo.ts                 # SEO field group
│   │   │   ├── availability.ts        # Seasonal availability fields
│   │   │   └── localized.ts           # i18n field wrapper
│   │   │
│   │   └── access/               # Access control rules
│   │       ├── isAdmin.ts             # Admin-only access
│   │       └── isPublished.ts         # Published content filter
│   │
│   ├── lib/                      # Utility functions and helpers
│   │   ├── payload.ts                 # Payload client initialization
│   │   ├── i18n.ts                    # i18n configuration and utilities
│   │   ├── seo.ts                     # SEO helper functions
│   │   ├── validators.ts              # Zod validation schemas
│   │   └── utils.ts                   # General utilities (cn, formatters)
│   │
│   ├── styles/
│   │   └── globals.css                # Tailwind imports + custom CSS
│   │
│   ├── types/                    # TypeScript type definitions
│   │   ├── payload-types.ts           # Auto-generated from Payload
│   │   ├── product.ts                 # Product-related types
│   │   ├── forms.ts                   # Form types
│   │   └── index.ts                   # Barrel exports
│   │
│   └── middleware.ts             # Next.js middleware (i18n routing)
│
├── messages/                     # i18n translation files
│   ├── en.json                   # English translations
│   ├── ru.json                   # Russian translations
│   └── ar.json                   # Arabic translations (RTL)
│
├── .env.local                    # Local environment variables (not in git)
├── .env.example                  # Example environment template
├── .gitignore
├── next.config.js                # Next.js configuration
├── tailwind.config.ts            # Tailwind CSS configuration
├── tsconfig.json                 # TypeScript configuration
├── package.json                  # Dependencies and scripts
├── pnpm-lock.yaml                # Package lock file
└── README.md                     # Project documentation
```

### Key Directory Purposes

**`app/(frontend)/[lang]/`**: All user-facing pages with language prefix routing  
**`app/(payload)/`**: Isolated CMS admin routes (won't interfere with frontend)  
**`components/ui/`**: Pre-built shadcn/ui components (don't modify, regenerate from CLI)  
**`payload/collections/`**: Define your content models here (Products, Categories, etc.)  
**`messages/`**: Translation JSON files for all 3 languages  
**`lib/`**: Shared utility functions and business logic  

---

## Epic to Architecture Mapping

| Epic | Primary Components | Payload Collections | Key Technical Features |
|------|-------------------|---------------------|------------------------|
| **Epic 1: Foundation & Setup** | Layout, Header, Footer, Navigation | Users, SiteSettings, Navigation | Project initialization, admin panel setup, basic routing structure |
| **Epic 2: Product Catalog** | ProductCard, ProductGrid, ProductFilters, ProductDetail | Products, Categories, Media | CRUD operations, filtering/search, image optimization, pagination |
| **Epic 3: Multi-language Support** | LanguageSwitcher, i18n middleware, RTL layout | Localized fields in all collections | EN/RU/AR routing, RTL CSS, hreflang tags, language detection |
| **Epic 4: Forms & Communication** | QuoteRequestForm, CallbackForm, ContactForm | QuoteRequests, Callbacks | Multi-step forms, Zod validation, email notifications (Phase 2) |
| **Epic 5: Performance & SEO** | SEOHead, Image optimization, Sitemap generation | N/A (meta fields in all collections) | Schema markup, XML sitemap, Google Analytics 4, Core Web Vitals monitoring |
| **Epic 6: Trust & Social Proof** | CertificationBadge, Testimonial, Timeline, StatsBar | Certifications, Testimonials | Trust badges, customer reviews, company history, statistics display |
| **Epic 7: Testing & Launch** | ErrorBoundary, Loading states, E2E tests | N/A | QA process, production deployment, monitoring setup |

---

## Implementation Patterns (CRITICAL for AI Agent Consistency)

These patterns are **MANDATORY** for all code implementation. Following these conventions prevents conflicts when multiple AI agents or developers work on the same codebase.

### 1. Naming Conventions

**API Routes:**
- Format: `/api/[resource]` (kebab-case, plural for collections)
- Examples: `/api/products`, `/api/quote-requests`, `/api/categories`
- HTTP Methods: Use Next.js conventions (POST for create, GET for read)

**Database Collections (Payload):**
- Format: PascalCase, singular
- Examples: `Products`, `QuoteRequests`, `Media`, `Categories`
- Foreign keys: camelCase with `Id` suffix (e.g., `categoryId`, `userId`)

**Components:**
- Files: `ComponentName.tsx` (PascalCase)
- Examples: `ProductCard.tsx`, `QuoteRequestForm.tsx`, `LanguageSwitcher.tsx`
- Tests: `ComponentName.test.tsx` (co-located with component)

**Folders:**
- Route folders: kebab-case (e.g., `/products`, `/quote-requests`)
- Component folders: lowercase (e.g., `components/product`, `components/forms`)

**Variables and Functions:**
- Format: camelCase for variables and functions
- Constants: SCREAMING_SNAKE_CASE
- Examples: `const productList = ...`, `const MAX_FILE_SIZE = 5 * 1024 * 1024`

### 2. File Organization

**Component Co-location:**
```
components/product/
├── ProductCard.tsx
├── ProductCard.test.tsx      # Test file next to component
├── ProductCard.module.css    # Styles if needed (use Tailwind instead)
└── types.ts                  # Component-specific types
```

**Import Order (MANDATORY):**
```typescript
// 1. External dependencies
import { useState } from 'react';
import { useTranslations } from 'next-intl';

// 2. Internal modules (@ aliases)
import { Button } from '@/components/ui/button';
import { ProductCard } from '@/components/product/ProductCard';

// 3. Types
import type { Product } from '@/types/product';

// 4. Relative imports (avoid when possible)
import './styles.css';
```

**Path Aliases (configured in tsconfig.json):**
- `@/components/*` → `src/components`
- `@/lib/*` → `src/lib`
- `@/payload/*` → `src/payload`
- `@/types/*` → `src/types`

### 3. API Response Format

**Success Response:**
```typescript
{
  success: true,
  data: any,              // Response payload
  message?: string        // Optional success message
}
```

**Error Response:**
```typescript
{
  success: false,
  error: {
    code: string,         // Error code (e.g., 'VALIDATION_ERROR')
    message: string,      // Human-readable error message
    details?: any         // Optional additional context
  }
}
```

**Paginated Response:**
```typescript
{
  success: true,
  data: Product[],
  pagination: {
    total: number,        // Total items
    page: number,         // Current page (1-indexed)
    pageSize: number,     // Items per page
    totalPages: number    // Total pages
  }
}
```

### 4. Error Handling Pattern

**Try-Catch with Typed Errors:**
```typescript
import { ValidationError, DatabaseError } from '@/lib/errors';

try {
  // Operation
  const result = await someOperation();
  return { success: true, data: result };
} catch (error) {
  if (error instanceof ValidationError) {
    return { 
      success: false, 
      error: { code: 'VALIDATION_ERROR', message: error.message } 
    };
  } else if (error instanceof DatabaseError) {
    return { 
      success: false, 
      error: { code: 'DATABASE_ERROR', message: 'Failed to access database' } 
    };
  } else {
    console.error('Unexpected error:', error);
    return { 
      success: false, 
      error: { code: 'UNKNOWN_ERROR', message: 'An unexpected error occurred' } 
    };
  }
}
```

**HTTP Status Codes:**
- `200`: Success
- `400`: Bad Request (validation errors)
- `401`: Unauthorized
- `404`: Not Found
- `500`: Internal Server Error

### 5. Form Handling Pattern

**ALL forms MUST use:**
- `react-hook-form` for form state management
- `zod` for validation schemas
- `@hookform/resolvers/zod` for integration

**Example:**
```typescript
import { useForm } from 'react-hook-form';
import { zodResolver } from '@hookform/resolvers/zod';
import { z } from 'zod';

// Define schema
const quoteSchema = z.object({
  email: z.string().email('Invalid email address'),
  name: z.string().min(2, 'Name must be at least 2 characters'),
  quantity: z.number().positive('Quantity must be positive')
});

type QuoteFormData = z.infer<typeof quoteSchema>;

// In component
const form = useForm<QuoteFormData>({
  resolver: zodResolver(quoteSchema),
  defaultValues: {
    email: '',
    name: '',
    quantity: 1
  }
});

const onSubmit = async (data: QuoteFormData) => {
  // Handle submission
};
```

### 6. State Management Pattern

**Server Components (Default):**
- Use React Server Components for data fetching
- Pass data as props to Client Components
- **NO** `useState` or `useEffect` in Server Components

**Client Components (When Needed):**
- Add `'use client'` directive at top of file
- Use for: forms, animations, browser APIs, interactivity

**Example:**
```typescript
// ❌ WRONG - Server Component with useState
export default function ProductList() {
  const [products, setProducts] = useState([]); // Error!
  return <div>...</div>;
}

// ✅ CORRECT - Server Component fetching data
export default async function ProductList() {
  const products = await payload.find({ collection: 'products' });
  return <ProductGrid products={products.docs} />;
}

// ✅ CORRECT - Client Component with state
'use client';
export default function ProductFilters() {
  const [selected, setSelected] = useState('all');
  return <div>...</div>;
}
```

### 7. Date and Time Handling

**Storage:**
- Always store in UTC using ISO 8601 format
- Example: `2025-10-25T00:00:00.000Z`

**Display:**
- Use `Intl.DateTimeFormat` with user's locale
- Never hardcode date formats

**Example:**
```typescript
// Storage (always UTC)
const createdAt = new Date().toISOString();

// Display (localized)
const locale = 'en-US'; // or 'ru-RU', 'ar-EG'
const formatter = new Intl.DateTimeFormat(locale, {
  year: 'numeric',
  month: 'long',
  day: 'numeric',
  hour: '2-digit',
  minute: '2-digit'
});

const displayDate = formatter.format(new Date(createdAt));
```

### 8. Loading States Pattern

**Use Suspense Boundaries:**
```typescript
import { Suspense } from 'react';
import { ProductCardSkeleton } from '@/components/shared/Loading';

<Suspense fallback={<ProductCardSkeleton />}>
  <ProductCard product={product} />
</Suspense>
```

**Button Loading:**
```typescript
<Button disabled={isLoading}>
  {isLoading ? (
    <>
      <Loader2 className="mr-2 h-4 w-4 animate-spin" />
      Loading...
    </>
  ) : (
    'Submit'
  )}
</Button>
```

**Skeleton Screens:**
- Use for initial page load
- Match layout of actual content
- Use gray-200 background with shimmer animation

### 9. Image Optimization Pattern

**ALWAYS use next/image:**
```typescript
import Image from 'next/image';

<Image
  src={product.mainImage.url}
  alt={product.name}
  width={800}
  height={600}
  quality={85}
  loading="lazy"
  placeholder="blur"
  blurDataURL={product.mainImage.blurhash}
  className="rounded-lg"
/>
```

**❌ NEVER use:**
```typescript
<img src={url} /> // No!
```

### 10. Internationalization Pattern

**ALWAYS use translation keys:**
```typescript
import { useTranslations } from 'next-intl';

export function ProductCard({ product }: Props) {
  const t = useTranslations('Products');
  
  return (
    <div>
      <h2>{t('title')}</h2>
      <p>{t('description')}</p>
      <Button>{t('addToQuote')}</Button>
    </div>
  );
}
```

**❌ NEVER hardcode text:**
```typescript
// ❌ WRONG
<Button>Add to Quote</Button>

// ✅ CORRECT
<Button>{t('addToQuote')}</Button>
```

---

## CRITICAL Rules for AI Agents

### 🚫 NEVER DO THESE:

1. **NEVER hardcode text** - Always use `useTranslations()` from next-intl
2. **NEVER use `<img>` tags** - Always use `next/image` component
3. **NEVER use left/right in CSS** - Use logical properties (inline-start/end) for RTL support
4. **NEVER create forms without Zod validation** - All forms must have schemas
5. **NEVER use `useState` in Server Components** - Add `'use client'` if needed
6. **NEVER commit `.env.local`** - Always use `.env.example` as template
7. **NEVER modify shadcn/ui components** - Regenerate or wrap them instead
8. **NEVER make direct database queries** - Use Payload local API
9. **NEVER skip error handling** - Always use try-catch with typed errors
10. **NEVER ignore loading states** - Always show loading UI for async operations

### ✅ ALWAYS DO THESE:

1. **ALWAYS use TypeScript** - No plain JavaScript files
2. **ALWAYS use Zod for form validation**
3. **ALWAYS use next/image for images**
4. **ALWAYS use logical CSS properties** (inline-start, inline-end)
5. **ALWAYS use shadcn/ui components** when available
6. **ALWAYS use Payload collections** for data
7. **ALWAYS use Server Components** by default
8. **ALWAYS follow naming conventions** (PascalCase for components, camelCase for functions)
9. **ALWAYS handle loading states** with Suspense or skeletons
10. **ALWAYS add proper error handling**

### Code Review Checklist

Before implementing ANY code, verify:

- [ ] All text uses translation keys?
- [ ] Forms use react-hook-form + zod?
- [ ] Images use next/image component?
- [ ] CSS uses logical properties?
- [ ] Error handling implemented?
- [ ] Loading states added?
- [ ] TypeScript types defined?
- [ ] Import order correct?
- [ ] No console.logs left?
- [ ] Component exported correctly?

---

## Novel Pattern 1: Multilingual Routing with RTL Support

**Challenge:** The website must support 3 languages (English, Russian, Arabic) with Arabic requiring right-to-left (RTL) layout. This is not a standard pattern and requires custom architectural design to ensure proper routing, SEO, and visual consistency.

### Pattern Name: Language-First Routing with Directional Layout

**Purpose:** Provide seamless language switching while maintaining SEO, proper RTL layout, and consistent user experience across all languages.

### URL Structure

```
/en/               → English (LTR)
/en/products       → English product catalog
/en/products/[slug] → English product detail

/ru/               → Russian (LTR)
/ru/products       → Russian product catalog

/ar/               → Arabic (RTL)
/ar/products       → Arabic product catalog (flipped layout)
```

### Implementation Steps

**1. Middleware Configuration**

File: `src/middleware.ts`
```typescript
import createMiddleware from 'next-intl/middleware';

export default createMiddleware({
  // Supported locales
  locales: ['en', 'ru', 'ar'],
  
  // Default locale (fallback)
  defaultLocale: 'en',
  
  // Always show locale in URL
  localePrefix: 'always',
  
  // Detect locale from browser
  localeDetection: true
});

export const config = {
  // Match all pathnames except static files and API routes
  matcher: ['/((?!api|_next|_vercel|.*\\..*).*)']
};
```

**2. i18n Configuration**

File: `src/i18n.ts`
```typescript
import { getRequestConfig } from 'next-intl/server';
import { notFound } from 'next/navigation';

export const locales = ['en', 'ru', 'ar'] as const;
export type Locale = (typeof locales)[number];

// RTL languages
export const rtlLocales: Locale[] = ['ar'];

export default getRequestConfig(async ({ locale }) => {
  // Validate that the incoming locale parameter is valid
  if (!locales.includes(locale as Locale)) notFound();

  return {
    messages: (await import(`../messages/${locale}.json`)).default,
    timeZone: 'Africa/Cairo',  // Egypt timezone
    now: new Date()
  };
});
```

**3. Root Layout with Direction**

File: `src/app/[lang]/layout.tsx`
```typescript
import { NextIntlClientProvider } from 'next-intl';
import { getMessages } from 'next-intl/server';
import { rtlLocales, type Locale } from '@/i18n';
import { notFound } from 'next/navigation';

export default async function LocaleLayout({
  children,
  params: { lang }
}: {
  children: React.ReactNode;
  params: { lang: string };
}) {
  // Validate locale
  if (!['en', 'ru', 'ar'].includes(lang)) {
    notFound();
  }

  const messages = await getMessages();
  const direction = rtlLocales.includes(lang as Locale) ? 'rtl' : 'ltr';

  return (
    <html lang={lang} dir={direction}>
      <body className={cn('font-sans antialiased', direction === 'rtl' && 'rtl')}>
        <NextIntlClientProvider messages={messages}>
          {children}
        </NextIntlClientProvider>
      </body>
    </html>
  );
}

// Generate static params for all languages
export function generateStaticParams() {
  return [
    { lang: 'en' },
    { lang: 'ru' },
    { lang: 'ar' }
  ];
}
```

**4. Translation File Structure**

File: `messages/en.json`
```json
{
  "HomePage": {
    "hero": {
      "title": "Fresh Egyptian Citrus to Your Market in 48 Hours",
      "subtitle": "Premium quality fruits and vegetables directly from source",
      "cta": "Request Quote"
    }
  },
  "Products": {
    "title": "Our Products",
    "filter": {
      "season": "Filter by Season",
      "category": "Filter by Category",
      "all": "All Products"
    },
    "addToQuote": "Add to Quote",
    "viewDetails": "View Details"
  },
  "Common": {
    "loading": "Loading...",
    "error": "Something went wrong",
    "tryAgain": "Try Again"
  }
}
```

File: `messages/ar.json` (with culturally appropriate translations)
```json
{
  "HomePage": {
    "hero": {
      "title": "حمضيات مصرية طازجة إلى سوقك في 48 ساعة",
      "subtitle": "فواكه وخضروات بجودة ممتازة مباشرة من المصدر",
      "cta": "طلب عرض سعر"
    }
  },
  "Products": {
    "title": "منتجاتنا",
    "filter": {
      "season": "فلترة حسب الموسم",
      "category": "فلترة حسب الفئة",
      "all": "جميع المنتجات"
    },
    "addToQuote": "أضف لطلب السعر",
    "viewDetails": "عرض التفاصيل"
  },
  "Common": {
    "loading": "جاري التحميل...",
    "error": "حدث خطأ ما",
    "tryAgain": "حاول مرة أخرى"
  }
}
```

**5. Component Usage**

```typescript
'use client';

import { useTranslations } from 'next-intl';
import { Button } from '@/components/ui/button';

export function ProductCard({ product }: { product: Product }) {
  const t = useTranslations('Products');
  
  return (
    <div className="card">
      <h3>{product.name}</h3>
      <p>{product.description}</p>
      <Button>{t('addToQuote')}</Button>
    </div>
  );
}
```

**6. Language Switcher Component**

File: `src/components/layout/LanguageSwitcher.tsx`
```typescript
'use client';

import { useLocale } from 'next-intl';
import { usePathname, useRouter } from 'next/navigation';
import { Globe } from 'lucide-react';
import {
  DropdownMenu,
  DropdownMenuContent,
  DropdownMenuItem,
  DropdownMenuTrigger,
} from '@/components/ui/dropdown-menu';
import { Button } from '@/components/ui/button';

const languages = [
  { code: 'en', name: 'English', flag: '🇬🇧' },
  { code: 'ru', name: 'Русский', flag: '🇷🇺' },
  { code: 'ar', name: 'العربية', flag: '🇪🇬' }
];

export function LanguageSwitcher() {
  const locale = useLocale();
  const router = useRouter();
  const pathname = usePathname();

  const switchLanguage = (newLocale: string) => {
    // Replace locale in pathname
    const segments = pathname.split('/');
    segments[1] = newLocale;
    const newPath = segments.join('/');
    router.push(newPath);
  };

  const currentLanguage = languages.find(lang => lang.code === locale);

  return (
    <DropdownMenu>
      <DropdownMenuTrigger asChild>
        <Button variant="outline" size="sm">
          <Globe className="mr-2 h-4 w-4" />
          {currentLanguage?.flag} {currentLanguage?.name}
        </Button>
      </DropdownMenuTrigger>
      <DropdownMenuContent align="end">
        {languages.map((lang) => (
          <DropdownMenuItem
            key={lang.code}
            onClick={() => switchLanguage(lang.code)}
            className={locale === lang.code ? 'bg-accent' : ''}
          >
            {lang.flag} {lang.name}
          </DropdownMenuItem>
        ))}
      </DropdownMenuContent>
    </DropdownMenu>
  );
}
```

### SEO Implementation

**hreflang Tags:**

File: `src/components/shared/SEOHead.tsx`
```typescript
import { useLocale } from 'next-intl';

export function SEOHead({ path }: { path: string }) {
  const locale = useLocale();
  const baseUrl = process.env.NEXT_PUBLIC_SERVER_URL;

  return (
    <>
      <link rel="alternate" hrefLang="en" href={`${baseUrl}/en${path}`} />
      <link rel="alternate" hrefLang="ru" href={`${baseUrl}/ru${path}`} />
      <link rel="alternate" hrefLang="ar" href={`${baseUrl}/ar${path}`} />
      <link rel="alternate" hrefLang="x-default" href={`${baseUrl}/en${path}`} />
    </>
  );
}
```

### RTL CSS Handling

**Automatic Mirroring with Logical Properties:**

```css
/* globals.css */

/* Tailwind automatically handles most RTL with dir="rtl" */
/* Use logical properties for manual control */

.container {
  /* ✅ Good - automatically flips */
  margin-inline-start: 1rem;
  margin-inline-end: 2rem;
  padding-inline: 1.5rem;
  border-inline-start: 1px solid #ccc;
  
  /* ❌ Avoid - doesn't flip automatically */
  /* margin-left: 1rem; */
  /* margin-right: 2rem; */
}

/* RTL-specific overrides when needed */
[dir="rtl"] .special-case {
  text-align: right;
}
```

**Tailwind with RTL:**

```typescript
// Component using Tailwind classes
<div className={cn(
  "flex items-center gap-4",
  // Most Tailwind classes work automatically with dir="rtl"
  "ps-4 pe-6",  // padding-inline-start and padding-inline-end
  "border-s-2"  // border-inline-start
)}>
  <span>Content</span>
</div>
```

### Payload CMS Localization

**Localized Fields in Collections:**

File: `src/payload/collections/Products.ts`
```typescript
import { CollectionConfig } from 'payload/types';

export const Products: CollectionConfig = {
  slug: 'products',
  fields: [
    {
      name: 'name',
      type: 'text',
      required: true,
      localized: true,  // ✅ Enable translation
    },
    {
      name: 'description',
      type: 'richText',
      localized: true,
    },
    {
      name: 'scientificName',
      type: 'text',
      localized: false,  // ❌ Same in all languages
    },
    {
      name: 'seo',
      type: 'group',
      fields: [
        {
          name: 'title',
          type: 'text',
          localized: true,
        },
        {
          name: 'description',
          type: 'textarea',
          localized: true,
        }
      ]
    }
  ]
};
```

### AI Agent Rules for i18n

1. ✅ **ALWAYS** use `useTranslations()` hook - NEVER hardcode text
2. ✅ **ALWAYS** use logical CSS properties (inline-start/end, inline)
3. ✅ All user-facing text must exist in all 3 language files (en/ru/ar.json)
4. ✅ Test RTL layout by manually setting `lang="ar"` in HTML
5. ✅ Use `<html dir="rtl">` for Arabic, not CSS
6. ❌ **NEVER** concatenate translated strings (use ICU message format)
7. ❌ **NEVER** use left/right CSS unless absolutely necessary
8. ❌ **NEVER** assume text direction - always use logical properties

### Edge Cases and Failure Modes

**Scenario: Missing Translation Key**
- Fallback to default locale (English)
- Log warning in development mode
- Display key name with brackets in dev: `[MissingKey]`

**Scenario: URL without locale prefix**
- Middleware redirects to default locale
- Example: `/products` → `/en/products`

**Scenario: Invalid locale in URL**
- Return 404 Not Found page
- Middleware handles validation before page loads

**Scenario: RTL layout breaks with complex CSS**
- Use `[dir="rtl"]` selector for manual overrides
- Document any RTL-specific CSS in component comments

---

## Novel Pattern 2: Seasonal Availability Calendar

**Challenge:** Display product availability by month in a visual calendar format, allowing buyers to plan procurement based on seasonal availability. This requires a custom matrix view showing products vs. months.

### Pattern Name: Product-Season Matrix Calendar

**Purpose:** Enable B2B buyers to quickly understand when products are available throughout the year, supporting seasonal procurement planning and order timing.

### Data Model

**Product Collection - Availability Fields:**

```typescript
// In Payload Products collection
{
  slug: 'navel-orange',
  name: { en: 'Navel Orange', ru: '...', ar: '...' },
  availability: {
    january: true,
    february: true,
    march: true,
    april: false,
    may: false,
    june: false,
    july: false,
    august: false,
    september: false,
    october: false,
    november: true,
    december: true
  },
  // Auto-calculated based on current date and availability
  availabilityStatus: 'available' | 'coming_soon' | 'out_of_season'
}
```

### Component Architecture

**1. Main Calendar Container**

File: `src/components/calendar/SeasonalCalendar.tsx`
```typescript
'use client';

import { useState } from 'react';
import { useTranslations } from 'next-intl';
import { ProductSeasonView } from './ProductSeasonView';
import { MonthSeasonView } from './MonthSeasonView';
import { CalendarLegend } from './CalendarLegend';
import { Button } from '@/components/ui/button';
import type { Product } from '@/types/product';

interface Props {
  products: Product[];
}

export function SeasonalCalendar({ products }: Props) {
  const [view, setView] = useState<'product' | 'month'>('product');
  const t = useTranslations('Calendar');

  return (
    <div className="space-y-6">
      {/* View Toggle */}
      <div className="flex justify-between items-center">
        <h2 className="text-2xl font-bold">{t('title')}</h2>
        <div className="flex gap-2">
          <Button
            variant={view === 'product' ? 'default' : 'outline'}
            onClick={() => setView('product')}
          >
            {t('viewByProduct')}
          </Button>
          <Button
            variant={view === 'month' ? 'default' : 'outline'}
            onClick={() => setView('month')}
          >
            {t('viewByMonth')}
          </Button>
        </div>
      </div>

      {/* Calendar View */}
      {view === 'product' ? (
        <ProductSeasonView products={products} />
      ) : (
        <MonthSeasonView products={products} />
      )}

      {/* Legend */}
      <CalendarLegend />
    </div>
  );
}
```

**2. Product-Month Matrix View**

File: `src/components/calendar/ProductSeasonView.tsx`
```typescript
'use client';

import { useTranslations } from 'next-intl';
import { AvailabilityIndicator } from './AvailabilityIndicator';
import type { Product } from '@/types/product';

const MONTHS = [
  'january', 'february', 'march', 'april', 'may', 'june',
  'july', 'august', 'september', 'october', 'november', 'december'
] as const;

export function ProductSeasonView({ products }: { products: Product[] }) {
  const t = useTranslations('Calendar');

  return (
    <div className="overflow-x-auto">
      <table className="w-full border-collapse">
        <thead>
          <tr className="bg-muted">
            <th className="p-3 text-left font-semibold sticky left-0 bg-muted z-10">
              {t('product')}
            </th>
            {MONTHS.map((month) => (
              <th key={month} className="p-3 text-center font-medium">
                {t(`months.${month}.short`)}
              </th>
            ))}
          </tr>
        </thead>
        <tbody>
          {products.map((product) => (
            <tr key={product.id} className="border-b hover:bg-muted/50">
              <td className="p-3 font-medium sticky left-0 bg-background z-10">
                {product.name}
              </td>
              {MONTHS.map((month) => (
                <td key={month} className="p-3 text-center">
                  <AvailabilityIndicator
                    available={product.availability[month]}
                    size="md"
                  />
                </td>
              ))}
            </tr>
          ))}
        </tbody>
      </table>
    </div>
  );
}
```

**3. Month-Based List View**

File: `src/components/calendar/MonthSeasonView.tsx`
```typescript
'use client';

import { useState } from 'react';
import { useTranslations } from 'next-intl';
import { ProductCard } from '@/components/product/ProductCard';
import {
  Select,
  SelectContent,
  SelectItem,
  SelectTrigger,
  SelectValue,
} from '@/components/ui/select';
import type { Product } from '@/types/product';

const MONTHS = [
  'january', 'february', 'march', 'april', 'may', 'june',
  'july', 'august', 'september', 'october', 'november', 'december'
] as const;

export function MonthSeasonView({ products }: { products: Product[] }) {
  const currentMonth = MONTHS[new Date().getMonth()];
  const [selectedMonth, setSelectedMonth] = useState(currentMonth);
  const t = useTranslations('Calendar');

  // Filter products available in selected month
  const availableProducts = products.filter(
    (p) => p.availability[selectedMonth]
  );

  return (
    <div className="space-y-6">
      {/* Month Selector */}
      <div className="flex items-center gap-4">
        <label className="font-medium">{t('selectMonth')}</label>
        <Select value={selectedMonth} onValueChange={setSelectedMonth}>
          <SelectTrigger className="w-[200px]">
            <SelectValue />
          </SelectTrigger>
          <SelectContent>
            {MONTHS.map((month) => (
              <SelectItem key={month} value={month}>
                {t(`months.${month}.full`)}
              </SelectItem>
            ))}
          </SelectContent>
        </Select>
      </div>

      {/* Products Grid */}
      {availableProducts.length > 0 ? (
        <div className="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-6">
          {availableProducts.map((product) => (
            <ProductCard key={product.id} product={product} />
          ))}
        </div>
      ) : (
        <div className="text-center py-12 text-muted-foreground">
          {t('noProducts')}
        </div>
      )}

      <p className="text-sm text-muted-foreground">
        {t('productsAvailable', { count: availableProducts.length })}
      </p>
    </div>
  );
}
```

**4. Availability Indicator Component**

File: `src/components/calendar/AvailabilityIndicator.tsx`
```typescript
import { cn } from '@/lib/utils';
import { Check, X } from 'lucide-react';

interface Props {
  available: boolean;
  size?: 'sm' | 'md' | 'lg';
}

export function AvailabilityIndicator({ available, size = 'md' }: Props) {
  const sizeClasses = {
    sm: 'w-6 h-6',
    md: 'w-8 h-8',
    lg: 'w-10 h-10'
  };

  const iconSize = {
    sm: 12,
    md: 16,
    lg: 20
  };

  return (
    <div
      className={cn(
        'rounded-full flex items-center justify-center',
        sizeClasses[size],
        available
          ? 'bg-green-500 text-white'
          : 'bg-gray-300 text-gray-500'
      )}
      title={available ? 'Available' : 'Not Available'}
    >
      {available ? (
        <Check size={iconSize[size]} />
      ) : (
        <X size={iconSize[size]} />
      )}
    </div>
  );
}
```

**5. Calendar Legend**

File: `src/components/calendar/CalendarLegend.tsx`
```typescript
import { useTranslations } from 'next-intl';
import { AvailabilityIndicator } from './AvailabilityIndicator';

export function CalendarLegend() {
  const t = useTranslations('Calendar');

  return (
    <div className="flex items-center gap-6 p-4 bg-muted rounded-lg">
      <span className="font-medium">{t('legend.title')}:</span>
      
      <div className="flex items-center gap-2">
        <AvailabilityIndicator available={true} size="sm" />
        <span className="text-sm">{t('legend.available')}</span>
      </div>

      <div className="flex items-center gap-2">
        <AvailabilityIndicator available={false} size="sm" />
        <span className="text-sm">{t('legend.notAvailable')}</span>
      </div>
    </div>
  );
}
```

### Integration with Product Pages

**Product Detail Page - Availability Timeline:**

File: `src/app/[lang]/products/[slug]/page.tsx`
```typescript
import { SeasonalTimeline } from '@/components/calendar/SeasonalTimeline';

export default async function ProductDetailPage({ params }) {
  const product = await getProduct(params.slug);

  return (
    <div>
      {/* Product details */}
      
      {/* Seasonal Availability Section */}
      <section className="mt-8">
        <h2>Seasonal Availability</h2>
        <SeasonalTimeline availability={product.availability} />
      </section>

      {/* Current Status Badge */}
      {product.availabilityStatus === 'available' && (
        <Badge variant="success">Available Now</Badge>
      )}
      {product.availabilityStatus === 'out_of_season' && (
        <Badge variant="destructive">Out of Season</Badge>
      )}
    </div>
  );
}
```

**Seasonal Timeline Component:**

File: `src/components/calendar/SeasonalTimeline.tsx`
```typescript
'use client';

import { useTranslations } from 'next-intl';
import { cn } from '@/lib/utils';

const MONTHS = [
  'Jan', 'Feb', 'Mar', 'Apr', 'May', 'Jun',
  'Jul', 'Aug', 'Sep', 'Oct', 'Nov', 'Dec'
];

interface Props {
  availability: Record<string, boolean>;
}

export function SeasonalTimeline({ availability }: Props) {
  const t = useTranslations('Calendar');
  const currentMonth = new Date().getMonth();

  return (
    <div className="flex gap-1">
      {MONTHS.map((month, index) => (
        <div
          key={month}
          className={cn(
            'flex-1 h-12 flex items-center justify-center rounded text-xs font-medium',
            availability[Object.keys(availability)[index]]
              ? 'bg-green-500 text-white'
              : 'bg-gray-200 text-gray-500',
            index === currentMonth && 'ring-2 ring-blue-500'
          )}
        >
          {month}
        </div>
      ))}
    </div>
  );
}
```

### Payload CMS Configuration

**Availability Field in Products Collection:**

File: `src/payload/fields/availability.ts`
```typescript
import { Field } from 'payload/types';

export const availabilityField: Field = {
  name: 'availability',
  type: 'group',
  label: 'Seasonal Availability',
  fields: [
    { name: 'january', type: 'checkbox', label: 'January' },
    { name: 'february', type: 'checkbox', label: 'February' },
    { name: 'march', type: 'checkbox', label: 'March' },
    { name: 'april', type: 'checkbox', label: 'April' },
    { name: 'may', type: 'checkbox', label: 'May' },
    { name: 'june', type: 'checkbox', label: 'June' },
    { name: 'july', type: 'checkbox', label: 'July' },
    { name: 'august', type: 'checkbox', label: 'August' },
    { name: 'september', type: 'checkbox', label: 'September' },
    { name: 'october', type: 'checkbox', label: 'October' },
    { name: 'november', type: 'checkbox', label: 'November' },
    { name: 'december', type: 'checkbox', label: 'December' }
  ],
  admin: {
    description: 'Check the months when this product is available'
  }
};
```

### Translation Keys

Add to `messages/en.json`:
```json
{
  "Calendar": {
    "title": "Seasonal Availability Calendar",
    "viewByProduct": "View by Product",
    "viewByMonth": "View by Month",
    "selectMonth": "Select Month",
    "product": "Product",
    "noProducts": "No products available in this month",
    "productsAvailable": "{count} products available",
    "legend": {
      "title": "Legend",
      "available": "Available",
      "notAvailable": "Not Available"
    },
    "months": {
      "january": { "short": "Jan", "full": "January" },
      "february": { "short": "Feb", "full": "February" },
      // ... all 12 months
    }
  }
}
```

### Mobile Responsiveness

**Responsive Table:**
```typescript
// On mobile, convert table to cards
<div className="lg:hidden">
  {products.map((product) => (
    <div key={product.id} className="card">
      <h3>{product.name}</h3>
      <div className="grid grid-cols-4 gap-2">
        {MONTHS.map((month) => (
          <div key={month} className="text-center">
            <p className="text-xs">{t(`months.${month}.short`)}</p>
            <AvailabilityIndicator available={product.availability[month]} />
          </div>
        ))}
      </div>
    </div>
  ))}
</div>

<div className="hidden lg:block">
  {/* Desktop table view */}
</div>
```

### AI Agent Rules for Calendar

1. ✅ **ALWAYS** use boolean fields for each month (not arrays or date ranges)
2. ✅ Availability status is calculated dynamically based on current date
3. ✅ Color coding must match design system exactly (green-500 for available)
4. ✅ Calendar must be fully responsive (table → cards on mobile)
5. ✅ Link from calendar cells to product detail pages
6. ✅ Show current month with visual indicator (ring)
7. ❌ **NEVER** use date pickers - this is month-based availability only
8. ❌ **NEVER** hardcode month names - use translation keys

### Edge Cases

**Scenario: All products out of season**
- Display message: "No products currently available"
- Show next availability date
- Suggest contacting for special orders

**Scenario: Product available year-round**
- All 12 months checked as true
- Display "Available Year-Round" badge

**Scenario: Mobile viewport with 20+ products**
- Implement virtual scrolling or pagination
- Load visible products only

---

## Summary

This architecture document provides a complete blueprint for building the Alsoadaa Export website. Key highlights:

✅ **Starter-based approach** reduces development time by 80%  
✅ **Explicit patterns** prevent AI agent conflicts  
✅ **Multilingual support** with RTL for Arabic markets  
✅ **Seasonal calendar** helps buyers plan procurement  
✅ **Performance-optimized** for <2s load times and Lighthouse >90  
✅ **SEO-ready** with proper meta tags and structured data  

### Next Steps

1. **Clone starter template** and configure database
2. **Install additional dependencies** (i18n, forms, calendar)
3. **Create Payload collections** (Products, Categories, etc.)
4. **Implement core components** following patterns
5. **Add translations** for all 3 languages
6. **Test thoroughly** across browsers and devices
7. **Deploy to Vercel** with proper environment variables

**Estimated Timeline:** 6 weeks for full implementation with 1-2 developers.

---

**Document Version:** 1.0  
**Last Updated:** 2025-10-25  
**Author:** Winston (Architect)  
**Project:** Alsoadaa Export Website

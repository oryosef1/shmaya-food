# Architecture — שמאיה עושה לכם טעים

## System Overview

This is a static single-page website with no backend, no build tools, and no JavaScript frameworks. Everything lives in a single `index.html` file with embedded CSS and JS. The site is designed to be opened directly in a browser or deployed to any static hosting.

## Page Structure (Top to Bottom)

```
┌──────────────────────────────┐
│  Sticky Navigation Bar       │  Fixed at top, links to each section
├──────────────────────────────┤
│  Hero / Header               │  Logo image + business name
├──────────────────────────────┤
│  Tali (Indian Thali)         │  Gallery (5 images) + description + hours
├──────────────────────────────┤
│  Souvlaki                    │  Gallery (5 images) + description + hours
├──────────────────────────────┤
│  Forest Walks                │  Description + hours (no images yet)
├──────────────────────────────┤
│  Company Events              │  Description + hours (no images yet)
├──────────────────────────────┤
│  Hours Summary               │  Table/cards summarizing all activities
├──────────────────────────────┤
│  Contact                     │  Address, Waze link, social media icons
└──────────────────────────────┘
```

## Directory Structure

```
moms-website/
├── index.html              ← Single HTML file (CSS + JS embedded)
├── content.txt             ← Raw text content from business owner
├── PLAN.md                 ← Detailed site plan and specifications
├── CLAUDE.md               ← Development conventions
├── TODO.md                 ← Task tracking
├── ARCHITECTURE.md         ← This file
├── NEXT-SESSION.md         ← Session continuity notes
├── .claude/
│   ├── commands/           ← Session workflow commands
│   └── rules/              ← Path-scoped rules
├── docs/
│   └── decisions/          ← Architecture Decision Records
└── images/
    ├── business/           ← Logo (1 image)
    │   └── logo.jpeg
    ├── tali/               ← Tali gallery (5 images)
    │   └── tali-{1-5}.jpeg
    └── suflaki/            ← Souvlaki gallery (5 images)
        └── suflaki-{1-5}.jpeg
    (No images yet for forest walks or company events)
```

## Key Design Decisions

### Single HTML File
All CSS and JS are embedded in `index.html`. No build step, no bundling. This makes deployment trivial — upload one file + images folder.

### No Frameworks
Vanilla HTML/CSS/JS only. The site is simple enough that frameworks add complexity without benefit. Google Fonts is the only external resource.

### RTL Layout
The entire site uses `dir="rtl"` and `lang="he"`. CSS layout (Grid/Flexbox) respects logical properties where possible.

### Mobile-First
CSS starts with mobile styles and uses `min-width` media queries for larger screens. Target: looks great on phones first, adapts up.

### Image Galleries
Horizontal scrolling galleries using CSS `scroll-snap`. No carousel library — native CSS provides smooth, accessible scrolling. A simple vanilla JS lightbox handles image enlargement.

### External Links
- **Waze:** Deep link to navigate to the business address
- **WhatsApp:** `wa.me` link for direct messaging
- **Instagram/Facebook:** Profile links

## Data Flow

There is no dynamic data. All content is hardcoded in the HTML. The `content.txt` file is a reference document, not read at runtime. Images are loaded via relative `src` paths with `loading="lazy"` for performance.

## Performance Considerations

- `loading="lazy"` on all images below the fold
- No external JS libraries to download
- Single HTTP request for the page (plus images and font)
- Images should be reasonably compressed (JPEG quality ~80%)

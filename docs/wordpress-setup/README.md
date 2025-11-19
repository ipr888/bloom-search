Yes! Just copy and paste this **full replacement** for your README.md file:

```markdown
# BloomSearch - WordPress Setup

## 🚀 Quick Start
- **Site URL**: bloomsearch.sg
- **Admin URL**: bloomsearch.sg/wp-admin  
- **Theme**: Kadence + Custom Child Theme
- **Status**: Development
- **Repo**: `bloomsearch/wordpress-setup`

## 📦 Plugin Stack

### Essential Plugins
| Plugin | Version | Purpose | Config |
|--------|---------|---------|---------|
| Kadence Blocks | 3.5.27 | Page Builder | Default |
| Rank Math SEO | 1.0.258 | SEO Optimization | Job Posting Schema |
| Wordfence Security | 8.1.2 | Security/Firewall | Enabled Firewall |
| WP Mail SMTP | 4.7.0 | Email Delivery | Gmail/SendGrid |
| UpdraftPlus | 1.25.9 | Backups | Google Drive Weekly |
| WP Super Cache | 3.0.3 | Caching | Simple Mode |
| Autoptimize | 3.1.13 | Minification | CSS+JS+HTML |
| Cloudflare | 4.13.0 | CDN/Firewall | Nameserver Setup |

### Optional Plugins
- SuperPWA (When ready for app-like features)

## 🎨 Theme Architecture

### File Structure
```
wordpress/
└── wp-content/themes/kadence-child/
    ├── style.css                 # Theme header
    ├── functions.php            # Main loader
    ├── assets/
    │   ├── css/
    │   │   ├── tokens.css       # Design system variables
    │   │   ├── base.css         # Resets, globals
    │   │   ├── main.css         # Main importer file
    │   │   ├── utilities.css    # Utility classes
    │   │   ├── layout.css       # Grids, spacing, containers
    │   │   ├── components/      # Individual components
    │   │   │   ├── hero.css
    │   │   │   ├── buttons.css
    │   │   │   ├── accordion.css
    │   │   │   └── alert-dialog.css
    │   │   └── page/
    │   │       ├── home.css     # Homepage specific
    │   │       └── land.css     # Landing page specific
    │   ├── js/
    │   │   ├── app.js           # Global JavaScript
    │   │   └── comp/            # Component scripts
    │   └── ref/                 # Figma/TSX reference files
    ├── template-parts/components/  # Component templates
    │   ├── hero.php             # Hero section
    │   ├── accordion.php        # Accordion component
    │   ├── alert-dialog.php     # Alert dialog component
    │   ├── cta.php              # Call-to-action
    │   └── feat.php             # Features grid
    ├── templates/               # Page templates
    │   ├── landing.php          # Landing page template
    │   └── careers.php          # Careers page template
    └── inc/                     # PHP includes
        ├── load.php             # Enqueue CSS/JS
        ├── hook.php             # WordPress hooks
        └── util.php             # Helper functions
```

### Design Tokens (tokens.css)
```css
@custom-variant dark (&:is(.dark *));

:root {
  /* ========================================
     BLOOM SEARCH DESIGN SYSTEM TOKENS
     WordPress-Ready CSS Custom Properties
     ======================================== */
  
  /* Base */
  --font-size: 16px;
  --background: #ffffff;
  --foreground: oklch(0.145 0 0);
  
  /* ========================================
     BRAND COLORS - Bloom Search Identity
     ======================================== */
  --bs-primary-600: #2563eb;
  --bs-primary-700: #1d4ed8;
  --bs-primary-50: #eff6ff;
  
  /* ========================================
     ACCENT COLORS - Secondary Highlights
     ======================================== */
  --bs-accent-500: #06b6d4;
  --bs-accent-50: #ecfeff;
  
  /* ========================================
     NEUTRAL COLORS - Grayscale Palette
     ======================================== */
  --bs-neutral-900: #111827;
  --bs-neutral-600: #4b5563;
  --bs-neutral-300: #d1d5db;
  --bs-neutral-200: #e5e7eb;
  --bs-neutral-50: #f9fafb;
  --bs-white: #ffffff;
  
  /* ========================================
     SEMANTIC COLORS - UI States
     ======================================== */
  --bs-success: #10b981;
  --bs-warning: #f59e0b;
  --bs-error: #ef4444;
  --bs-info: #3b82f6;
  
  /* ========================================
     TYPOGRAPHY - Font Sizes
     ======================================== */
  --bs-text-4xl: 3.5rem;      /* 56px - Hero headlines */
  --bs-text-3xl: 3rem;        /* 48px - Large headings */
  --bs-text-2xl: 2.5rem;      /* 40px - H1 */
  --bs-text-xl: 2rem;         /* 32px - H2 */
  --bs-text-lg: 1.5rem;       /* 24px - H3 */
  --bs-text-base: 1rem;       /* 16px - Body */
  --bs-text-sm: 0.875rem;     /* 14px - Small */
  --bs-text-xs: 0.75rem;      /* 12px - Tiny */
  
  /* ========================================
     TYPOGRAPHY - Font Weights
     ======================================== */
  --bs-font-normal: 400;
  --bs-font-medium: 500;
  --bs-font-semibold: 600;
  --bs-font-bold: 700;
  
  /* ========================================
     TYPOGRAPHY - Line Heights
     ======================================== */
  --bs-leading-tight: 1.25;
  --bs-leading-normal: 1.5;
  --bs-leading-relaxed: 1.75;
  --bs-leading-loose: 2;
  
  /* ========================================
     SPACING - Base Scale (4px increments)
     ======================================== */
  --bs-space-1: 0.25rem;      /* 4px */
  --bs-space-2: 0.5rem;       /* 8px */
  --bs-space-3: 0.75rem;      /* 12px */
  --bs-space-4: 1rem;         /* 16px */
  --bs-space-6: 1.5rem;       /* 24px */
  --bs-space-8: 2rem;         /* 32px */
  --bs-space-12: 3rem;        /* 48px */
  --bs-space-16: 4rem;        /* 64px */
  --bs-space-24: 6rem;        /* 96px */
  
  /* ========================================
     SPACING - Semantic Gaps
     ======================================== */
  --bs-gap-xs: 0.5rem;        /* 8px */
  --bs-gap-sm: 1rem;          /* 16px */
  --bs-gap-md: 1.5rem;        /* 24px */
  --bs-gap-lg: 2rem;          /* 32px */
  --bs-gap-xl: 3rem;          /* 48px */
  
  /* ========================================
     SPACING - Section Layout
     ======================================== */
  --bs-section-py: 4rem;      /* 64px vertical padding */
  --bs-section-px: 1.5rem;    /* 24px horizontal padding */
  --bs-section-gap: 4rem;     /* 64px between sections */
  
  /* ========================================
     CONTAINER WIDTHS
     ======================================== */
  --bs-container-5xl: 64rem;   /* 1024px */
  --bs-container-6xl: 72rem;   /* 1152px */
  --bs-container-7xl: 80rem;   /* 1280px */
  
  /* ========================================
     BORDER RADIUS
     ======================================== */
  --bs-radius-sm: 0.25rem;     /* 4px */
  --bs-radius-base: 0.5rem;    /* 8px */
  --bs-radius-md: 0.625rem;    /* 10px */
  --bs-radius-lg: 0.75rem;     /* 12px */
  --bs-radius-xl: 1rem;        /* 16px */
  --bs-radius-full: 9999px;    /* Circular */
  
  /* ========================================
     SHADOWS
     ======================================== */
  --bs-shadow-sm: 0 1px 2px 0 rgba(0, 0, 0, 0.05);
  --bs-shadow-base: 0 1px 3px 0 rgba(0, 0, 0, 0.1), 0 1px 2px -1px rgba(0, 0, 0, 0.1);
  --bs-shadow-md: 0 4px 6px -1px rgba(0, 0, 0, 0.1), 0 2px 4px -2px rgba(0, 0, 0, 0.1);
  --bs-shadow-lg: 0 10px 15px -3px rgba(0, 0, 0, 0.1), 0 4px 6px -4px rgba(0, 0, 0, 0.1);
  --bs-shadow-xl: 0 20px 25px -5px rgba(0, 0, 0, 0.1), 0 8px 10px -6px rgba(0, 0, 0, 0.1);
  
  /* ========================================
     SHADCN/UI COMPATIBILITY LAYER
     ======================================== */
  --card: #ffffff;
  --card-foreground: oklch(0.145 0 0);
  --popover: oklch(1 0 0);
  --popover-foreground: oklch(0.145 0 0);
  --primary: #030213;
  --primary-foreground: oklch(1 0 0);
  --secondary: oklch(0.95 0.0058 264.53);
  --secondary-foreground: #030213;
  --muted: #ececf0;
  --muted-foreground: #717182;
  --accent: #e9ebef;
  --accent-foreground: #030213;
  --destructive: #d4183d;
  --destructive-foreground: #ffffff;
  --border: rgba(0, 0, 0, 0.1);
  --input: transparent;
  --input-background: #f3f3f5;
  --switch-background: #cbced4;
  --font-weight-medium: 500;
  --font-weight-normal: 400;
  --ring: oklch(0.708 0 0);
  --chart-1: oklch(0.646 0.222 41.116);
  --chart-2: oklch(0.6 0.118 184.704);
  --chart-3: oklch(0.398 0.07 227.392);
  --chart-4: oklch(0.828 0.189 84.429);
  --chart-5: oklch(0.769 0.188 70.08);
  --radius: 0.625rem;
  --sidebar: oklch(0.985 0 0);
  --sidebar-foreground: oklch(0.145 0 0);
  --sidebar-primary: #030213;
  --sidebar-primary-foreground: oklch(0.985 0 0);
  --sidebar-accent: oklch(0.97 0 0);
  --sidebar-accent-foreground: oklch(0.205 0 0);
  --sidebar-border: oklch(0.922 0 0);
  --sidebar-ring: oklch(0.708 0 0);
}

.dark {
  --background: oklch(0.145 0 0);
  --foreground: oklch(0.985 0 0);
  --card: oklch(0.145 0 0);
  --card-foreground: oklch(0.985 0 0);
  --popover: oklch(0.145 0 0);
  --popover-foreground: oklch(0.985 0 0);
  --primary: oklch(0.985 0 0);
  --primary-foreground: oklch(0.205 0 0);
  --secondary: oklch(0.269 0 0);
  --secondary-foreground: oklch(0.985 0 0);
  --muted: oklch(0.269 0 0);
  --muted-foreground: oklch(0.708 0 0);
  --accent: oklch(0.269 0 0);
  --accent-foreground: oklch(0.985 0 0);
  --destructive: oklch(0.396 0.141 25.723);
  --destructive-foreground: oklch(0.637 0.237 25.331);
  --border: oklch(0.269 0 0);
  --input: oklch(0.269 0 0);
  --ring: oklch(0.439 0 0);
  --font-weight-medium: 500;
  --font-weight-normal: 400;
  --chart-1: oklch(0.488 0.243 264.376);
  --chart-2: oklch(0.696 0.17 162.48);
  --chart-3: oklch(0.769 0.188 70.08);
  --chart-4: oklch(0.627 0.265 303.9);
  --chart-5: oklch(0.645 0.246 16.439);
  --sidebar: oklch(0.205 0 0);
  --sidebar-foreground: oklch(0.985 0 0);
  --sidebar-primary: oklch(0.488 0.243 264.376);
  --sidebar-primary-foreground: oklch(0.985 0 0);
  --sidebar-accent: oklch(0.269 0 0);
  --sidebar-accent-foreground: oklch(0.985 0 0);
  --sidebar-border: oklch(0.269 0 0);
  --sidebar-ring: oklch(0.439 0 0);
}

/* ========================================
   RESPONSIVE DESIGN TOKENS
   Desktop adjustments for spacing
   ======================================== */
@media (min-width: 768px) {
  :root {
    --bs-section-py: 6rem;     /* 96px on desktop */
  }
}
```

## 🔧 Development Workflow

### 1. Local Development
```bash
# Clone child theme to local
git clone [repo-url] kadence-child
cd kadence-child

# Development server (if using LocalWP/Laragon)
# Make changes → Test locally → Push to GitHub
```

### 2. TSX to PHP Conversion
- Reference: `assets/ref/[component].tsx`
- Output: `template-parts/components/[component].php`
- Shared styles: `assets/css/components/[component].css`

### 3. Component Usage in Templates
```php
<?php
// In page templates or other PHP files
get_template_part('template-parts/components/hero');
get_template_part('template-parts/components/accordion');
get_template_part('template-parts/components/alert-dialog');
?>
```

### 4. Asset Management
- Enqueue via `inc/load.php`
- Dependencies: tokens → base → utilities → layout → components
- Minification handled by Autoptimize

### 5. Deployment
```bash
# Manual deployment via cPanel File Manager
# Or via WP-CLI if SSH access available
wp theme activate kadence-child
```

## 🌐 External Services

### Cloudflare Setup
- **Status**: Active
- **DNS**: Nameservers pointed to Cloudflare
- **SSL**: Full (strict)
- **Caching**: Browser cache TTL 4 hours

### Email Service
- **Provider**: Gmail/SendGrid (via WP Mail SMTP)
- **Usage**: Forms, notifications, password resets

### Backup Strategy
- **Primary**: UpdraftPlus → Google Drive (weekly)
- **Secondary**: Hosting cPanel backups (daily)
- **Retention**: 4 weeks

## 🎯 React Subdomain Integration

### Future Planning
- **Subdomain**: `app.bloomsearch.sg`
- **Tech Stack**: React, shared design tokens
- **Data Source**: WordPress REST API (if needed)
- **Shared Assets**: `tokens.css`, `ref/` components

### Current Status
- Design tokens defined for cross-platform consistency
- TSX components preserved for future React migration
- CSS architecture supports both platforms

## 🔒 Security Configuration

### Wordfence Settings
- Firewall enabled
- Login attempt limiting
- File change detection
- Real-time traffic monitoring

### Cloudflare Rules
- Bot protection
- DDoS mitigation
- Country blocking (if needed)

## 📝 Maintenance Checklist

### Weekly
- [ ] Verify backups in Google Drive
- [ ] Check Wordfence security alerts
- [ ] Review performance metrics

### Monthly
- [ ] Update plugins/themes
- [ ] Test contact forms
- [ ] Review SEO rankings

### Quarterly
- [ ] Security audit
- [ ] Performance optimization review
- [ ] Backup restoration test

---

## 📞 Contact & Support

- **Developer**: Darren Tay
- **Hosting**: WebHostingWorld
- **Domain**: bloomsearch.sg
- **Last Updated**: 19/11/2025

> **Note**: Keep sensitive data (API keys, passwords) in local environment files only.
```

**Save as:** `bloom-search/docs/wordpress-setup/README.md`

This now accurately reflects your actual file structure with components in `template-parts/components/` and the updated CSS architecture! 🎉

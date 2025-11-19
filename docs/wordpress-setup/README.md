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
    │   │   ├── comp.css         # Components (buttons, cards, forms)
    │   │   ├── layout.css       # Grids, spacing, containers
    │   │   └── page/
    │   │       ├── home.css     # Homepage specific
    │   │       └── land.css     # Landing page specific
    │   ├── js/
    │   │   ├── app.js           # Global JavaScript
    │   │   └── comp/            # Component scripts
    │   └── ref/                 # Figma/TSX reference files
    ├── parts/                   # Template parts
    │   ├── hero.php             # Hero section
    │   ├── feat.php             # Features grid
    │   └── cta.php              # Call-to-action
    ├── tmpl/                    # Page templates
    │   ├── land.php             # Landing page template
    │   └── career.php           # Careers page template
    └── inc/                     # PHP includes
        ├── load.php             # Enqueue CSS/JS
        ├── hook.php             # WordPress hooks
        └── util.php             # Helper functions
```

### Design Tokens (tokens.css)
```css
:root {
  /* Bloom Search Colors */
  --primary: #276BF4;
  --secondary: #30A1A8;
  --bg: #FBFCFD;
  --text: #333333;
  
  /* Spacing */
  --space-sm: 16px;
  --space-md: 24px;
  --space-lg: 32px;
  --space-xl: 48px;
  
  /* Typography */
  --font-main: 'Inter', sans-serif;
  --text-sm: 14px;
  --text-base: 16px;
  --text-lg: 20px;
  --text-xl: 32px;
  --text-2xl: 48px;
  
  /* Borders & Shadows */
  --radius-sm: 4px;
  --radius-md: 8px;
  --radius-lg: 16px;
  --shadow-sm: 0 2px 4px rgba(0,0,0,0.1);
  --shadow-md: 0 4px 8px rgba(0,0,0,0.12);
  --shadow-lg: 0 8px 16px rgba(0,0,0,0.15);
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
- Output: `parts/[component].php`
- Shared styles: `assets/css/comp.css`

### 3. Asset Management
- Enqueue via `inc/load.php`
- Dependencies: tokens → base → comp → layout → page
- Minification handled by Autoptimize

### 4. Deployment
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

- **Developer**: [Your Name]
- **Hosting**: [Hosting Provider]
- **Domain**: bloomsearch.sg
- **Last Updated**: $(date +%Y-%m-%d)

> **Note**: Keep sensitive data (API keys, passwords) in local environment files only.
```

**Save as:** `bloomsearch/docs/wordpress-setup/README.md`

This gives you a complete, professional setup document that's ready for GitHub and can be easily maintained as your project evolves! 🚀

Absolutely! Here's a cleaner hierarchy with better visual organization:

```markdown
# BloomSearch - WordPress Setup

## 🏗️ Architecture Overview
```
BloomSearch Ecosystem
├── 🌐 Main Site (WordPress)
│   ├── 🎨 Kadence Theme + Custom Child
│   ├── 📦 Plugin Stack
│   └── 🎯 Marketing/SEO Content
└── ⚡ App Subdomain (Future React)
    ├── 🔧 Dashboard/Tools
    ├── 📊 Analytics
    └── 🤖 AI Features
```

## 🚀 Quick Start
| Component | Details |
|-----------|---------|
| **Site URL** | bloomsearch.sg |
| **Admin URL** | bloomsearch.sg/wp-admin |
| **Theme** | Kadence + Custom Child Theme |
| **Status** | Development |
| **Repo** | bloomsearch/wordpress-setup |

## 📦 Plugin Stack

### 🔧 Core Functionality
| Plugin | Purpose | Status |
|--------|---------|---------|
| **Kadence Blocks** | Page Builder Features | ✅ Active |
| **Rank Math SEO** | SEO Optimization | ✅ Active |
| **Wordfence Security** | Security & Firewall | ✅ Active |

### 📧 Communication
| Plugin | Purpose | Status |
|--------|---------|---------|
| **WP Mail SMTP** | Email Delivery | ✅ Active |
| **Kadence Forms** | Contact/Application Forms | ✅ Built-in |

### 🛡️ Performance & Security
| Plugin | Purpose | Status |
|--------|---------|---------|
| **WP Super Cache** | Page Caching | ✅ Active |
| **Autoptimize** | CSS/JS Minification | ✅ Active |
| **Cloudflare** | CDN & Security | ✅ Active |

### 💾 Backup & Maintenance
| Plugin | Purpose | Status |
|--------|---------|---------|
| **UpdraftPlus** | Automated Backups | ✅ Active |

### 🔮 Future Enhancements
| Plugin | Purpose | Status |
|--------|---------|---------|
| **SuperPWA** | App-like Features | ⏳ Planned |

## 🎨 Theme Architecture

### 📁 File Structure
```
kadence-child/
├── 🎯 Core Files
│   ├── style.css              # Theme header
│   └── functions.php          # Main loader
│
├── 🎨 Assets
│   ├── css/
│   │   ├── tokens.css         # Design system
│   │   ├── base.css           # Resets & globals
│   │   ├── comp.css           # Components
│   │   ├── layout.css         # Grids & spacing
│   │   └── page/              # Page-specific
│   │       ├── home.css
│   │       └── land.css
│   ├── js/
│   │   ├── app.js             # Global scripts
│   │   └── comp/              # Component scripts
│   └── ref/                   # Reference files
│       ├── hero.tsx
│       ├── features.tsx
│       └── design-tokens.json
│
├── 🧩 Template Parts
│   ├── hero.php               # Hero section
│   ├── feat.php               # Features grid
│   └── cta.php                # Call-to-action
│
├── 📄 Page Templates
│   ├── land.php               # Landing page
│   └── career.php             # Careers page
│
└── ⚙️ Includes
    ├── load.php               # Asset management
    ├── hook.php               # WordPress hooks
    └── util.php               # Helper functions
```

### 🎨 Design System (tokens.css)
```css
/* ===== COLOR SYSTEM ===== */
:root {
  /* Primary Palette */
  --primary: #276BF4;    /* Bloom Blue */
  --secondary: #30A1A8;  /* Growth Teal */
  --bg: #FBFCFD;         /* Cloud White */
  --text: #333333;       /* Dark Text */
  
  /* Semantic Colors */
  --success: #10B981;
  --warning: #F59E0B;
  --error: #EF4444;
}

/* ===== TYPOGRAPHY ===== */
:root {
  --font-main: 'Inter', sans-serif;
  --text-sm: 14px;
  --text-base: 16px;
  --text-lg: 20px;
  --text-xl: 32px;
  --text-2xl: 48px;
}

/* ===== SPACING SYSTEM ===== */
:root {
  --space-sm: 16px;
  --space-md: 24px;
  --space-lg: 32px;
  --space-xl: 48px;
}

/* ===== EFFECTS ===== */
:root {
  --radius-sm: 4px;
  --radius-md: 8px;
  --radius-lg: 16px;
  --shadow-sm: 0 2px 4px rgba(0,0,0,0.1);
  --shadow-md: 0 4px 8px rgba(0,0,0,0.12);
  --shadow-lg: 0 8px 16px rgba(0,0,0,0.15);
}
```

## 🔄 Development Workflow

### 1. 🏗️ Component Development
```
Figma Design → assets/ref/[component].tsx → parts/[component].php
```

### 2. 🎨 Styling Approach
```
Design Tokens → Base Styles → Components → Layouts → Pages
```

### 3. 📦 Asset Pipeline
```php
// inc/load.php - Dependency order
1. tokens.css    # Design system
2. base.css      # Global styles  
3. comp.css      # Components
4. layout.css    # Layouts
5. page/*.css    # Page-specific
```

## 🌐 External Services

### ☁️ Cloudflare Configuration
| Feature | Status | Details |
|---------|---------|---------|
| **DNS** | ✅ Active | Nameservers pointed |
| **SSL** | ✅ Active | Full (strict) |
| **Caching** | ✅ Active | Browser TTL: 4h |
| **Firewall** | ✅ Active | Bot protection |

### 📧 Email Delivery
| Service | Purpose | Status |
|---------|---------|---------|
| **WP Mail SMTP** | Transactional emails | ✅ Active |
| **Gmail/SendGrid** | SMTP provider | 🔄 Configuring |

### 💾 Backup Strategy
| Method | Frequency | Retention | Location |
|---------|-----------|-----------|----------|
| **UpdraftPlus** | Weekly | 4 weeks | Google Drive |
| **Hosting** | Daily | 7 days | cPanel |

## 🛡️ Security & Maintenance

### 🔒 Security Layers
1. **Wordfence** - Firewall & malware scanning
2. **Cloudflare** - DDoS protection & bot mitigation
3. **Regular Updates** - Core, theme, plugin updates

### 📅 Maintenance Schedule
| Frequency | Tasks |
|-----------|-------|
| **Weekly** | Backup verification, security alerts, performance check |
| **Monthly** | Plugin updates, form testing, SEO review |
| **Quarterly** | Security audit, optimization review, restore test |

## 🔮 Future Roadmap

### 🎯 Phase 1: Foundation (Current)
- ✅ WordPress setup
- ✅ Basic plugin stack
- ✅ Design system
- ✅ Security configuration

### 🚀 Phase 2: Enhancement
- 🔄 Advanced forms (job applications)
- 🔄 Performance optimization
- 🔄 Content development

### ⚡ Phase 3: Expansion
- ⏳ React subdomain (app.bloomsearch.sg)
- ⏳ Advanced analytics
- ⏳ AI-powered features

---

## 👥 Team & Support

| Role | Contact | Responsibilities |
|------|---------|------------------|
| **Developer** | Darren Tay | Theme development, plugin config |
| **Hosting** | WebHostingWorld | Server management, backups |
| **Domain** | bloomsearch.sg | DNS, SSL management |

**Last Updated**: 19/11/2025

> 💡 **Note**: Sensitive credentials stored in local environment only.
```

This hierarchy is much more scannable with:
- Clear visual grouping using emojis and tables
- Better categorization of plugins by function
- Structured design system documentation
- Visual workflow diagrams
- Clean status indicators (✅🔄⏳)
- Future roadmap with clear phases

Much easier to navigate and maintain! 🚀

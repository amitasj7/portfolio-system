# Future improvements - 
## sidebar section -
- problem: in profile icon, it's doesn't show my profile image and also in header section - top right corner of screen

## Account section -
- problem: when i update display name then it not update in header and also check for password.
- problem: suppose I don't remember password then what i do

## About Section - 
- done: last updated : add timing also like 23:45:56




# Admin Settings Features

All functionalities available under the Settings section of the Admin Dashboard.

---

## 🌳 Settings Feature Tree

```
Settings
│
├── 1. Account Settings
│   ├── Change Password
│   │   ├── Current password input
│   │   ├── New password input
│   │   ├── Confirm password input
│   │   └── Password strength indicator
│   │
│   ├── Update Email (Optional - Future)
│   │   ├── New email input
│   │   └── Verification flow
│   │
│   └── Update Display Name
│       ├── Name input
│       └── Preview of initials change
│
├── 2. Notification Preferences
│   ├── Email Notifications
│   │   ├── Toggle: New lead received
│   │   ├── Toggle: High-priority (recruiter) lead
│   │   └── Toggle: Weekly summary report
│   │
│   └── Browser Notifications (Future)
│       ├── Toggle: Enable push notifications
│       └── Toggle: Sound on new lead
│
├── 3. Portfolio Display Settings
│   ├── Theme Preferences
│   │   ├── Dark mode (default)
│   │   ├── Light mode
│   │   └── System preference
│   │
│   ├── Public Portfolio Visibility
│   │   ├── Toggle: Portfolio is live/under maintenance
│   │   └── Maintenance message input
│   │
│   └── SEO Settings
│       ├── Meta title
│       ├── Meta description
│       └── Social preview image
│
├── 4. Lead Management Settings
│   ├── Auto-reply Settings
│   │   ├── Toggle: Enable auto-reply
│   │   ├── Auto-reply message template
│   │   └── Delay before sending (instant, 1hr, 24hr)
│   │
│   ├── Lead Classification
│   │   ├── Recruiter domain keywords (google.com, amazon.com, etc.)
│   │   └── Priority keywords (recruiter, hiring, opportunity)
│   │
│   └── Stale Lead Threshold
│       └── Days before marking as stale (default: 3)
│
├── 5. Security Settings
│   ├── Active Sessions
│   │   ├── View current sessions (device, location, time)
│   │   └── Logout all sessions
│   │
│   ├── Two-Factor Authentication (Future)
│   │   ├── Enable/disable 2FA
│   │   └── Recovery codes
│   │
│   └── Login History
│       └── View last 10 login attempts
│
├── 6. Data Management
│   ├── Export Data
│   │   ├── Export all leads (CSV/JSON)
│   │   ├── Export projects (JSON)
│   │   └── Export full portfolio (ZIP)
│   │
│   └── Danger Zone
│       ├── Clear all leads
│       ├── Reset portfolio to defaults
│       └── Delete account (irreversible)
│
└── 7. About / System Info
    ├── App Version
    ├── Last updated
    ├── Backend health status
    └── API response time
│
└── 8. Developer Settings (Advanced)
    ├── API Environment
    │   ├── Toggle: Staging / Production mode
    │   ├── Display current API keys (masked)
    │   └── Warning banner when in staging
    │
    ├── Third-Party Integrations
    │   ├── Stripe API key (masked)
    │   ├── Cloudinary config
    │   ├── SendGrid API key (masked)
    │   └── Test connection buttons
    │
    └── Debug Mode
        ├── Toggle: Enable verbose logging
        └── View recent error logs
```

---

## Priority for V1 Implementation

### ✅ HIGH PRIORITY (Build First)
| Feature | Reason |
|---------|--------|
| Change Password | Security essential |
| Update Display Name | Shows in header |
| Stale Lead Threshold | Affects dashboard alerts |
| Portfolio Visibility Toggle | Control public access |
| API Environment Toggle | Dev vs Production safety |

### ⏳ MEDIUM PRIORITY (Phase 2)
| Feature | Reason |
|---------|--------|
| Email Notification Toggles | Nice to have |
| Export Leads (CSV) | Data portability |
| Theme Preferences | User comfort |
| About / System Info | Debug help |

### 📋 LOW PRIORITY (Future)
| Feature | Reason |
|---------|--------|
| Two-Factor Auth | Advanced security |
| Browser Push Notifications | Requires service worker |
| Auto-reply Settings | Email complexity |
| SEO Settings | For public portfolio |

---

## UI Layout Proposal

```
┌──────────────────────────────────────────────────────────────┐
│  ⚙️ Settings                                                  │
├──────────────────────────────────────────────────────────────┤
│                                                              │
│  ┌─────────────────┐   ┌──────────────────────────────────┐ │
│  │ 📋 SIDEBAR      │   │  CONTENT AREA                    │ │
│  │                 │   │                                  │ │
│  │ • Account       │   │  ┌──────────────────────────┐    │ │
│  │ • Notifications │   │  │ Change Password          │    │ │
│  │ • Display       │   │  │ ────────────────────     │    │ │
│  │ • Leads         │   │  │ Current: ●●●●●●●●        │    │ │
│  │ • Security      │   │  │ New: ●●●●●●●●●●          │    │ │
│  │ • Data          │   │  │ Confirm: ●●●●●●●●●●      │    │ │
│  │ • Developer ⚠️  │   │  │                          │    │ │
│  │ • About         │   │  │ [Update Password]        │    │ │
│  │                 │   │  └──────────────────────────┘    │ │
│  │ ─────────────── │   │                                  │ │
│  │ 👤 USER CARD    │   │                                  │ │
│  │ ┌─────────────┐ │   │                                  │ │
│  │ │ [Photo]     │ │   │                                  │ │
│  │ │ Amit Singh  │ │   │                                  │ │
│  │ │ Super Admin │ │   │                                  │ │
│  │ └─────────────┘ │   │                                  │ │
│  └─────────────────┘   └──────────────────────────────────┘ │
│                                                              │
└──────────────────────────────────────────────────────────────┘
```

> **Note**: Developer section shows ⚠️ warning icon to indicate advanced/dangerous options.

---

## API Endpoints Required

| Endpoint | Method | Purpose |
|----------|--------|---------|
| `/admin/settings` | GET | Get all settings |
| `/admin/settings` | PUT | Update settings |
| `/admin/auth/password` | PUT | Change password |
| `/admin/data/export/leads` | GET | Export leads |
| `/admin/data/export/portfolio` | GET | Export full data |

---

## Database Model (Settings)

```typescript
interface ISettings {
    // Notifications
    emailOnNewLead: boolean;
    emailOnRecruiterLead: boolean;
    emailWeeklySummary: boolean;
    
    // Portfolio
    portfolioTheme: 'dark' | 'light' | 'system';
    portfolioIsLive: boolean;
    maintenanceMessage?: string;
    
    // SEO
    metaTitle?: string;
    metaDescription?: string;
    socialPreviewImage?: string;
    
    // Leads
    recruiterDomains: string[];
    priorityKeywords: string[];
    staleDaysThreshold: number;
    
    // Auto-reply
    autoReplyEnabled: boolean;
    autoReplyMessage?: string;
    autoReplyDelay: 'instant' | '1h' | '24h';
}
```

---

## Next Steps

1. [ ] Review and approve feature list
2. [ ] Build Settings page layout
3. [ ] Implement HIGH PRIORITY features first
4. [ ] Add remaining features in phases

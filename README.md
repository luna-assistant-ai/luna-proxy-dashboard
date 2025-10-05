# AI-Gate Dashboard 🎨

Modern, beautiful dashboard for AI-Gate users to manage their usage, track sessions, and upgrade plans.

## 🌐 Live Dashboards

- **User Dashboard**: https://dashboard.ai-gate.dev/dashboard.html ✨ NEW
- **Pricing Page**: https://dashboard.ai-gate.dev/pricing.html ✨ NEW
- **Monitoring**: https://dashboard.ai-gate.dev/ (Admin)

---

## 🎯 Pages

### 1. **User Dashboard** (`dashboard.html`) ✨ NEW
Beautiful billing & usage dashboard for end users

**Features:**
- ✅ Session quota display with animated progress bars
- ✅ Real-time usage tracking
- ✅ Plan features overview
- ✅ Smart upgrade alerts (80%, 100% quota)
- ✅ Responsive design with glassmorphism effects
- ✅ Auto-refresh every 30s

**API:** `GET /billing/usage?user_id=xxx`

### 2. **Pricing Page** (`pricing.html`) ✨ NEW
Stunning pricing page with session-based plans

**Features:**
- ✅ 3 tiers: FREE ($0), STARTER ($29), GROWTH ($99)
- ✅ Transparent session-based pricing
- ✅ Feature comparison table
- ✅ Comprehensive FAQ section
- ✅ One-click Stripe checkout integration
- ✅ Mobile-optimized

**API:** `POST /billing/checkout`

### 3. **Monitoring Dashboard** (`index.html`)
Real-time technical monitoring for administrators

**Features:**
- ✅ Live metrics tracking
- ✅ Session success rates
- ✅ Performance charts
- ✅ Health status indicators
- ✅ Recent sessions history

**API:** `GET /metrics`

---

## 🎨 Design Highlights

### Color Palette
```css
--primary: #6366f1      /* Indigo */
--success: #10b981      /* Green */
--warning: #f59e0b      /* Amber */
--danger: #ef4444       /* Red */
```

### UI Features
- **Glassmorphism cards** with subtle shadows
- **Gradient backgrounds** (purple to violet)
- **Animated progress bars** with shimmer effect
- **Smooth transitions** on all interactions
- **Responsive grid layouts** for all screen sizes

---

## 📊 User Dashboard Data

### API Response (`/billing/usage`)
```json
{
  "plan": "free",
  "sessionsIncluded": 100,
  "sessionsUsed": 45,
  "sessionsRemaining": 55,
  "estimatedMinutes": 200,
  "minutesUsed": 90,
  "percentUsed": 45,
  "rateLimit": {
    "requestsPerMinute": 100,
    "concurrent": 1
  }
}
```

### Displayed Metrics
1. **Quota Display** - Big, bold session count
2. **Progress Bar** - Visual usage percentage
3. **Stats Grid** - Rate limits, concurrent sessions, projects
4. **Plan Features** - Dynamic list based on plan
5. **Alerts** - Warning at 80%, danger at 100%

---

## 💳 Pricing Page Integration

### Checkout Flow
```javascript
// User clicks "Start Free Trial"
POST /billing/checkout
{
  "plan": "starter",
  "user_id": "user_123",
  "email": "user@example.com"
}

// Returns Stripe Checkout URL
{
  "url": "https://checkout.stripe.com/..."
}

// Redirect to Stripe
window.location.href = data.url;
```

### Plans
| Plan | Price | Sessions | Minutes Est | Features |
|------|-------|----------|-------------|----------|
| FREE | $0 | 100 | ~200 | 1 project, community support |
| STARTER | $29 | 5,000 | ~10,000 | 3 projects, email support |
| GROWTH | $99 | 20,000 | ~40,000 | 10 projects, priority support, SLA 99.9% |

---

## 🚀 Deployment

### Cloudflare Pages
```bash
cd luna-proxy-dashboard
wrangler pages deploy . --project-name=luna-proxy-dashboard
```

**Live URLs:**
- Production: https://dashboard.ai-gate.dev
- Preview: Auto-generated per commit

### Auto-Deploy
Connected to GitHub repository. Automatic deployment on every push to `main`.

---

## 🛠️ Local Development

1. **Open in browser**
   ```bash
   open dashboard.html
   # or
   open pricing.html
   ```

2. **Test with production API**
   - Connects to `https://api.ai-gate.dev`
   - Real-time data updates every 30s

3. **Customize**
   - Edit `TEST_USER_ID` in scripts for testing
   - Adjust CSS variables for colors
   - Modify `PLAN_FEATURES` object for features

---

## 📁 File Structure

```
luna-proxy-dashboard/
├── index.html         # Admin monitoring dashboard
├── dashboard.html     # User billing dashboard ✨
├── pricing.html       # Pricing page ✨
└── README.md          # This file
```

---

## 💡 Innovation Points

✨ **Session-based pricing** (not minutes like competitors)
✨ **Real-time quota visualization** with animations
✨ **Smart alerts** at usage milestones (80%, 100%)
✨ **One-click upgrade** via Stripe Checkout
✨ **Transparent pricing** with no hidden fees
✨ **Beautiful UI** that builds trust
✨ **Mobile-first responsive design**

---

## 🎯 User Journey

1. **Visit Dashboard** → See quota usage
2. **Hit 80% quota** → Warning alert + "Upgrade" CTA
3. **Click "View Plans"** → Pricing page
4. **Select Plan** → Stripe Checkout
5. **Complete Payment** → Webhook updates plan in DB
6. **Return to Dashboard** → New quota reflected instantly

---

## 📊 Monitoring Dashboard

### Métriques Affichées
1. **Status** - Health check + uptime
2. **Total Sessions** - Cumulative counter
3. **Success Rate** - Percentage with color coding
4. **Active Sessions** - Currently processing

### Graphique (Chart.js)
- Sessions success (green line)
- Sessions errors (red line)
- Last 20 data points
- Auto-updates every 30s

---

## 🔧 Configuration

### API Endpoints
```javascript
const API_URL = 'https://api.ai-gate.dev';

// Dashboard
GET /billing/usage?user_id=xxx

// Pricing
POST /billing/checkout
{
  "plan": "starter",
  "user_id": "user_123",
  "email": "user@example.com"
}

// Monitoring
GET /metrics
```

### Refresh Intervals
```javascript
// Dashboard: Every 30 seconds
setInterval(loadUsage, 30000);

// Monitoring: Every 30 seconds
setInterval(fetchMetrics, 30000);
```

---

## 🔐 TODO: Authentication

Currently uses hardcoded `TEST_USER_ID`. Next steps:

- [ ] Add OAuth (Google/GitHub) via NextAuth
- [ ] JWT-based sessions with secure cookies
- [ ] User profile page with settings
- [ ] Multi-project management UI
- [ ] API key management
- [ ] Team collaboration features

---

## 🎨 Technologies

- **Pure HTML/CSS/JavaScript** (no build step!)
- **Chart.js 4.4.0** for data visualization
- **Stripe Checkout** for payments
- **Cloudflare Pages** for hosting
- **Inter font** from Google Fonts
- **Modern CSS** (Grid, Flexbox, CSS Variables, Animations)

---

## 💰 Coût

**Cloudflare Pages Free Tier:**
- 500 builds/month
- Unlimited requests
- Unlimited bandwidth
- **Coût: $0**

---

## 🔗 Links

- **User Dashboard:** https://dashboard.ai-gate.dev/dashboard.html
- **Pricing:** https://dashboard.ai-gate.dev/pricing.html
- **Monitoring:** https://dashboard.ai-gate.dev/
- **API:** https://api.ai-gate.dev/
- **GitHub:** https://github.com/CosteGieF/luna-proxy-dashboard
- **Docs:** https://docs.ai-gate.dev

---

**Built with ❤️ for AI developers who value transparency**

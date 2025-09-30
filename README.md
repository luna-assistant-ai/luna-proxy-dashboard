# 📊 Luna Proxy API - Monitoring Dashboard

Dashboard de monitoring en temps réel pour l'API Luna Proxy.

## 🌐 Live Dashboard

**URL:** https://luna-proxy-dashboard.pages.dev/

## ✨ Features

- ✅ Status API en temps réel
- ✅ Métriques totales (sessions, success rate, uptime)
- ✅ Graphique temps réel (success vs errors)
- ✅ Historique des sessions récentes
- ✅ Auto-refresh toutes les 30 secondes
- ✅ Design responsive et moderne
- ✅ Gratuit (Cloudflare Pages)

## 📈 Métriques Affichées

### Cards Principales
1. **Status** - Health check + uptime
2. **Total Sessions** - Compteur total + type de storage
3. **Success Rate** - Pourcentage avec code couleur
4. **Active Sessions** - Sessions en cours

### Graphique
- Sessions success (vert)
- Sessions error (rouge)
- Historique des 20 derniers points

### Liste Sessions
- 10 dernières sessions
- Model + voice utilisés
- Timestamp
- Status (success/error)

## 🎨 Design

- Gradient violet moderne
- Cards avec shadow et hover effect
- Graphique Chart.js interactif
- Status indicator animé (pulse)
- Responsive mobile-friendly

## 🚀 Déploiement

### Cloudflare Pages
```bash
wrangler pages deploy . --project-name=luna-proxy-dashboard
```

### GitHub Repository
https://github.com/CosteGieF/luna-proxy-dashboard

### Auto-Deploy
Le dashboard se redéploie automatiquement à chaque push sur `main`.

## 🔧 Configuration

### API Endpoint
```javascript
const API_URL = 'https://api.ai-gate.dev';
```

### Refresh Interval
```javascript
setInterval(fetchMetrics, 30000); // 30 seconds
```

## 📊 Queries API

Le dashboard consomme l'endpoint:
```bash
GET https://api.ai-gate.dev/metrics
```

**Response:**
```json
{
  "uptime_seconds": 123456,
  "storage": "persistent_kv",
  "sessions_total": 100,
  "sessions_success": 95,
  "sessions_error": 5,
  "success_rate": 95.0,
  "active_sessions": 2,
  "recent_sessions": [
    {
      "sessionId": "xxx",
      "startTime": 1234567890,
      "model": "gpt-4o-realtime-preview",
      "voice": "echo",
      "status": "success"
    }
  ]
}
```

## 🎯 Future Enhancements

### Priorité 1
- [ ] Ajouter Analytics Engine queries
- [ ] Graphique latence moyenne
- [ ] Alertes visuelles (error rate > 10%)

### Priorité 2
- [ ] Export métriques CSV
- [ ] Filtres par date/model/voice
- [ ] Dark mode toggle

### Priorité 3
- [ ] Intégration D1 audit logs
- [ ] Rate limiting metrics
- [ ] Geographic distribution (Cloudflare Analytics)

## 💰 Coût

**Cloudflare Pages Free Tier:**
- 500 builds/month
- Unlimited requests
- Unlimited bandwidth
- **Coût: $0**

## 📝 Technologies

- HTML5
- CSS3 (Gradient, Flexbox, Grid)
- JavaScript (ES6+, Fetch API)
- Chart.js 4.4.0
- Cloudflare Pages

## 🔗 Links

- **Dashboard:** https://luna-proxy-dashboard.pages.dev/
- **API:** https://api.ai-gate.dev/
- **GitHub:** https://github.com/CosteGieF/luna-proxy-dashboard
- **Cloudflare:** https://dash.cloudflare.com/602a3ee367f65632af4cab4ca55b46e7/pages/view/luna-proxy-dashboard
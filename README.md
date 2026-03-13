# InfraCraft -- ParkHub Demos

Live interactive demos of [ParkHub](https://github.com/nash87/parkhub-rust) -- a self-hosted parking management system available in two editions.

**Demo site:** [nash87.github.io/infracraft-demos](https://nash87.github.io/infracraft-demos)
**Portfolio:** [infracraft.duckdns.org](https://infracraft.duckdns.org)

---

## Demos

| Edition | Backend | Frontend | Source |
|---------|---------|----------|--------|
| **Rust** | Rust + Axum, embedded redb database | Astro 6 + React 19 + Tailwind CSS 4 | [nash87/parkhub-rust](https://github.com/nash87/parkhub-rust) |
| **PHP** | Laravel 12 + MySQL/SQLite | Astro 6 + React 19 + Tailwind CSS 4 | [nash87/parkhub-php](https://github.com/nash87/parkhub-php) |

Both editions share the same Astro 6 + React 19 + Tailwind CSS 4 frontend and run at **v1.2.1** with production-level security hardening.

### Live Demos

- **PHP Edition:** [parkhub-php-demo.onrender.com](https://parkhub-php-demo.onrender.com)
- **Rust Edition:** [parkhub-rust-demo.onrender.com](https://parkhub-rust-demo.onrender.com)

### Demo Credentials

```
Email:    admin@parkhub.test
Password: ParkHub2026!
```

Demo data is pre-seeded with 10 parking lots, 200 users, and ~3,500 bookings.
Data resets every 30 minutes automatically -- or use the "Reset Demo Now" button.

---

## Features (v1.2.1)

- Parking lot management (lots, floors, slots)
- Credits system for booking and resource allocation
- Booking system with conflict detection
- Internationalization (i18n) -- 10 languages supported
- Dark mode with multiple color themes
- User management + role-based access control
- Admin dashboard with analytics
- Vehicle management
- Security: HSTS, CSP, rate limiting, JWT, GDPR Art.17 erasure

---

## Architecture

### Demo Hosting
- **Landing page**: GitHub Pages (this repo, static HTML -- zero build step)
- **Demo instances**: [Render.com](https://render.com) free-tier Docker containers

### Reset Mechanism
Clicking "Reset Demo Now" calls a [Render Deploy Hook](https://render.com/docs/deploy-hooks), which redeploys the container. Since Render free-tier has no persistent volumes, the database resets to a clean seeded state on every deploy.

Client-side 5-minute cooldown prevents abuse (stored in `localStorage`).

### PHP Demo Seeding
The PHP container runs `ProductionSimulationSeeder` on startup when `DEMO_MODE=true`:
```bash
php artisan db:seed --class=ProductionSimulationSeeder --force
```

---

## Repo Structure

```
infracraft-demos/
├── index.html              # Single-file landing page (vanilla HTML/CSS/JS)
└── .github/
    └── workflows/
        └── pages.yml       # GitHub Actions -- auto-deploy to Pages on push
```

---

## Deploying Your Own

### PHP Edition (Render.com)
1. Fork [nash87/parkhub-php](https://github.com/nash87/parkhub-php)
2. Create a new Web Service on Render -> connect your fork
3. Render detects `render.yaml` automatically
4. Set `DEMO_MODE=true` to enable auto-seeding

### Rust Edition (Render.com)
1. Fork [nash87/parkhub-rust](https://github.com/nash87/parkhub-rust)
2. Create a new Web Service on Render -> connect your fork
3. Render detects `render.yaml` automatically

### Self-hosted (Kubernetes)
Both editions ship with full Kubernetes manifests and Flux GitOps integration.
See the respective repos for deployment details.

---

## License

MIT -- see [LICENSE](https://github.com/nash87/parkhub-rust/blob/main/LICENSE) in the source repos.

Built by [Florian](https://infracraft.duckdns.org) -- Part of the InfraCraft homelab stack.

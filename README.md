# ParkHub — Live Demos

Live interactive demos of [ParkHub](https://github.com/nash87/parkhub-rust) — a self-hosted parking management system available in two editions.

**Demo site:** [nash87.github.io/infracraft-demos](https://nash87.github.io/infracraft-demos)

---

## Demos

| Edition | Backend | Frontend | Source |
|---------|---------|----------|--------|
| **Rust** | Rust + Axum, embedded redb database | Astro 6 + React 19 + Tailwind CSS 4 | [nash87/parkhub-rust](https://github.com/nash87/parkhub-rust) |
| **PHP** | Laravel 12 + MySQL/SQLite | Astro 6 + React 19 + Tailwind CSS 4 | [nash87/parkhub-php](https://github.com/nash87/parkhub-php) |

Both editions share the same frontend and feature set.

### Live Demos

- **Rust Edition:** [parkhub-rust-demo.onrender.com](https://parkhub-rust-demo.onrender.com)
- **PHP Edition:** [parkhub-php-demo.onrender.com](https://parkhub-php-demo.onrender.com)

### Demo Credentials

```
Email:    admin@parkhub.test
Password: ParkHub2026!
```

Demo data is pre-seeded. Data resets via in-app overlay — vote with other visitors or reset when you're the only one online.

---

## Features

- Parking lot management (lots, floors, slots)
- Credits system for booking and resource allocation
- Booking system with conflict detection and auto-assignment
- Recurring and guest bookings
- QR code check-in
- Absence tracking (homeoffice, vacation, sick)
- iCal import and export
- Team overview and today status
- Waitlist system and booking swaps
- Vehicle management with photo upload
- Push notifications and webhooks
- Admin dashboard with reports and CSV export
- Internationalization (i18n) — 10 languages
- Dark mode with 10 color themes
- Branding customization (logo, colors, company name)
- Security: HSTS, CSP, Argon2id, rate limiting, JWT
- GDPR: data export and erasure (Art. 15/17)

---

## Architecture

- **Landing page**: [GitHub Pages](https://nash87.github.io/infracraft-demos) (static HTML)
- **Demo instances**: [Render.com](https://render.com) Docker containers

### Reset Mechanism

The in-app overlay lets visitors vote on resetting demo data. If you're the only visitor online, you can reset immediately.

---

## Repo Structure

```
infracraft-demos/
├── index.html              # Single-file landing page (vanilla HTML/CSS/JS)
├── .github/
│   └── workflows/
│       └── pages.yml       # GitHub Actions — auto-deploy to Pages on push
└── README.md
```

---

## License

MIT — see [LICENSE](https://github.com/nash87/parkhub-rust/blob/main/LICENSE) in the source repos.

Built by [Florian](https://github.com/nash87).

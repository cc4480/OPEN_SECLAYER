# Seclayer

Pay-per-scan black-box penetration testing SaaS with an MCP scan endpoint.

## Stack

- **Frontend:** React 19 + Vite 6 + Tailwind 4
- **Backend:** Express 4 (TypeScript via `tsx`), better-sqlite3
- **Auth:** Passwordless magic-link sign-in; dev mode auto-authenticates as `dev@localhost`
- **AI:** DeepSeek (OpenAI-compatible); falls back to local summaries if key not set
- **Email:** Resend for magic links; prints to console in dev if key not set
- **Payments:** Stripe Checkout + signed webhooks; FREE_MODE on when Stripe not configured

## How to run

```bash
npm run dev   # starts server + Vite dev middleware on port 5000
```

The `Start application` workflow runs `npm run dev` automatically.

## Environment variables

| Variable | Purpose | Required |
|----------|---------|----------|
| `SESSION_SECRET` | Signs session cookies | ✅ Already set |
| `PORT` | Listen port | Set to `5000` for Replit |
| `DEEPSEEK_API_KEY` | AI-generated reports | Optional |
| `RESEND_API_KEY` | Magic-link emails | Optional |
| `EMAIL_FROM` | Sender address for emails | Optional |
| `STRIPE_SECRET_KEY` | Enables credit purchases | Optional |
| `STRIPE_WEBHOOK_SECRET` | Verifies Stripe webhooks | Optional |
| `APP_URL` | Public base URL (magic-link URLs) | Required in production |

## Other scripts

```bash
npm run lint    # TypeScript typecheck
npm test        # unit tests (Node test runner)
npm run build   # build client + bundle server to dist/
npm start       # run the production build
```

## User preferences

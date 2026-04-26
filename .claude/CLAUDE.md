# Claude Code conventions for sixpass.app

## Repo role

sixpass.app is a public Cloudflare-only platform under HTU. It is governed
by the htu-governance onboarding procedure
([SPEC #3](https://github.com/zi007lin/htu-governance/issues/3)).

## Hard rules

- Never write secrets, API keys, or credentials to any file in this repo.
- Never modify `wrangler.*.toml` / `wrangler.jsonc` directly. Wrangler
  configs are governed by the deployment procedure (forthcoming SPEC).
- Never run `wrangler deploy` or `npm run deploy:*` directly. Deployment
  is operator-driven per the htu-governance procedure.
- Issue specs follow `issues/YYYY-MM-DD__type__short-title.md`.
- PRs authored by `zi007lin`, approved by `daniel-silvers`. Dual control.

## Implementation conventions

- TypeScript on Cloudflare Workers + Hono.
- React 18 + Vite + Tailwind v4 for frontend (when it lands).
- Single-package layout (NOT monorepo).
- i18n strings written out completely inline in specs — never generated
  by Claude Code at impl time.

## Out of scope for Claude Code

- Email send (Brevo/Resend) — code paths only, no actual sends from
  development.
- Stripe API calls in test mode are acceptable; live mode never.
- GitHub repo settings (collaborators, branch protection, hooks) — these
  are operator actions per the onboarding procedure.

## When in doubt

Halt and ask. Do not improvise. The htu-governance ONBOARDING.md is the
source of truth.

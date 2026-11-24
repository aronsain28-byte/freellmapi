# Napkin Runbook

## Curation Rules
- Re-prioritize on every read.
- Keep recurring, high-value notes only.
- Max 10 items per category.
- Each item includes date + "Do instead".

## Execution & Validation (Highest Priority)
1. **[2026-11-24] Every change needs a test and a green suite**
   Do instead: add a test with the change and run `npm test` from the root before committing.
2. **[2026-11-24] `npm test` runs much more than server tests**
   Do instead: for a quick loop run `npm run test -w server` (or `-w cli` / `-w client`); run the full `npm test` before committing.
3. **[2026-11-24] Lint and build only cover some workspaces**
   Do instead: run `npm run lint` (server + cli) and `npm run build` (server, cli, client) after TypeScript changes.

## Domain Behavior Guardrails
1. **[2026-11-24] Never edit migrations that were already applied**
   Do instead: create a new one with `npm run db:migration:create --name=<name>` under `server/src/db/migrations/`.
2. **[2026-11-24] Only list genuinely free providers**
   Do instead: reject any paid or credit-card-gated tier when adding a provider.
3. **[2026-11-24] `en.json` is the source of truth for the 60 locales**
   Do instead: add keys to `client/.../en.json` and mirror them, then run `npm run check:i18n` from `client/`.
4. **[2026-11-24] One change per PR**
   Do instead: split unrelated fixes into separate branches/PRs.

## Shell & Command Reliability
1. **[2026-11-24] Supported Node is >=20.18 <25**
   Do instead: check `node -v` first if installs or native modules (better-sqlite3) fail.

## User Directives
1. **[2026-11-24] Clear, direct answers in Spanish**
   Do instead: get to the point without rambling, but don't reduce it to a bare summary.

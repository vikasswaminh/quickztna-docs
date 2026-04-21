# quickztna-docs

Documentation site for **QuickZTNA** — Stripe-style 3-column API reference + user guide + CLI reference.

**Live at:** [docs.quickztna.com](https://docs.quickztna.com) (Cloudflare Pages, project `docs-quickztna`)

## Stack

- Astro 5 (static output)
- Vanilla CSS with OKLCH token system (no Tailwind — design tokens carried verbatim from the Stripe-inspired bundle)
- Geist Sans + Geist Mono (Google Fonts)
- No client-side React — SSR to HTML, ship minimal JS for copy buttons + language tabs + search modal

## Develop

```bash
npm install
npm run dev           # http://localhost:4321
npm run build         # static output to dist/
```

## Deploy

```bash
npm run build
npx wrangler@latest pages deploy dist --project-name=docs-quickztna --branch=main --commit-dirty=true
```

Requires `CLOUDFLARE_API_TOKEN` + `CLOUDFLARE_ACCOUNT_ID` env vars.

## Pages (16 total)

### Entry
- `/` — introduction + card grid
- `/quickstart` — 2-minute onboarding

### User guide (dedicated workflow pages)
- `/guide/auth-keys` — Issue + rotate + revoke auth keys
- `/guide/install` — Installer deep-dive (MDM/Ansible/cloud-init/Docker)
- `/guide/approve-devices` — Approve, quarantine, wipe, delete
- `/guide/acl-policies` — Writing + testing ACLs
- `/guide/posture` — Device posture + remediation
- `/guide/sso` — Okta, Azure AD, Google, SCIM

### Reference
- `/api` — REST API reference (17 endpoint headings, 3-column Stripe layout)
- `/cli` — ztna CLI reference (41 command headings, 14 categories)

### Platform
- `/concepts` — ZTNA / ABAC / PQC / DERP / tailnet / MagicDNS
- `/architecture` — control plane + data plane + HA
- `/security` — crypto commitments + threat model
- `/features` — feature matrix by plan
- `/pricing` — pricing + FAQ
- `/glossary` — 46 alphabetical terms

## Layout variants

- **Default (2-col):** sidebar + content. Used by `/`, guides, platform pages, CLI.
- **3-col API style:** sidebar + content + sticky right rail with request/response code samples. Used by `/api`.

## Related

- **Dashboard:** [login.quickztna.com](https://login.quickztna.com) — source in [`quickztna`](https://github.com/vikasswaminh/quickztna)
- **Marketing:** [quickztna.com](https://quickztna.com) — source in [`quickztna-marketing`](https://github.com/vikasswaminh/quickztna-marketing)

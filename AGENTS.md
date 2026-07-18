# Maple Docs

Public product documentation for Maple Finance (lender/borrower/token-holder guides, technical resources, legal), published via GitBook at [docs.maple.finance](https://docs.maple.finance). Content is Markdown with GitBook extensions — there is no local build, test, or lint step.

## GitBook Git Sync

This repo is bidirectionally synced with GitBook. Edits made in the GitBook web editor arrive here as commits by `gitbook-bot` (subject `GITBOOK-<n>: No subject`); commits pushed here sync back to the live site. Consequences an agent must respect:

- The repo is **not** the sole source of truth — a page may be edited in GitBook at the same time. Pull before editing and keep changes small to avoid sync conflicts.
- A page's published URL derives from its file path and `SUMMARY.md` position. Renaming or moving a `.md` file changes that URL and breaks inbound links. There is no `.gitbook.yaml`, so no redirects are configured — avoid moves unless a redirect is arranged first.

## Layout

- `SUMMARY.md` — GitBook navigation / table of contents. A page must be listed here to publish (e.g. `maple-for-lenders/accessing-permissioned-pools.md` exists but is unregistered, so it does not appear on the site). Register every new page here.
- `README.md` — site landing page (root of the nav).
- `.gitbook/assets/` — all images and files; reference with a relative path (`../.gitbook/assets/name.png`).
- `technical-resources/` — protocol and smart-contract reference: protocol overview, security, loans, pools, strategies, interfaces, singletons, SDK.
- `integrate/` — Syrup asset / frontend / smart-contract integration guides.
- `syrupusdc-usdt-for-lenders/`, `maple-institutional-for-lenders/`, `cash-management-pool/` — lender guides per product.
- `maple-for-borrowers/`, `maple-for-token-holders/` — borrower and SYRUP token-holder guides.
- `legal/` — terms, privacy, risk disclosures. `maple-1.0/` — deprecated Maple 1.0.

## Conventions

- **GitBook Markdown extensions** — hint callouts (`{% hint style="info" %} … {% endhint %}`), tabs (`{% tabs %}`), card grids (`<table data-view="cards">`), and cross-page refs (`{% content-ref %}`). These render only through GitBook; match the surrounding page.
- **Domain terms are canonical** — Pool, Pool Delegate, Lender/LP (never "vault", "manager", "depositor"). The headline metric is **AUM**, not TVL. Existing pages are the reference for tone toward a lay audience.

## Constraints

- Don't rename or move published `.md` files without accounting for the URL change (see GitBook Git Sync).
- Don't add build tooling, CI, or config files expecting them to run — GitBook owns publishing.

# Development

Use Node.js 22.22.2 or later. Run `npm ci`, `npm run build`, `npm run lint` and `npm run bundle`. Build writes to `dist`; bundle writes to `releases`. `npm run dev` imports the extension into Raycast for local development. Use this repository’s source for review and submission. Do not publish private evidence, local installation notes or personal configuration; these are excluded by the project’s Git ignore rules.

`src/core-api.d.ts` is an exact distribution snapshot of the ME-owned protocol, with provenance and hash in `docs/protocol-source.json`. It is not a separate protocol implementation. Refresh it from ME's authoritative `docs/api-v1.d.ts` and update that hash together; do not hand-edit the contract. A clean extension build needs no checkout of ME.

Tests that execute ME require either `ME_INSTALLED_DISCOVERY` pointing to an installed helper record or `ME_CORE_HOST` pointing to ME's source `helper/host.py`. For source tests, `ME_TEST_PYTHON` optionally selects the Python environment. `npm test` uses fresh temporary configs and libraries and removes them afterwards; it does not rebind the daily library. `scripts/duplicate-check.ts` and `scripts/installed-check.ts` use the same isolation fixture.

The reused Raycast/Raindrop UI and its pinned source are documented in [THIRD-PARTY-NOTICES.md](THIRD-PARTY-NOTICES.md). The full MIT notice is included in the runtime assets.

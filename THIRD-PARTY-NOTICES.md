# Third-party notices

## raindrop-io Raycast extension

Parts of this extension are derived from the Raindrop.io Raycast extension
published in the official Raycast extensions repository:

- Source at the adopted revision: https://github.com/raycast/extensions/tree/4cd99da7dfe0dbe794f371f7ec59550d52558c2b/extensions/raindrop-io
- License at that revision: https://github.com/raycast/extensions/blob/4cd99da7dfe0dbe794f371f7ec59550d52558c2b/LICENSE
- Pinned commit: `4cd99da7dfe0dbe794f371f7ec59550d52558c2b`
- Retrieved: 2026-11-05

Adopted files and their local counterparts:

| Upstream | Local | Changes |
| --- | --- | --- |
| `src/search.tsx` | `src/search.tsx` | data hooks read ME; server-side search disables local filtering |
| `src/save_browser_tab.tsx` | `src/save.tsx` | uses the existing Chrome/Edge/Arc page capture |
| `src/components/BookmarkItem.tsx` | `src/components/BookmarkItem.tsx` | ME fields; inline edit and live detail refresh; conflict opens the ME manager; Move to Trash uses one shared list/detail/editor action; restore stays in ME |
| `src/components/BookmarkForm.tsx` | `src/components/BookmarkForm.tsx`, `src/components/BookmarkFields.tsx` | native fields extracted for create/edit; create container uses ME duplicate guard and durable submission; no collection creation |
| `src/components/CollectionsDropdown.tsx` | `src/components/CollectionsDropdown.tsx` | stable list key; native labels/icons and nonrepeated collection paths |
| `src/helpers/collections.ts` | `src/helpers/collections.ts` | Raindrop user-group ordering removed |
| `src/hooks/useRequest.ts` | `src/hooks/useRequest.ts` | originally adapted; current orchestration uses ME hooks, per-library selection and local request lifecycle, with no Raindrop user lookup |
| `src/types.ts` | `src/types.ts` | subset used by the components; ME entity ids are strings |

## Reuse and distribution boundaries

- The reused source is the **Raycast extension** listed above, not the full Raindrop web application or its backend. The table records the provenance of adapted UI, collection helpers and view types; local behavior has changed as described.
- The Raindrop REST/OAuth/account client, Pro/AI account features, cloud data operations and Raindrop branding assets are not distributed by this extension. Data hooks with similar filenames implement ME queries rather than the upstream REST client.
- Bookmark data is accessed through ME’s installed local stdio helper. Versioned edits, duplicate checks, pending-command handling and ME-specific projections live in this companion’s adapter code; the data core, browser manager, import, synchronization and pinyin indexing remain in the separate ME project.
- `src/core-api.d.ts` is an exact declaration snapshot from ME, documented in [docs/protocol-source.json](docs/protocol-source.json). It is a type contract, not a copy of the data core or sync implementation.
- The light and dark Mark Everything icons were supplied by this project’s maintainer and resized to the required dimensions. They are not Raindrop icons. Project names identify provenance only; no affiliation, sponsorship or endorsement by Raindrop is claimed.

## License preservation

The complete upstream MIT license, including **Copyright (c) 2021 Raycast**, is preserved verbatim in [assets/THIRD-PARTY-NOTICES.txt](assets/THIRD-PARTY-NOTICES.txt). This file is included both in the public source and in the bundled extension. The project’s [MIT license](LICENSE) does not replace or remove the upstream notice.

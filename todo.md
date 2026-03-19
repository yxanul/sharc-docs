# Docs Audit: sharc-docs vs D:\SHARC (actual codebase)

Audit date: 2026-03-19

---

## Legend

- [x] = Fixed
- [~] = Won't fix (by design / decision)
- [ ] = Open

---

## 1. docs.json — Starter kit leftovers

- [x] Global anchors pointed to mintlify.com — replaced with GitHub link to SHARC repo
- [x] Navbar support link went to `hi@mintlify.com` — changed to `contact@sharc.sh`
- [x] Navbar dashboard button went to `dashboard.mintlify.com` — changed to `sharc.sh/dashboard`
- [x] Footer socials pointed to Mintlify accounts — changed to SHARC GitHub

---

## 2. Package versions

- [x] `@sharc-code/mcp` updated from `0.2.1` → `0.2.11` in `packages/index.mdx`
- [x] `@sharc-code/splitter` updated from `0.2.0` → `0.2.4` in `packages/index.mdx`

---

## 3. Provider routing / performance tiers

- [x] Removed Standard/Performance tier table from `architecture/index.mdx`
- [x] Removed Standard/Performance tier table from `getting-started/index.mdx`

---

## 4. Model branding

- [~] Keep "Sharc-Embed" / "Sharc-Rerank" branding. Never mention underlying models. (Decision by David)
- [x] Verified: no Qwen/DeepInfra/Fireworks references in any .mdx file

---

## 5. Plan limits

- [~] Docs do not currently have a plans/pricing page. Single aggregate token bucket (1:1 embed + rerank) is the actual model. Consider adding a pricing page later.
- [ ] SHARC main repo README.md still has stale separate embed/rerank columns — update separately in that repo.

---

## 6. API endpoint paths

- [x] `files.mdx`: Fixed `POST /v1/files` → `DELETE /v1/files`
- [x] `sync-save.mdx`: Fixed `POST /v1/sync/save` → `PUT /v1/sync/snapshot`
- [x] `sync-load.mdx`: Fixed `POST /v1/sync/load` → `GET /v1/sync/snapshot`

---

## 7. MCP tools — new parameters

- [x] Added `searchMode` parameter to `search_code` in `mcp/tools.mdx` with full mode table
- [x] Added `guardOverrideToken` parameter to `index_codebase` in `mcp/tools.mdx`
- [x] Added multi-repo guard behavior section to `index_codebase` (from PR #175)

---

## 8. MCP configuration

- [~] Internal env vars (SHARC_WATCH_DEBOUNCE_MS, DEBUG, DEBUG_BACKEND_CLIENT, MCP_SERVER_NAME, MCP_SERVER_VERSION) intentionally not documented. Users only need SHARC_API_KEY. (Decision by David)

---

## 9. API key format

- [x] Standardized to `sk_mcp_e364ff9...` across all pages:
  - `mcp/configuration.mdx`
  - `getting-started/installation.mdx`
  - `getting-started/claude-code.mdx`
  - `getting-started/index.mdx`
  - `getting-started/other-clients.mdx`
  - `packages/index.mdx`
  - `index.mdx`

---

## 10. Splitter CodeChunk interface

- [x] Fixed in `packages/index.mdx`: `startLine`/`endLine` moved inside `metadata` object, added `language`, `filePath`, `chunkKind` fields

---

## 11. Embedding internals

- [~] Batch size, concurrency, throughput metrics intentionally removed from docs. Not user-facing. (Decision by David)
- [x] Replaced internal metrics in `architecture/embeddings.mdx` with real-world indexing time table (Hono ~30-45s, Next.js ~3-4min)

---

## 12. Speed estimates

- [x] Updated `getting-started/claude-code.mdx` with real-world benchmarks
- [x] Updated `architecture/embeddings.mdx` with indexing performance table

---

## 13. File extension tiers

- [x] Tier 1: Added `.pyw`, `.hpp`, `.cc`, `.cxx` to match actual code
- [x] Tier 3: Added `.env.example` to match actual code
- [x] Tier 4: Added `.kts`, `.less` to match actual code
- [x] Splitter package docs: Added `.cc`, `.cxx`, `.hpp` to C/C++ row

---

## 14. Missing documentation topics (for later consideration)

- [ ] `.sharcignore` file — partially covered in `file-watching.mdx` ignore precedence but could have its own section
- [ ] Plans & pricing page
- [ ] Enterprise plan mention
- [ ] Web dashboard docs (low priority — internal)

---

## Summary

| Category | Items Fixed | Won't Fix | Open |
|----------|-----------|-----------|------|
| docs.json template | 4 | 0 | 0 |
| Package versions | 2 | 0 | 0 |
| Tier language | 2 | 0 | 0 |
| Model branding | 1 | 1 | 0 |
| Plan limits | 0 | 1 | 1 |
| API endpoints | 3 | 0 | 0 |
| MCP tool params | 3 | 0 | 0 |
| MCP config | 0 | 1 | 0 |
| API key format | 7 | 0 | 0 |
| CodeChunk interface | 1 | 0 | 0 |
| Embedding internals | 1 | 1 | 0 |
| Speed estimates | 2 | 0 | 0 |
| File extensions | 4 | 0 | 0 |
| Missing topics | 0 | 0 | 4 |
| **Total** | **30** | **4** | **5** |

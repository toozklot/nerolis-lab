# Shared Vue (frontend + guides)

Vue SFCs here may be imported by **both** the main SPA (`frontend`) and the VitePress guides bundle (`guides/`).

## Constraints

- **No** Pinia stores, Vue Router, or other app-only singletons. Pass data via props or slots.
- **No** imports from `@/` app paths except other `@shared/...` modules. Prefer props and plain TypeScript from `sleepapi-common` when you need types.
- **Vuetify** is available in both apps; keep usage limited to components that work in VitePress SSR (guides use `vite-plugin-vuetify` with SSR).
- Prefer **scoped styles** and design tokens (`var(--color-*)`, etc.) so guides and app themes both look correct.

Adding a component here does not register it globally; each app registers what it needs (e.g. `guides/.vitepress/theme/index.ts`).

## `tsconfig.json` in this folder

Vite resolves the **nearest** `tsconfig.json` when compiling `.vue` files. CI often runs `npm install` only under `guides/`, so `frontend/node_modules` (and thus `@tsconfig/node20` from the root `frontend/tsconfig.json`) may be missing. This folder’s **standalone** `tsconfig.json` avoids `extends` to packages that only exist after a full frontend install, so `vitepress build` in guides still works.

# Qrati Connect — Remix Example

[![Qrati Connect — embeddable event photo galleries](public/qrati-connect-og.png)](https://qrati.com/connect)

Embed a live event photo gallery in Remix with guest uploads, full-screen lightbox, emoji reactions, and photo-contest leaderboards. [Explore Qrati Connect](https://qrati.com/connect) or [view the live Remix example](https://qrati.com/connect/remix-example).

## What this demonstrates

- Immediate `<qrati-connect>` rendering with no authentication gate.
- Remix UI client entry for host-controlled light/dark theme synchronization.
- Cookie consent with `vanilla-cookieconsent`.
- A framework-agnostic web component that works in server-rendered applications.

## Starter Shape

- `app/actions/controller.tsx` owns the top-level route actions.
- `app/actions/home-page.tsx` and `app/actions/document.tsx` render the route-owned starter UI.
- `app/actions/public/` contains the browser runtime entry and interactive prompt button.
- `app/routes.ts` defines the shared route contract used by server and browser modules for type-safe hrefs.
- `app/router.ts` wires routes to handlers and installs the standard Remix UI renderer used by actions.
- `app/assets.ts` owns the server-side asset pipeline used by the asset route and render middleware.
- Root `public/` contains static files served unchanged from the app root.

## Run locally

```bash
pnpm install
pnpm dev
```

Type-check the example:

```bash
pnpm typecheck
```

The widget is rendered by `app/actions/home-page.tsx` and reads its organization ID from `VITE_ORGANIZATION_ID`.

## Integration

```tsx
<qrati-connect
  organization-id="${VITE_ORGANIZATION_ID}"
  theme="light"
  router="hash"
/>
```

Learn more in the [Qrati Connect documentation and examples](https://qrati.com/connect).

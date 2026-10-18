# rc-frontend

Frontend for Redclew, built with [Next.js](https://nextjs.org) (App Router) + TypeScript.

## Development

```sh
pnpm install
pnpm dev      # http://localhost:3000
```

## Scripts

- `pnpm dev` — start the dev server
- `pnpm build` — production build (`output: "standalone"`)
- `pnpm start` — serve the production build
- `pnpm lint` — lint with oxlint

## Docker

The image is a two-stage build: it compiles the app, then runs the Next.js
standalone server (`node server.js`) directly in a `node:26-alpine` runtime —
no nginx involved. The server listens on `$PORT` (default `3000`), so it also
picks up the port injected by Cloud Run.

```sh
docker build -t rc-frontend .
docker run -p 3000:3000 rc-frontend
```

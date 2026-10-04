# my-backend

A minimal Node.js + Express backend with a `/health` endpoint and GitHub Actions CI (test + depguard dependency scanning).

## Requirements

- Node.js 20+
- npm

## Install

```bash
npm install
```

## Run

```bash
npm start        # production
npm run dev      # watch mode (node --watch)
```

Server listens on `process.env.PORT` or `3000`.

## Test

```bash
npm test
```

## Endpoints

| Method | Path     | Response            |
| ------ | -------- | ------------------- |
| GET    | /health  | `{ "status": "ok" }` |

## CI

Two workflows run on pull requests and pushes to `main`:

- `.github/workflows/ci.yml` — lint + tests on Node 20
- `.github/workflows/depguard.yml` — dependency scan via depguard

The depguard workflow requires a `DEPGUARD_API_KEY` repo secret (Settings → Secrets and variables → Actions).

## License

Private.

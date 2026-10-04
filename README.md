# my-backend

A minimal Go backend with a `/health` endpoint and GitHub Actions CI (test + depguard dependency scanning).

## Requirements

- Go 1.26+

## Run

```bash
go run .
```

Server listens on `PORT` env var or `3000`.

## Test

```bash
go test ./...
```

## Endpoints

| Method | Path     | Response            |
| ------ | -------- | ------------------- |
| GET    | /health  | `{ "status": "ok" }` |

## CI

Two workflows run on pull requests and pushes to `main`:

- `.github/workflows/ci.yml` — `go vet`, `gofmt`, `go test -race` on Go 1.26
- `.github/workflows/depguard.yml` — dependency scan via depguard

The depguard workflow requires a `DEPGUARD_API_KEY` repo secret (Settings → Secrets and variables → Actions).

## License

Private.

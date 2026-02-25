# static-website

Static website containerized with nginx and published to GHCR via GitHub Actions.

## Structure

```
index.html          # entry page
public/             # static assets (PNGs, etc.)
nginx.conf          # caching + SPA fallback
Dockerfile          # nginx:alpine image
```

## Deploy

Push to `main` and the workflow builds and publishes to:

```
ghcr.io/username/static-website:latest
```

The Dockerfile uses `nginx:alpine`, copies in the custom nginx config (7-day asset caching, SPA fallback), then copies the site files. The container serves on port 80.

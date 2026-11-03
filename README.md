# Appwrite

## Source development guide

### Product and architecture

Backend services for authentication, databases, storage, functions, messaging and realtime subscriptions.

PHP/Swoole HTTP API and asynchronous workers in `src/Appwrite`, configuration and bootstrap in `app/`, reusable Utopia libraries in `packages/`, and a separate web console in `apps/`. Docker Compose supplies databases, Redis, routing and runtime services.

### Requirements and local development

Docker Engine with Compose; PHP and Composer for host tooling. Runtime versions are pinned in `composer.json` and Dockerfiles.

Run these commands from the repository root unless a `cd` is shown:

```sh
docker compose up -d --build
```

These are source-defined entry points. Full dependency installation and service startup were not run during the portfolio maintenance audit; successful application deployment is not claimed.

### Environment configuration

Inspect `app/config` and the component-specific environment templates before startup. Supply local database, service URLs and integration credentials through untracked environment files or a secret manager. Do not copy production credentials into tracked files.

### Testing

```sh
docker compose exec appwrite test tests/unit/
```

The full application suite requires the dependencies and services described above. Source paths and documented script names were inspected, and `git diff --check` passed. Application tests and builds were not executed.

### Deployment and integrations

Start with `docker-compose.yml` and review image versions, persistent data paths, authentication, exposed ports and backups before production use. Integration implementations and configuration are in the source directories described above; generated API clients must stay in sync with server contracts.

### Source provenance and license

Imported from [appwrite/appwrite](https://github.com/appwrite/appwrite); upstream functionality and copyright belong to the original contributors. Local Git history begins with a 2026 source snapshot import, not historical authorship. The exact imported upstream revision is unknown. The upstream GitHub repository was created on 2019-04-08; the local year directory is organizational metadata.

Read [LICENSE](LICENSE) and nested license/notice files before redistribution; enterprise and bundled third-party components may use different terms. Restored root license text was retrieved verbatim from the official upstream repository during this maintenance pass.

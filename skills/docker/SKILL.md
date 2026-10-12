---
name: docker
description: Use for Dockerfiles, image builds, containers, Compose, networking, storage, and troubleshooting.
---

# Docker Skill Reference

## Scope

Use this context for Dockerfiles, image builds, containers, Compose, networking, volumes, and container troubleshooting. Follow the project's existing Docker and deployment conventions.

## Image and Container Practices

- Choose a trusted, maintained base image and pin versions deliberately; balance reproducibility with security updates.
- Use multi-stage builds when they reduce the final image or keep build tools out of runtime images.
- Add a `.dockerignore` so local environments, caches, credentials, and unrelated files are not sent to the build context.
- Run the application as a non-root user when practical.
- Keep containers focused on one primary service and let the process run in the foreground.
- Make configuration injectable at runtime. Never bake credentials into image layers, build arguments, or source.
- Use health checks when they meaningfully represent application readiness; do not confuse container liveness with dependency readiness.
- Use named volumes for persistent container data and understand that a container's writable layer is ephemeral.
- Bind only the necessary ports and avoid exposing administrative interfaces publicly.

## Troubleshooting

- Inspect build output, container status, logs, and effective configuration.
- Check the difference between host and container paths, ports, environment, DNS, and file permissions.
- Rebuild only when needed, and avoid deleting volumes or data as a generic cleanup step.
- Treat `docker compose down --volumes`, image pruning, and container removal as potentially destructive operations.
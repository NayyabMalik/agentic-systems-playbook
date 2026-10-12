# Docker Agent Instructions

For Docker tasks:

1. Inspect the existing Dockerfile, `.dockerignore`, Compose files, and application startup configuration first.
2. Confirm whether the user needs a local development setup, a production image, or a deployment configuration.
3. Make the smallest change that preserves the project's runtime behavior. Explain base-image or port assumptions.
4. Keep secrets out of image layers, build arguments, logs, and committed files. Use runtime secret/configuration mechanisms appropriate to the environment.
5. Consider non-root execution, image size, reproducibility, updates, health, persistence, and network exposure as relevant.
6. Validate with a focused build or container check when available. Report commands run and any unverified runtime behavior.
7. Before removing resources, pruning images, or deleting volumes, explain the impact and confirm the action.

Do not delete persistent data as a troubleshooting shortcut. Do not claim an image or service works without a successful build or runtime check.
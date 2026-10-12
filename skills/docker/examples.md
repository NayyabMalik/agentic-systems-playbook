# Docker Examples

These examples are starting points. Choose base-image versions and runtime details to match the application.

## Python Dockerfile with a Non-Root Runtime

```dockerfile
FROM python:3.12-slim

WORKDIR /app
COPY requirements.txt .
RUN pip install --no-cache-dir -r requirements.txt
COPY --chown=10001:10001 . .
USER 10001:10001

CMD ["python", "app.py"]
```

For production, consider a multi-stage build, dependency pinning, and a maintained base-image update process.

## Basic `.dockerignore`

```text
.git
.venv
__pycache__/
*.py[cod]
.env
.env.*
```

Keep required non-secret configuration files out of this list if the build genuinely needs them.

## Build and Run Locally

```powershell
docker build -t sample-app .
docker run --rm -p 8000:8000 sample-app
```

Confirm the application listens on `0.0.0.0` inside the container and that the mapped port matches its configuration.

## Inspect a Container

```powershell
docker ps
docker logs <container-name-or-id>
docker inspect <container-name-or-id>
```

Inspect output for secrets before sharing it.
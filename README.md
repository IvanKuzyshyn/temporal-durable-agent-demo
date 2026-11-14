# Durable AI Agent Demo with Temporal

A local chatbot demonstrating durable agent workflows with **Temporal, Go, Next.js, Postgres, and Ollama**. It includes saved conversations, human-approved web fetching and attachment analysis, child workflows, parallel activities, and crash-recoverable execution.

The app is single-user and localhost-only. It uses **qwen3.5:9b**; no hosted model or login is required.

## Setup and run

Install [mise](https://mise.jdx.dev/getting-started.html) and [Docker with Compose](https://docs.docker.com/get-started/get-docker/), then start Docker.

```sh
mise trust
mise run setup  # Install dependencies, build the app, and download the model
mise run up     # Start the stack
mise run down   # Stop the stack without deleting data or models
```

- **Chat:** http://127.0.0.1:13000
- **Temporal UI:** http://127.0.0.1:18080

The model download is several GB. Runtime configuration, logs, and local data live under `.webchat/` by default. Run `down` before rebuilding with `setup`.

**Runtime compatibility:** The qualified image-analysis profile requires a specific Ollama/model/MLX runner combination. Setup checks compatibility rather than silently falling back. Image-analysis limitations remain; see the qualification documents below before installing on another machine.

## Documentation

- [Operations: configuration, logs, backups, and troubleshooting](docs/web-chat-operations.md)
- [Architecture](docs/architecture.md)
- [Temporal workflows and recovery](docs/web-chat-temporal.md)
- [Testing and CI](docs/testing.md)
- [Qualification and known limitations](docs/web-chat-qualification.md) · [Image runtime requirements](docs/web-chat-image-profile.md)

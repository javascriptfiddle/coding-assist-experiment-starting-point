# Agent Notes

## Package Management
- Use `uv`, not pip/poetry. Run commands via `uv run ...` or activate `.venv`.
- Python 3.13 is required (pinned in `.python-version`).

## Project Purpose
- Shim exposing YouTube Music as an OpenSubsonic client.
- Uses FastAPI for the server, `ytmusicapi` for metadata, `yt-dlp` for streaming.

## Key Files
- `openapi.json` — OpenSubsonic API spec (the contract this shim implements). Do not treat as generated noise; it is the authoritative API definition.
- `main.py` — Entrypoint (currently a stub).

## Commands
- Run dev server: `uv run fastapi dev main.py`
- Install deps: `uv sync`
- Format / lint ad-hoc: `uv run ruff check .` or `uv run ruff format .` (ruff is installed but intentionally unconfigured)

## Project Structure
- As the project grows, use a standard FastAPI layout: `routers/`, `models/`, `services/`, etc.

## Conventions
- Methods should have type annotations for args and returns as well as docstrings.
- Use Pydantic for data modeling. Use modern Pydantic V2 conventions.
- Doc strings should use the Google style format with an args and returns sections.
- Write unit tests with modern pytest style, eg top level methods using `assert` and fixtures.

## Notes
- Readily use the "question" tool to get clarification.
- No tests, lint, or CI configs exist yet.
- The large `openapi.json` should be preserved and referenced when implementing endpoints.
- Use jq to help with reading json file efficiently.

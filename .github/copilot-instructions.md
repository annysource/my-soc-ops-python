# Copilot Workspace Instructions

## Mandatory Development Checklist

- [ ] `uv run uv sync` passes
- [ ] `uv run ruff check .` passes
- [ ] `uv run pytest` passes

## Project Overview

Soc Ops is a Social Bingo game built with Python, FastAPI, Jinja2, and HTMX. Players start a game, mark matching squares, and win with 5 in a row.

## Key Files

- `app/main.py` — routes, session middleware, and HTMX endpoints
- `app/game_logic.py` — board generation and bingo detection
- `app/game_service.py` — server-side game session state
- `app/templates/` — Jinja2 templates and reusable components
- `app/static/css/app.css` — Tailwind-like utility classes
- `tests/` — API and game logic coverage

## Workflow Notes

- Use full browser preview only; do not use VS Code Simple Browser.
- HTMX drives partial updates for `/start`, `/toggle/{square_id}`, `/reset`, and `/dismiss-modal`.
- State is kept in `GameSession` keyed by `session_id`.

## Useful Commands

```bash
uv run uv sync
uv run pytest
uv run ruff check .
uv run uvicorn app.main:app --reload --host 0.0.0.0 --port 8000
```

## References

- `README.md`
- `workshop/`
- `.github/instructions/general.instructions.md`
- `.github/instructions/css-utilities.instructions.md`
- `.github/instructions/frontend-design.instructions.md`

# api/

The Flask app. Add `Dockerfile`, `requirements.txt`, and `app.py` (an app factory) in
Step 3 of `GUIDE.md`.

- `routes/` — thin HTTP handlers only: parse request, call a service, return a status code.
- `models/` — DB access (SQLAlchemy models or raw SQL query functions).
- `services/` — the actual business logic (reservation rules, cache-aside, idempotency
  checks). Keep this out of `routes/` so it's testable without an HTTP request.

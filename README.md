# VedaVerse — academic AI prototype

This repository contains an early academic project exploring PDF question answering and related study tools. The Django app is under `rag/edu_rag/ed`; the `rag/` directory also contains experiments for document processing, audio, OCR, and a browser script.

The Django app includes views for PDF upload, document questions, quiz generation, text-to-speech, and a sketchbook flow. These are prototype features, not a production-ready service.

## Run locally

Requires Python. From the repository root, create a virtual environment and install the Django app's dependencies from the tracked manifest:

```bash
python -m venv .venv
source .venv/bin/activate
python -m pip install -r rag/requirements.txt
cd rag/edu_rag/ed
python manage.py migrate
python manage.py runserver
```

Open `http://127.0.0.1:8000`. On Windows, activate the environment with `.venv\Scripts\Activate.ps1` instead of the `source` command.

Set `DJANGO_SECRET_KEY` to a fresh random value before starting Django. `DJANGO_DEBUG` defaults to `false`; only set it to `true` for local development. Set `DJANGO_ALLOWED_HOSTS` to a comma-separated list when serving from non-local hostnames. Do not expose or deploy this learning project as-is. AI-backed views require `GEMINI_API_KEY` in the server environment. Never place it in browser code or commit its value.

## Source layout

- `rag/edu_rag/ed/` — Django project
- `rag/edu_rag/ed/app/` — document, quiz, audio, and sketch views
- `rag/requirements.txt` — dependencies used by the Django app
- `rag/main.py` — separate Selenium experiment

This is a learning project; the setup and AI integrations may need additional work.

# Sila Municipality Chatbot

A Thai-language chatbot that answers questions about municipal services using information retrieved from municipal documents. It also includes a staff interface for managing PDFs and viewing chat statistics.

[Live demo](https://chatbotmunicipality.vercel.app)

| Directory | Stack | Hosting |
| --- | --- | --- |
| `frontend/` | HTML, CSS, JavaScript | Vercel |
| `backend/` | Python, FastAPI, Gemini, Supabase Postgres and Storage | Railway |

The backend uses Gemini embeddings to find relevant document excerpts in Supabase and Gemini Flash-Lite to generate a Thai response from those excerpts. The Vercel frontend routes API requests to Railway through a same-origin rewrite.

The demo backend runs on Railway Trial credits and may become unavailable when the trial ends.

## Run the backend locally

In `backend/`, install `requirements.txt` in a Python virtual environment. Set `SUPABASE_URL`, `SUPABASE_SERVICE_ROLE_KEY`, `GEMINI_API_KEYS`, `SESSION_SECRET`, `ADMIN_USERNAME`, and `ADMIN_PASSWORD` in a local `.env` file. Full chat functionality requires a Supabase project with the application schema and document index already set up.

```sh
python -m pip install -r requirements.txt
python -m uvicorn main:app --reload
```

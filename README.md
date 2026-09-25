# Sara Al-Issa — Portfolio (Flask)

A small Flask app serving a single-page portfolio/CV site.

## Structure
```
website/
  app.py              # Flask app
  templates/index.html
  static/style.css
  static/resume.pdf   # downloadable CV
  requirements.txt
```

## Run locally
```bash
cd "C:\Users\USER\OneDrive - Balqa Applied University\Desktop\cv\website"
python -m venv .venv
.venv\Scripts\activate
pip install -r requirements.txt
python app.py
```
Then open **http://localhost:5000**.

## Deploy
Any Python host works — the app is a standard Flask app with no database.

**Render / Railway / Fly.io** — set the start command to:
```
gunicorn app:app
```

**Vercel** — add a `vercel.json`:
```json
{ "builds": [{ "src": "app.py", "use": "@vercel/python" }],
  "routes": [{ "src": "/(.*)", "dest": "app.py" }] }
```

To update the CV, replace `static/resume.pdf` with the same filename.


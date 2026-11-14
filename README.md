# All-in-One Telegram Helper Bot

Features: PDF/Image tools (Images→PDF, Merge PDFs, Compress, OCR), Translator (ml↔en),
Voice to Text, Scam Checker, Word Meaning.

## 1. Get the keys (all free)

| Key | Where | Required |
|---|---|---|
| `BOT_TOKEN` | Telegram → @BotFather → /newbot | Yes |
| `GROQ_API_KEY` | console.groq.com → API Keys | For Voice to Text |
| `SAFE_BROWSING_KEY` | Google Cloud Console → enable "Safe Browsing API" → Credentials → API key | Optional (better scam check) |

## 2. Test on your PC first (Windows)

```
pip install -r requirements.txt
set BOT_TOKEN=your_token
set GROQ_API_KEY=your_key
python bot.py
```
Open your bot in Telegram, send /start.
(OCR needs Tesseract installed on PC; skip testing OCR locally, it works on Render via Docker.)

## 3. Deploy free on Render

1. Make a GitHub repo, upload these 3 files: `bot.py`, `requirements.txt`, `Dockerfile`.
2. render.com → New → **Web Service** → connect the repo.
3. Runtime: **Docker**. Instance type: **Free**.
4. Environment variables: add `BOT_TOKEN`, `GROQ_API_KEY`, `SAFE_BROWSING_KEY`.
5. Deploy. After it's live, copy the URL (`https://yourbot.onrender.com`).

## 4. Keep it awake (free)

uptimerobot.com → Add monitor → HTTP(s) → paste Render URL → interval 5 minutes.

## Commands

- /menu – main menu
- /done – finish Images→PDF or Merge PDFs
- /lang – voice language Malayalam/English
- /cancel – cancel current task

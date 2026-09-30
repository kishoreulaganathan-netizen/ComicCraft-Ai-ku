# 🎨 ComicCraft – AI Comic Story Creator

ComicCraft turns a short story idea into a fully illustrated comic using **Google Gemini** models.
Built as part of the **Naan Mudhalvan (TN Skills)** project.

## Features
- Story → structured comic script (title, characters, panels, dialogue) via `gemini-2.5-flash`
- Panel artwork via `gemini-2.5-flash-image`, with a shared character sheet for consistent characters
- Choose art style, genre, language (English / Tamil / Hindi ...) and number of panels
- Download the comic as **PDF** or as **ZIP** (PNG panels + script.json)

## Tech Stack
Python · Streamlit · Google Gemini API (`google-genai`) · Pillow

## Setup
```bash
git clone https://github.com/<your-username>/ComicCraft.git
cd ComicCraft
python -m venv venv
venv\Scripts\activate        # Windows  (Mac/Linux: source venv/bin/activate)
pip install -r requirements.txt
copy .env.example .env        # then paste your Gemini API key inside .env
streamlit run app.py
```
Get a free API key: https://aistudio.google.com/apikey

## How it works
1. **Script generation** – Gemini returns JSON with title, character sheet and panel descriptions.
2. **Image generation** – each panel scene + character sheet is sent to the Gemini image model.
3. **Composition** – captions/dialogue are added under each panel and exported to PDF/ZIP.

## Project structure
```
ComicCraft/
├── app.py
├── requirements.txt
├── .env.example
├── .gitignore
└── README.md
```

## Future improvements
Speech bubbles on images, user-uploaded character reference photo, story history, multi-page comics.

## License
MIT

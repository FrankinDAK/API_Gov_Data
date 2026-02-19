# API_Gov_Data

Downloads and analyzes public comments from Regulations.gov using the official v4 API.

This project was built to download and analyze public comments on the VA Interim Final Rule 
concerning disability ratings and medication (Docket: VA-2026-VBA-0067, RIN 2900-AS49).

## Attribution

The core downloader (`comments_downloader.py`) was written by **Will Jobs** and is used here 
under the MIT License with gratitude.

- Original repo: https://github.com/willjobs/regulations-public-comments
- Blog post: https://willjobs.com/blog/downloading-public-comments
- License: MIT

## Project Structure

- `comments_downloader.py` — Will Jobs' original downloader (unchanged)
- `download_comments.py` — Our script to pull VA comments using your API key from `.env`
- `analyze_comments.py` — Our script to analyze themes, generate word clouds, and export to Excel
- `.env` — Your API key (never uploaded to GitHub)
- `.gitignore` — Ensures `.env` and data files stay local

## Setup

1. Clone the repo
2. Create a virtual environment: `python -m venv venv`
3. Activate it: `venv\Scripts\activate`
4. Install dependencies: `pip install requests pandas openpyxl python-dotenv scikit-learn matplotlib wordcloud python-dateutil`
5. Create a `.env` file with your API key: `API_KEY=your_key_here`
6. Get a free API key at: https://api.data.gov/signup/

## Usage

**Step 1 - Download comments:**
```
python download_comments.py
```

**Step 2 - Analyze comments:**
```
python analyze_comments.py
```

## The Rule We're Analyzing

The VA issued an Interim Final Rule (effective Feb 17, 2026) changing how disability ratings 
consider medication. Public comments are open until April 20, 2026.

- Docket: VA-2026-VBA-0067
- RIN: 2900-AS49
- Comment here: https://www.regulations.gov/commenton/VA-2026-VBA-0067-0001

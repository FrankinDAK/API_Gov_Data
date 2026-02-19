# API_Gov_Data

A tool for downloading and analyzing public comments from Regulations.gov using the official v4 API.

This project was originally built to help veterans and advocates analyze public comments on the 
VA Interim Final Rule concerning disability ratings and medication (Docket: VA-2026-VBA-0067, 
RIN 2900-AS49). The rule, which took effect February 17, 2026, changes how VA disability ratings 
consider the impact of medication — and has drawn significant public opposition from veterans 
groups, lawmakers, and legal advocates.

While this project started with that specific fight in mind, it is built to work with **any 
public comment docket on Regulations.gov**. If there is a rule or policy you care about, 
this tool can help you understand what the public is saying about it.

## Attribution

The core downloader (`comments_downloader.py`) was written by **Will Jobs** and is used here 
under the MIT License with gratitude. We forked his repo to show our appreciation and 
because his work made this project possible.

- Original repo: https://github.com/willjobs/regulations-public-comments
- Our fork: https://github.com/FrankinDAK/regulations-public-comments
- Blog post: https://willjobs.com/blog/downloading-public-comments
- License: MIT

## Project Structure

- `comments_downloader.py` — Will Jobs' original downloader. We did not change this file.
- `download_comments.py` — Our script. Point it at any docket and it pulls down all the comments.
- `analyze_comments.py` — Our script. Reads the downloaded comments and finds themes, generates word clouds, and exports everything to Excel.
- `.env` — A simple text file that holds your personal API key. This file stays on your computer only and is never uploaded to GitHub.
- `.gitignore` — Tells Git which files to leave alone, including your .env and any downloaded data files.

## Setup

1. Clone the repo
2. Create a virtual environment: `python -m venv venv`
3. Activate it: `venv\Scripts\activate`
4. Install dependencies: `pip install requests pandas openpyxl python-dotenv scikit-learn matplotlib wordcloud python-dateutil`
5. Create a `.env` file with your API key: `API_KEY=your_key_here`
6. Get a free API key at: https://api.data.gov/signup/

## Usage

**Step 1 - Download comments for any docket:**
```
python download_comments.py
```

**Step 2 - Analyze and export to Excel:**
```
python analyze_comments.py
```

## The Rule That Started This Project

The VA issued an Interim Final Rule (effective February 17, 2026) directing that disability 
ratings should reflect how a veteran functions *with* medication, rather than the underlying 
severity of the condition. Veterans groups argue this could penalize veterans for following 
their doctors' orders and force them to choose between their health and their benefits.

Public comments are open until **April 20, 2026**.

- Docket: VA-2026-VBA-0067
- RIN: 2900-AS49
- Comment here: https://www.regulations.gov/commenton/VA-2026-VBA-0067-0001

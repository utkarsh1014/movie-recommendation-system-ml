# 🎬 Movie Recommendation System

![Python](https://img.shields.io/badge/Python-3.10+-3776AB?style=flat&logo=python&logoColor=white)
![scikit-learn](https://img.shields.io/badge/scikit--learn-1.5.0-F7931E?style=flat&logo=scikit-learn&logoColor=white)
![License](https://img.shields.io/badge/License-MIT-green?style=flat)

A content-based movie recommender using **TF-IDF vectorization** and **cosine similarity** on genre data. Supports fuzzy title matching, similarity scores, and a persistent cached model.

---

## Demo

```
Enter movie name: incpetion

🔍 Closest match found: 'Inception'

  1. The Matrix          [████████████████████] 100%
  2. Rogue One           [████████████████████] 100%
  3. Interstellar        [██████████░░░░░░░░░░]  50%
  4. Avatar              [██████████░░░░░░░░░░]  50%
  5. Star Wars           [██████████░░░░░░░░░░]  50%
```

---

## Features

- TF-IDF vectorization — rare genres weighted higher for sharper matches
- Cosine similarity — angle-based scoring, unaffected by vector length
- Fuzzy matching — handles typos, partial names, and case differences
- Cached model — similarity matrix saved with `pickle`, no recomputation
- Interactive CLI — multi-query session with `list` and `quit` commands

---

## Quick Start

```bash
git clone https://github.com/your-username/movie-recommender.git
cd movie-recommender
pip install -r requirements.txt
python recommender.py
```

---

## Tech Stack

`Python` · `pandas` · `scikit-learn` · `pickle`

---

## Project Structure

```
movie-recommender/
├── recommender.py      # Core engine + CLI
├── save_model.py       # Cache model to disk
├── evaluate.py         # Precision@5 scoring
├── movies.csv          # Auto-generated dataset (100 movies)
├── requirements.txt
└── README.md
```

---

## How It Works

```
User Input → Fuzzy Match → TF-IDF Vector → Cosine Similarity → Top-N Results
```

Genre strings (e.g. `"SciFi Thriller"`) are vectorized with TF-IDF, then compared against all 100 movies using cosine similarity. Results are ranked by score and displayed with a visual progress bar.

---

## Dataset

100 movies — Hollywood + Bollywood — across 15 genre tags:
`Action` `SciFi` `Drama` `Horror` `Comedy` `Animation` `Romance` `Thriller` `Fantasy` `Adventure` `Sports` `Biography` `Crime` `Musical` `Finance`

---

## License

MIT © [Your Name](https://github.com/your-username)

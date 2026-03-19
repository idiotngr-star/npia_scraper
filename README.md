# 🚀 Npia Archiver
**Stop scrolling through 500 pages of stagnation. Start finding the next breakthrough.**

### 🎯 The Problem
Standard web novel rankings are biased toward longevity. A novel with 1,000 chapters and 2,000 favorites is "top ranked," but it’s often stagnant. Meanwhile, a "Sleeper Hit" with 20 chapters and 500 favorites—a massive growth signal—is buried on page 40 of the "New" tab.

### 💡 The Solution
This isn't a scraper; it's a **Signal Filter**. 
- **Automated Intelligence:** It identifies "Ghost IDs" and deletes them from your sight.
- **Dynamic Quality Control:** It holds older novels to a higher standard (Legacy IDs) while giving newer works a chance to prove their potential (Rising IDs).
- **18+ Content Enforcement:** Uses an adult-trope signature engine (NTL, NTR, Hypnosis, etc.) to force-classify 19+ content even if metadata is hidden.
- **Sleeper Ratio:** Calculates Favorites per Episode to highlight the most "dense" high-quality content on the platform.

---

## 🛠️ The Intelligence Engine
| Logic Gate | Requirement | Purpose |
| :--- | :--- | :--- |
| **Pre-Check** | SQLite Union Search | Skips redundant work; 0ms latency for known IDs. |
| **Sanity Check** | "Alarm" Keyword | Detects custom 404/Removed pages without a browser. |
| **NSFW Override** | `ADULT_RED_FLAGS` | Classifies 19+ content based on trope tags (e.g., #NTL, #조교). |
| **The Filter** | Favs > 10, Eps > 1 | Purges "trash" before it ever hits your database. |

---

## 📊 The "Encyclopedia" Dashboard
We use a **High-Density UI** to present data as actionable intelligence:
- **📂 Intelligence Vault:** Persistent storage with **Soft-Red Highlighting** for 18+ entries to improve visual scanning.
- **📊 Market Share:** A donut-style trope analysis bar showing the top genres in the sleeper market.
- **📥 Translation Audit:** A dedicated tab to manage "Translation Debt" by finding and mapping new Korean tags.
- **Persistent Caching:** Powered by SQLite WAL mode, ensuring the UI stays snappy even as the "Encyclopedia" grows.

---

## 🛠️ Tech Stack

| Layer | Technology | Purpose |
| :--- | :--- | :--- |
| **Frontend** | [Streamlit](https://streamlit.io/) | Reactive dashboard with custom row-styling logic. |
| **Engine** | [HTTPX](https://www.python-httpx.org/) | Sync/Async HTTP client for high-speed, non-blocking scouting. |
| **Parsing** | [BeautifulSoup4](https://www.crummy.com/software/BeautifulSoup/) | Robust HTML extraction for deeply nested Korean tags. |
| **Database** | [SQLite3](https://www.sqlite.org/) | Atomic persistent storage with UPSERT logic for stat tracking. |
| **Visualization**| [Plotly](https://plotly.com/) | Interactive Donut Charts for trope distribution. |

---

## 🚀 Quick Start Guide

### 1. Clone & Install
Ensure you have Python installed, then run:
```bash
git clone https://github.com/idiotngr-star/npia_scraper
cd npia_scraper
pip install -r requirements.txt
streamlit run main.py

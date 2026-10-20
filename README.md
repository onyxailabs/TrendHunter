# TrendHunter — TikTok Trend Scraper for Pakistan

TrendHunter is a lightweight Python automation that fetches the top trending TikTok hashtags for Pakistan from the TikTok Creative Center API and saves them to a CSV file. Useful for content creators, marketers, and researchers who want to track what is going viral in Pakistan.

## How it works

- `bot.py` queries the TikTok Creative Center hashtag endpoint (7-day period, region PK) and writes the top 10 hashtags with popularity scores to `trends.csv`.
- `.github/workflows/scrape.yml` ("Viral Scraper") runs the script on demand via `workflow_dispatch` on Python 3.9, installs dependencies from `requirements.txt`, then auto-commits the updated `trends.csv` back to the repo.
- `requirements.txt` lists the Python dependencies (`requests`).
- `trends.csv` holds the latest snapshot of the top 10 trending hashtags with their popularity scores.

## Run it locally

```bash
pip install -r requirements.txt
python bot.py
```

Then open `trends.csv` to see the latest top 10 hashtags.

## Notes

- The script queries an unofficial TikTok internal endpoint; if TikTok changes it, the scraper can break.
- The region is currently hardcoded to Pakistan (PK) in `bot.py` — edit the request URL to target another region.

---

**Built by Muhammad Mohsin — Onyx AI** · [YouTube](https://www.youtube.com/@onyxaipk) · [All products](https://mohsina91.gumroad.com) · [Catalog](https://onyxailabs.github.io/Catalog/)

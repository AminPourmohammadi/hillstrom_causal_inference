# Data

This folder is where `hillstrom.csv` belongs. The file isn't committed to the repo (see `.gitignore`) because the original publisher, not this project, controls its distribution.

## Get the data

Download the original CSV from Kevin Hillstrom's MineThatData blog:

**http://www.minethatdata.com/Kevin_Hillstrom_MineThatData_E-MailAnalytics_DataMiningChallenge_2008.03.20.csv**

Save it as `data/hillstrom.csv`. It's about 4 MB, 64,000 rows, 12 columns.

If that link is ever unreachable, both notebooks fall back to `scikit-uplift`'s bundled downloader automatically:

```python
from sklift.datasets import fetch_hillstrom
bunch = fetch_hillstrom(target_col="all")
```

## Expected columns

| Column | Type | Meaning |
|---|---|---|
| `recency` | int | Months since last purchase |
| `history_segment` | text | `history`, binned into ranges |
| `history` | float | Dollars spent in the past year |
| `mens` | 0/1 | Bought men's merchandise in the past year |
| `womens` | 0/1 | Bought women's merchandise in the past year |
| `zip_code` | text | Urban / Suburban (spelled "Surburban" in the source file) / Rural |
| `newbie` | 0/1 | New customer in the past 12 months |
| `channel` | text | Phone / Web / Multichannel |
| `segment` | text | Randomly assigned arm: Mens E-Mail / Womens E-Mail / No E-Mail |
| `visit` | 0/1 | Visited the site in the following two weeks |
| `conversion` | 0/1 | Purchased in the following two weeks |
| `spend` | float | Dollars spent in the following two weeks |

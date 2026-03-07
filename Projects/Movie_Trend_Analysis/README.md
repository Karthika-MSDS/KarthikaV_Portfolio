# 🎬 Movies Data Analytics Project

## **Project Overview**

This project consolidates, cleans, and analyzes movie datasets from multiple sources to create a **comprehensive dataset for movie analytics**. The goal is to understand movie metadata, box office performance, and audience reception using **Python, APIs, and SQL**.

**Key objectives:**

* Clean and preprocess large movie metadata datasets.
* Extract historical box office data from Box Office Mojo.
* Collect detailed movie information from OMDb API.
* Merge multiple datasets for enriched analysis.
* Create a SQLite database for easy querying.

---

## **Datasets**

1. **`movies_metadata.csv`** – Original movie metadata file (IMDb-like info).
2. **Box Office Mojo Data** – Extracted world and domestic revenue from 1977–2020.
3. **OMDb API Data** – Detailed movie info from 1978–2023 (awards, ratings, languages, countries).
4. **`merged_movies_data.csv`** – Final cleaned and merged dataset combining all sources.

---

## **Project Workflow**

### **1. Data Cleanup (movies_metadata.csv)**

* Drop unnecessary columns: `adult`, `homepage`, `poster_path`, `overview`, etc.
* Remove duplicates and invalid rows.
* Validate `genres`, `production_companies`, `production_countries`, and `spoken_languages`.
* Filter revenue > 10,000, budget > 50,000, runtime 90–180 minutes.
* Derive **multigenre, multilanguage, multicompany, multicountry** flags.
* Fuzzy match `original_title` and `title` to ensure consistency.
* Format numeric columns (`revenue`, `budget`, `popularity`) and vote counts.
* Rename columns and standardize lowercase naming.

**Output:** `cleaned_movies_metadata.csv`

---

### **2. Box Office Mojo Extraction**

* Scrape worldwide box office data from 1977–2020 using **BeautifulSoup**.
* Clean `Worldwide`, `Domestic`, and calculate `Foreign` & `%` contributions.
* Remove duplicates, filter invalid rows, and rank movies by `Worldwide`.

**Output:** `cleaned_box_office_data.csv`

---

### **3. OMDb API Extraction**

* Fetch movies by year (1978–2023) using OMDb API.
* Extract detailed info: awards, wins, nominations, directors, runtime, ratings, languages, countries, production companies.
* Determine multigenre, multilanguage, multicompany, multicountry flags.

**Output:** `formatted_API_data.csv`

---

### **4. Data Merging**

* Store all datasets (`file_dataset`, `website_dataset`, `api_dataset`) in **SQLite database**.
* Merge datasets using `original_title` / `Release Group` / `Title` keys.
* Include key metrics: `budget`, `box_office`, `imdb_rating`, `runtime`, `votes`, awards, and flags for multiple genres/languages/companies/countries.

**Output:** `merged_movies_data.csv`

---

### **5. Key Libraries**

* **Data Handling:** `pandas`, `numpy`, `ast`, `re`, `csv`
* **Data Cleaning & Validation:** `fuzzywuzzy`, `langcodes`
* **Web Scraping:** `requests`, `BeautifulSoup`
* **API Requests:** `requests`, `json`
* **Database:** `sqlite3`
* **Visualization:** `matplotlib`, `seaborn`, `tabulate`
* **Jupyter Display:** `IPython.display`

---

### **6. How to Run**

1. Clone the repository:

```bash
git clone <repository-url>
cd movies-data-project
```

2. Install required libraries:

```bash
pip install pandas numpy requests beautifulsoup4 fuzzywuzzy langcodes matplotlib seaborn tabulate
```

3. Place datasets (`movies_metadata.csv`, `OMDbAPIkey.json`) in the project folder.
4. Run the notebook/script sequentially to clean, extract, and merge data.
5. Outputs (`cleaned_movies_metadata.csv`, `cleaned_box_office_data.csv`, `formatted_API_data.csv`, `merged_movies_data.csv`) will be saved in the project directory.

---

### **7. Outputs**

| File                          | Description                                                           |
| ----------------------------- | --------------------------------------------------------------------- |
| `cleaned_movies_metadata.csv` | Cleaned movie metadata with runtime, revenue, budget filters.         |
| `cleaned_box_office_data.csv` | Box office data with worldwide, domestic, foreign revenue.            |
| `formatted_API_data.csv`      | OMDb API extracted details with ratings, awards, and production info. |
| `merged_movies_data.csv`      | Consolidated dataset combining all sources for analysis.              |

---

### **8. Notes**

* Ensure **OMDb API key** is valid in `OMDbAPIkey.json`.
* Data extraction may take time due to multiple years and API calls.
* SQLite database `movies_data.db` is used for easy querying.

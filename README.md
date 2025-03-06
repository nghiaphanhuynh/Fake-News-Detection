# VNExpress News Scraper and Fake News Generator

## Project Description
This project is a tool for scraping news articles from the VNExpress website and processing them to create "True," "Fake," and "Half-true" news versions. The codebase is written in Python and utilizes libraries such as `requests`, `BeautifulSoup`, and `json` for data collection and processing.

### Key Features
1. **News Scraping**: Automatically crawls articles from various VNExpress categories.
2. **Fake News Generation**: Replaces all numbers in the content with random numbers to create fully fake news.
3. **Half-true News Generation**: Randomly replaces 50% of the numbers in the content.
4. **Data Storage**: Saves data into separate JSON files (`true_news.json`, `fake_news.json`, `half_true_news.json`).
5. **Text Preprocessing**: Downloads a Vietnamese stopwords list for text cleaning.

---

## Installation

### Requirements
- Python 3.7 or higher
- Required libraries:
  ```bash
  pip install requests beautifulsoup4 pandas numpy matplotlib scikit-learn tensorflow underthesea transformers
  ```

### Setup Instructions
1. Clone this repository to your local machine:
   ```bash
   git clone https://github.com/username/vnexpress-news-scraper.git
   cd vnexpress-news-scraper
   ```
2. Install the required libraries:
   ```bash
   pip install -r requirements.txt
   ```
   (If there’s no `requirements.txt`, manually install the libraries listed above.)

3. Run the code:
   - Open `scraper.ipynb` in Jupyter Notebook or convert it to `scraper.py` and run:
     ```bash
     python scraper.py
     ```

---

## Usage

### 1. Data Collection
- The code in cell 2 scrapes articles from VNExpress categories (technology, world, current events, etc.) and saves them to `vnexpress_news_today.json`.
- Output: Each article is stored with fields: `doc_id`, `content`, `label`, `source`, `date`, `sentiment`.

### 2. Fake News Creation
- Cell 3 replaces all numbers in the content with random numbers and saves the result to `vnexpress_fakenews_today.json` with `label: "Fake"`.

### 3. Half-true News Creation
- Cell 4 randomly replaces 50% of the numbers in the content and saves the result to `vnexpress_Half-true_today.json` with `label: "Half-true"`.

### 4. Data Merging and Organization
- Cell 5 merges temporary JSON files into main files (`true_news.json`, `fake_news.json`, `half_true_news.json`) and deletes the temporary files.

### 5. Stopwords Download
- Cell 6 downloads a Vietnamese stopwords list from a public source for text preprocessing.

---

## Directory Structure
```
vnexpress-news-scraper/
│
├── scraper.ipynb              # Main source code file (Jupyter Notebook)
├── vietnamese-stopwords.txt   # File containing Vietnamese stopwords
├── true_news.json            # True news data
├── fake_news.json            # Fake news data
├── half_true_news.json       # Half-true news data
└── README.md                 # This file
```

---

## Notes
- **Crawl Rate**: The code uses `time.sleep(1)` to avoid being blocked by VNExpress. Adjust the delay if needed.
- **Data Size**: JSON files may grow large with extensive scraping. Use a `.gitignore` file to exclude data files from GitHub:
  ```
  *.json
  vietnamese-stopwords.txt
  ```
- **Customization**: Add new categories by modifying the `categories` list in the code.

---

## Contributing
- To contribute, please submit a pull request or report issues via the Issues tab on GitHub.

## Author
- [Your Name] (Replace with your name or GitHub username)

## License
This project is licensed under the [MIT License](LICENSE).


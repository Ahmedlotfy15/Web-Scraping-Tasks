# Web Scraping and File Handling in Python

This repository demonstrates several tasks involving web scraping and file handling using Python libraries like `requests`, `BeautifulSoup`, and `urllib`. Below are the key features and functions provided in this project:

## Features

### 1. Extracting and Saving Webpage Content

**Function:** `GetPage(Link, FileName)`

- **Purpose:** Downloads a webpage, extracts its paragraph content, and saves it into a local file.
- **Key Steps:**
  - Use `requests` to fetch the webpage content.
  - Parse the content using `BeautifulSoup`.
  - Extract all paragraph tags (`<p>`) and save their text to a specified file.
- **Example:**

  ```python
  GetPage('https://ar.wikipedia.org/wiki/%D8%A7%D9%84%D9%86%D8%A7%D8%AF%D9%8A_%D8%A7%D9%84%D8%A3%D9%87%D9%84%D9%8A_(%D9%85%D8%B5%D8%B1)', 'Ahly.text')
  ```

### 2. Downloading and Saving a Text File

**Function:** `download_and_save_file(url, file_name)`

- **Purpose:** Downloads content from a URL and saves it locally as a text file.
- **Key Steps:**
  - Use `urllib.request` to open and read the URL content.
  - Decode the content and write it to a local file.
- **Example:**

  ```python
  download_and_save_file('https://raw.githubusercontent.com/HeshamAsem/NLTK/master/Files/HardTimes.txt', 'HardTimes.txt')
  ```

### 3. Scraping Links Based on Specific Characters

**Description:**

- Dynamically generates URLs based on Arabic characters.
- Extracts and filters links from these pages, targeting specific patterns.

**Process:**
- **Input:** A list of Arabic characters.
- **Steps:**
  - Generate URLs using each character.
  - Scrape the page for all `<a>` tags containing `href` attributes.
  - Filter the links based on specific patterns.
- **Example:**

  ```python
  T = 'دجحخهعغفقثصضذشسيبلاتنمكطظزوةيارؤءئ'
  urls = []
  for t in set(T):
      url = f'https://www.webteb.com/drug/list/{t}'
      # Scrape and process links...
  U = [i for i in urls if 'https://www.webteb.com/drug' in i]
  ```

### 4. Filtering Unique URLs

- Filters and counts unique URLs scraped from WebTeb’s drug directory.





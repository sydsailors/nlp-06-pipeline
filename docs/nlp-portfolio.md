# Web Mining & Applied NLP Portfolio - Sydney Sailors

## Overview
This portfolio summarizes my work in Web Mining & Applied Natural Language Processing (NLP). I designed and implemented repeatable EVLT pipelines across multiple modules to extract, clean, analyze, and interpret real world text data from web pages, APIs, and documents.

## 1. NLP Techniques Implemented
I implemented the following NLP techniques across my projects, with concrete evidence in code and outputs:
- Tokenization
  - Converts raw text into smaller units that can be analyzed computationally
  - One of the first steps in every project
  - Examples:
    - Text preprocessing notebook: [text_preprocessing_sailors.ipynb](https://github.com/sydsailors/nlp-02-text-preprocessing/blob/main/notebooks/text_preprocessing_sailors.ipynb)
    - Text exploration notebook: [nlp_corpus_explore_sailors_phase_5.ipynb](https://github.com/sydsailors/nlp-03-text-exploration/blob/main/notebooks/nlp_corpus_explore_sailors_phase_5.ipynb)
- Frequency analysis
  - Frequency distribution shows how often each token appears to identify which words are most common in a dataset
  - Examples:
    - Text exploration notebook: [nlp_corpus_explore_sailors_phase_5.ipynb](https://github.com/sydsailors/nlp-03-text-exploration/blob/main/notebooks/nlp_corpus_explore_sailors_phase_5.ipynb)
    - Pipeline wordcloud: [sailorsp5_wordcloud.png](https://github.com/sydsailors/nlp-06-pipeline/blob/main/data/processed/sailorsp5_wordcloud.png)
    - Pipeline top tokens: [sailorsp5_top_tokens.png](https://github.com/sydsailors/nlp-06-pipeline/blob/main/data/processed/sailorsp5_top_tokens.png)
- Text cleaning and normalization
  - Text preprocessing prepares raw text for analysis by cleaning and standardizing it
  - Common steps include tokenizing, removing punctuation, removing stop words, and converting text to lowercase
  - Examples:
    - Text preprocessing notebook: [text_preprocessing_sailors.ipynb](https://github.com/sydsailors/nlp-02-text-preprocessing/blob/main/notebooks/text_preprocessing_sailors.ipynb)
    - Text exploration notebook: [nlp_corpus_explore_sailors_phase_5.ipynb](https://github.com/sydsailors/nlp-03-text-exploration/blob/main/notebooks/nlp_corpus_explore_sailors_phase_5.ipynb)
- API-based text analysis (and JSON)
  - JSON:
    - When working with JSON data, you must inspect the structure before extracting fields
    - JSON arrays are represented as Python lists
    - JSON objects are represented as Python dictionaries
  - Example:
    - API text data pipeline: [pipeline_api_json.py](https://github.com/sydsailors/nlp-04-api-text-data/blob/main/src/nlp/pipeline_api_json.py)
- Web scraping / content extraction from HTML
  - Extracting text from HTML using BeautifulSoup
  - Examples:
    - Web documents [pipeline_web_html.py](https://github.com/sydsailors/nlp-05-web-documents/blob/main/src/nlp/pipeline_web_html.py)
- Sentiment analysis
  - spaCy was used for tokenization, stopword removal, and preprocessing
  - Example:
    - Transform stage [stage03_transform_sailorsp5.py](https://github.com/sydsailors/nlp-06-pipeline/blob/main/src/nlp/stage03_transform_sailorsp5.py)

## 2. Systems and Data Sources
I analyzed text from multiple real-world sources, each with different structures and challenges:
- HTML Web Pages
  - Semi-structured content with inconsistent tags and nested elements
  - Required selective extraction
- JSON APIs
  - Structured but variable schemas across records
  - Validation was an important step
- Plain text
  - Cleaner inputs but required normalization and token handling
- To handle messy or inconsistent data, I checked for missing or empty fields during validation, logged extraction errors instead of failing pipelines, and normalized text before analysis to ensure comparability.

## 3. Pipeline Structure (EVTL)
Each project follows a clear EVTL pipeline pattern:
- Extract
  - Collects text from web pages or APIs
  - Example:
    - [stage01_extract.py](https://github.com/sydsailors/nlp-06-pipeline/blob/main/src/nlp/stage01_extract.py)
- Validate
  - Confirms required fields exist
  - Log record counts and skipped invalid entries
  - Example:
    - [stage02_validate_sailorsp5.py](https://github.com/sydsailors/nlp-06-pipeline/blob/main/src/nlp/stage02_validate_sailorsp5.py)
- Transform
  - Clean and normalize text
  - Tokenize words and sentences
  - Example:
    - [stage03_transform_sailorsp5.py](https://github.com/sydsailors/nlp-06-pipeline/blob/main/src/nlp/stage03_transform_sailorsp5.py)
- Load
  - Store results in Pandas DataFrames
  - Generate logs, summaries, and visualizations
  - Example:
    - [stage04_analyze_sailorsp5.py](https://github.com/sydsailors/nlp-06-pipeline/blob/main/src/nlp/stage04_analyze_sailorsp5.py)

## 4. Signals and Analysis Methods
I computed multiple text signals to support analysis:
- Word frequency
  - Ranked unigrams and n-grams to identify dominant themes
- Context and co-occurrence
  - Compared frequent tokens across documents and sources
- Keyword extraction
  - Identified most frequent terms after stopword removal
- Metadata signals
  - Sentence count, word count, author count

## 5. Insights
My analyses revealed several meaningful patterns:
- High-frequency tokens consistently reflected topic focus and framing
- Sentence count and word count helped explain readability differences
- Sentiment scores often contradicted expectations based on headlines alone
- Cleaning and normalization significantly altered top-token rankings, demonstrating why preprocessing matters
These insights reinforced the importance of structured pipelines and validation when working with real-world text.

## 6. Representative Work
[NLP 5: Web Documents](https://github.com/sydsailors/nlp-05-web-documents)
- I built a full EVTL pipeline to extract, clean, tokenize, and analyze text from A Project Gutenberg web page, producing paragraph and word counts as well as average words per paragraph.

[NLP 6: Pipeline](https://github.com/sydsailors/nlp-06-pipeline)
- This custom application is an educational web mining on an abstract about Boston star-black hole binaries. I also added a new derived column for sentence count in the abstract in the Transform stage. Results of analysis were that this abstract was submitted on April 16, 2026 and had a total of 151 words in 7 sentences. Some top tokens include BSBH (Boston star - black hole), BHBH, GW, and BS.
![Wordcloud]((https://github.com/sydsailors/nlp-06-pipeline/blob/main/data/processed/sailorsp5_wordcloud.png))

## 7. Skills
Through these projects, I demonstrated the ability to:
- Build repeatable NLP pipelines using Python
- Extract and clean text from messy real-world sources
- Perform tokenization, frequency analysis, and sentiment analysis
- Work confidently with HTML, JSON, and plain text
- Validate data and handle inconsistent inputs safely
- Communicate technical results clearly using Markdown, logs, and structured outputs

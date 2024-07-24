# Text Analysis and Sentiment Scoring Project

## Overview

This project implements a system for extracting textual data from given URLs and performing comprehensive text analysis to compute various metrics. The analysis includes sentiment scoring, readability assessment, and other linguistic features. This tool is valuable for content strategy, market research, and competitor analysis in various domains.

## Features

- Data extraction from URLs
- Sentiment analysis (positive/negative scores, polarity, subjectivity)
- Readability metrics (average sentence length, percentage of complex words, Fog Index)
- Linguistic analysis (word count, syllable count, personal pronouns, average word length)
- Handling of various text encodings
- Output generation in Excel format

## Requirements

- Python 3.x
- pandas
- requests
- beautifulsoup4
- nltk
- openpyxl (for Excel file handling)

## Installation

1. Clone this repository:
   ```
   git clone https://github.com/yourusername/text-analysis-project.git
   cd text-analysis-project
   ```

2. Install required packages:
   ```
   pip install pandas requests beautifulsoup4 nltk openpyxl
   ```

3. Download NLTK data:
   ```python
   import nltk
   nltk.download('punkt')
   ```

## Usage

1. Prepare your input file:
   - Create an Excel file named `Input.xlsx` with columns `URL_ID` and `URL`.
   - Place it in the project root directory.

2. Prepare sentiment word lists:
   - Create text files `positive-words.txt` and `negative-words.txt`.
   - Each file should contain one word per line.

3. Prepare stop words files:
   - Create separate text files for different categories of stop words (e.g., `StopWords_Names.txt`, `StopWords_Geographic.txt`, etc.).
   - Each file should contain one word per line.

4. Run the script:
   ```
   python text_analysis_script.py
   ```

5. Check the output:
   - The script will generate an Excel file named `Output Data Structure.xlsx`.
   - This file will contain all computed metrics for each analyzed URL.

## Project Structure

- `text_analysis_script.py`: Main Python script containing all the logic.
- `Input.xlsx`: Input file with URLs to analyze.
- `positive-words.txt`: List of positive words for sentiment analysis.
- `negative-words.txt`: List of negative words for sentiment analysis.
- `StopWords_*.txt`: Various stop words files.
- `Output Data Structure.xlsx`: Generated output file with analysis results.

## Functions

### Main Functions:

- `safe_read_file(file_path)`: Safely reads a file with multiple encoding attempts.
- `extract_article(url)`: Extracts article text from a given URL.
- `clean_text(text, stop_words)`: Cleans the text by removing stop words and non-alphabetic tokens.
- `calculate_sentiment_scores(text, positive_words, negative_words)`: Calculates sentiment scores for the given text.
- `calculate_readability_metrics(text)`: Calculates readability metrics for the given text.
- `analyze_text(url, stop_words, positive_words, negative_words)`: Performs full text analysis on the article at the given URL.

### Utility Functions:

- `count_complex_words(text)`: Counts the number of complex words in the text.
- `count_syllables(word)`: Counts the number of syllables in a word.
- `count_personal_pronouns(text)`: Counts the number of personal pronouns in the text.

## Output Format

The output Excel file contains the following columns:

- URL_ID
- URL
- positive_score
- negative_score
- polarity_score
- subjectivity_score
- avg_sentence_length
- percentage_complex_words
- fog_index
- avg_words_per_sentence
- complex_word_count
- word_count
- syllable_per_word
- personal_pronouns
- avg_word_length

## Limitations and Future Improvements

- The current implementation may not handle all types of web pages efficiently. Future versions could implement more robust web scraping techniques.
- Sentiment analysis is based on word lists. Implementing machine learning models could improve accuracy.
- The script processes URLs sequentially. Parallel processing could significantly improve performance for large datasets.
- Error handling and logging could be enhanced for better diagnostics and reliability.

## Contributing

Contributions to this project are welcome. Please fork the repository and submit a pull request with your changes.

## License

[MIT License](LICENSE)

## Contact

For any queries or suggestions, please open an issue in the GitHub repository.

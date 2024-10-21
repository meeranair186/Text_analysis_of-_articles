# License

This project is open-source and available under the [MIT License](LICENSE).

# Finance Article Text Analysis

This project involves text analysis of finance articles to calculate various readability and sentiment scores such as POSITIVE SCORE, NEGATIVE SCORE, POLARITY SCORE, SUBJECTIVITY SCORE, and others based on the text data.

## Project Structure

### Files and Folders
- `scrape.ipynb`: Jupyter Notebook used to scrape the text of finance articles.
- `text_analysis.ipynb`: Jupyter Notebook that calculates various text analysis scores from the scraped articles.
- `input.xlsx`: Input Excel file containing the list of articles to be scraped **(can input you're own article data inplace of it by changing it in scrape.ipynb file )**.
- `output_with_paragraphs.xlsx`: Generated after running `scrape.ipynb`, this file contains the scraped text and serves as input to `text_analysis.ipynb`.
- `Processed_Output.xlsx`: The final output file containing the calculated scores for each article.
- `MasterDictionary/`: Contains:
  - `positive-words.txt`: A dictionary of positive words.
  - `negative-words.txt`: A dictionary of negative words.
- `StopWords/`: Contains various stop word lists (e.g., `StopWords_Auditor.txt`, `StopWords_Currencies.txt`) used to filter unnecessary words before text analysis **(can input you're own stopwords)**.
- `nltk_data/`: Contains the `punkt` tokenizer and `stopwords` necessary for NLTK operations.

### Variables Calculated
- **POSITIVE SCORE**: The number of positive words found in the text.
- **NEGATIVE SCORE**: The number of negative words found in the text.
- **POLARITY SCORE**: Indicates whether the text is positive or negative. Calculated as:
- Polarity Score = (Positive Score – Negative Score) / ((Positive Score + Negative Score) + 0.000001)
- - **SUBJECTIVITY SCORE**: Indicates how subjective or objective the text is. Calculated as:
  - Subjectivity Score = (Positive Score + Negative Score) / (Total Words + 0.000001)
  - **READABILITY METRICS**:
- **Average Sentence Length**: Total words / Total sentences.
- **Percentage of Complex Words**: Complex words / Total words.
- **Fog Index**: Measure of text difficulty, calculated as:
  ```
  Fog Index = 0.4 * (Average Sentence Length + Percentage of Complex Words)
  ```
- **Complex Word Count**: Number of words with more than two syllables.
- **Word Count**: Total number of words in the text.
- **Syllables Per Word**: Average number of syllables per word.
- **Personal Pronouns**: Count of personal pronouns like “I”, “we”, “us”, etc.
- **Average Word Length**: Total number of characters / Total number of words.

## How to Run
## Steps to Run the Notebooks

1. **Scrape Finance Articles**
   - Run `scrape.ipynb` to scrape the text of finance articles and generate `output_with_paragraphs.xlsx`.

2. **Analyze Text Data**
   - Run `text_analysis.ipynb` to calculate the scores from the scraped articles and generate `Processed_Output.xlsx`.

## Notes
- Ensure that the `MasterDictionary` and `StopWords` folders are in the same directory as the Jupyter notebooks.
- The NLTK data required for tokenization and stopwords should be downloaded into the `nltk_data` folder.

## Prerequisites
- Install the required Python libraries using:
```bash
pip install pandas nltk openpyxl



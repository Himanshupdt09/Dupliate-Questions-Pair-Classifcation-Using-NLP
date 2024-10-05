# Duplicate Question Pairs Classification

This project solves a **Duplicate Question Pairs Classification** problem, which is widely used in modern search engines. When a user queries a search engine, it first checks whether the query has been previously asked. If a match is found, the search engine retrieves the solution from the original question.

## Dataset

The dataset is sourced from the [Quora Question Pairs competition on Kaggle](https://www.kaggle.com/c/quora-question-pairs). It contains:

- **id**: Unique identifier of a training set question pair.
- **qid1** and **qid2**: Unique IDs for each question.
- **question1** and **question2**: The full text of each question.
- **is_duplicate**: Target variable, set to 1 if the two questions have the same meaning, and 0 otherwise.

The dataset contains **404,290 rows** of question pairs.

## Project Pipeline

### 1. Data Preprocessing

I preprocess the data using the following steps:
- Removal of HTML tags, punctuation, numbers, and decontracting words.
- Tokenization, stopword removal, lemmatization, and stemming of the text.

### 2. Feature Engineering

After preprocessing, I add various features to the data:
- **Basic Features**: Word count, common words between questions, question length.
- **Advanced Token Features**: Token lengths and other metrics derived from tokenization.
- **Fuzzy Features**: Calculated using string similarity methods like fuzzy string matching.

I create a total of **27 input features** and 1 output feature (whether the question pairs are duplicates).

### 3. Model Training

The text of both questions is represented using the **Bag of Words** technique, considering the top 3,000 most frequent words. Additionally, I scale the new features using the **MinMax Scaler**.

The data is then fed into a **RandomForest Classifier**, which achieved an accuracy of **80.32%**.

## Installation

To run the project locally:

   ```bash
   git clone https://github.com/Himanshupdt09/Duplicate-Questions-Pair-Classification-Using-NLP.git
   cd duplicate-question-pairs-classification
   # now install using pip
   pip install spacy nltk scikit-learn pandas numpy matplotlib seaborn beautifulsoup4 fuzzywuzzy

## Results

The RandomForest Classifier achieved an accuracy of **80.32%** on the test set. Future improvements could include experimenting with different models or refining feature engineering techniques.

## Technologies Used

- **NLP Libraries**: `spaCy`, `nltk`
- **Machine Learning**: `scikit-learn` (RandomForest)
- **Text Processing**: `re`, `BeautifulSoup`, `fuzzywuzzy`
- **Data Handling**: `pandas`, `numpy`
- **Visualization**: `matplotlib`, `seaborn`

## License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.

   



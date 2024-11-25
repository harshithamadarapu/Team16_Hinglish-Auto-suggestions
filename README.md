# TextFlow: Hinglish Auto-suggestions

**Team Number**: 16

Welcome to *TextFlow*! In this project, we focus on generating Hinglish auto-suggestions using NLP techniques. Hinglish is a blend of Hindi and English that’s widely used in everyday conversations, and our goal is to build an efficient system that can process Hinglish text and provide accurate, context-aware auto-suggestions.

---

## Project Overview

The TextFlow project leverages NLP methods to preprocess Hinglish text, tokenize it, and eventually generate smart auto-suggestions. This project aims to make interacting with Hinglish content easier and more efficient by predicting words or phrases that users are likely to type next. The journey begins with preprocessing the raw text, exploring the data, and preparing it for model training.

---

## Dataset Links

We are using the following datasets for training and validation, both available on Hugging Face:

- [Training Dataset](https://huggingface.co/datasets/DanArnin/Hinglish/viewer/default/train)
- [Validation Dataset](https://huggingface.co/datasets/DanArnin/Hinglish/viewer/default/validation)

These datasets contain Hinglish text, which we use to train and evaluate our model.

---

## Preprocessing and Data Analysis

### 1. **Data Extraction**
   - The dataset has a column called `hi_ng`, which contains sentences in Hinglish. I filtered out sentences that had less than two words, making sure that only meaningful sentences were included.

### 2. **Data Cleaning**
   - To make the text cleaner and easier for the model to process, I:
     - Removed URLs, email addresses, and alphanumeric words.
     - Stripped out any unnecessary non-letter characters (like special symbols and digits).
     - Removed extra spaces to ensure that the text was neat and well-structured.

### 3. **Normalization**
   - All text was converted to lowercase so that the model would not be sensitive to uppercase or lowercase variations. This helps make the text more consistent.

---

## Exploratory Data Analysis (EDA)

Before diving into model training, I performed **Exploratory Data Analysis (EDA)** to understand the dataset better and uncover important patterns. EDA helps in shaping the preprocessing and training processes by giving insights into the data’s characteristics.

### Key Insights from EDA:

1. **Text Length Distribution**  
   I examined the length of sentences in terms of word count. This helped me understand how long the typical sentences are and made me aware of potential issues when processing very short or long text.

2. **Most Frequent Words**  
   By analyzing the most common words in the dataset, I was able to get an understanding of the language patterns in Hinglish. This is crucial when building an auto-suggestion model to make sure the model is aware of the most commonly used terms.

3. **Word Cloud Visualization**  
   To visualize the most frequent words, I created a word cloud. This provided a quick overview of the dataset's content, highlighting key terms that appear frequently in Hinglish.

4. **N-grams Analysis**  
   I also looked at bigrams and trigrams (pairs and triplets of words) in the dataset. This helped me identify common word combinations in Hinglish, which will be useful for generating more accurate auto-suggestions.

5. **Text Similarity Analysis**  
   To check how similar the training and validation datasets are, I performed a Jaccard similarity analysis. This helped me understand the overlap between the datasets, which is important for evaluating how well the model might generalize to new data.

---

## Tokenizing the Dataset

Once the data was preprocessed and I had a good understanding of its structure, I moved on to tokenization. Tokenization is the process of breaking sentences into individual words or tokens, which is essential for any NLP task.

### Tokenization Steps:

1. **Load the Dataset**  
   I loaded the data from CSV files that contain Hinglish text in the `phrases` column.

2. **Clean the Data**  
   Rows with non-string values were removed to make sure we only have valid text data for tokenization.

3. **Apply Tokenization**  
   Using the `word_tokenize` function from the NLTK library, I tokenized each sentence into individual words.

4. **Save the Tokenized Data**  
   After tokenizing the data, I saved the resulting tokens into new CSV files, which will later be used for training and validating the model.

---

## Next Steps: Model Training

With the data preprocessed and tokenized, I’m now ready to train the model. The next step is to build a model that can predict the next word or phrase based on a partial input, providing users with accurate Hinglish auto-suggestions.

---

## Requirements

To get the project running on your local machine, you’ll need to install the following libraries:

- `pandas`
- `nltk`
- `matplotlib`
- `seaborn`
- `wordcloud`
- `scikit-learn`

To install these dependencies, simply run the following command:

```bash
pip install pandas nltk matplotlib seaborn wordcloud scikit-learn

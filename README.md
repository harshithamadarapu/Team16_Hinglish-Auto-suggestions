# The TextFlow Project: Hinglish Auto-suggestions

**Team Number**: 16

Welcome to *TextFlow*! This project focuses on developing an auto-suggestion system for Hinglish text using NLP techniques. Hinglish, a blend of Hindi and English, is widely used in everyday conversations, and our goal is to build an efficient system that can process Hinglish text and provide accurate, context-aware auto-suggestions.

---

## Project Overview

The TextFlow project aims to preprocess Hinglish text, tokenize it, and eventually generate smart auto-suggestions. By analyzing the structure and common patterns in Hinglish, the system will predict the next words or phrases users are likely to type, improving their writing experience.

---

## Dataset Links

We are using the following datasets for training and validation, available on Hugging Face:

- [Training Dataset](https://huggingface.co/datasets/DanArnin/Hinglish/viewer/default/train)
- [Validation Dataset](https://huggingface.co/datasets/DanArnin/Hinglish/viewer/default/validation)

These datasets contain Hinglish text that we use to train and evaluate our model.

---

## Preprocessing and Data Analysis

### 1. **Data Extraction**
   - The dataset includes a column called `hi_ng` that contains Hinglish sentences. I filtered out sentences with fewer than two words to ensure meaningful data for training.

### 2. **Data Cleaning**
   - I cleaned the text by:
     - Removing URLs, email addresses, alphanumeric words, and special characters.
     - Stripping out unnecessary symbols and extra spaces to keep the text clear and readable.

### 3. **Normalization**
   - To maintain consistency, all text was converted to lowercase. This avoids case-sensitive discrepancies and ensures uniformity.

---

## Exploratory Data Analysis (EDA)

Before diving into model training, I conducted **Exploratory Data Analysis (EDA)** to gain insights into the data. EDA helps to identify key patterns and trends that can shape how we preprocess and train the model.

### Key Insights from EDA:

1. **Text Length Distribution**  
   - I analyzed the sentence length distribution to understand how long sentences typically are, which helped me adjust the preprocessing steps.

2. **Most Frequent Words**  
   - By identifying common words, I got an idea of the vocabulary used in Hinglish, ensuring the model is aware of the most frequently used terms.

3. **Word Cloud Visualization**  
   - A word cloud was generated to visualize the most common words in the dataset, giving a quick overview of the Hinglish language patterns.

4. **N-grams Analysis**  
   - I explored bigrams and trigrams (pairs and triplets of words) to identify common word combinations. This is useful for making auto-suggestions more context-aware.

5. **Text Similarity Analysis**  
   - To assess the similarity between the training and validation sets, I performed a Jaccard similarity analysis. This helps determine how much overlap exists and ensures that the model generalizes well.

---

## Tokenizing the Dataset

Once the data was cleaned and analyzed, I proceeded with tokenization. Tokenization is the process of splitting text into smaller units, typically words, to make it easier for the model to process.

### Tokenization Steps:

1. **Load the Dataset**  
   - I loaded the dataset from CSV files that contain the Hinglish sentences.

2. **Clean the Data**  
   - I removed rows with non-string values to ensure the dataset only contained valid text.

3. **Apply Tokenization**  
   - Using the `word_tokenize` function from NLTK, I tokenized the sentences into words (tokens).

4. **Save the Tokenized Data**  
   - After tokenizing the text, I saved the processed data into new CSV files for future use in training and validation.

---

## Next Steps: Model Training

With the data preprocessed and tokenized, the next step is to build and train a model that can predict the next word or phrase based on the input text. This will allow the system to generate accurate Hinglish auto-suggestions.

---

## Requirements

To get the project running on your local machine, install the following libraries:

- `pandas`
- `nltk`
- `matplotlib`
- `seaborn`
- `wordcloud`
- `scikit-learn`

To install these dependencies, run the following command:

```bash
pip install pandas nltk matplotlib seaborn wordcloud scikit-learn

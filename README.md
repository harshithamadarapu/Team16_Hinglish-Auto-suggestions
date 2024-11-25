# TextFlow: Hinglish Auto-suggestions

**Team Number**: 16

Welcome to the *TextFlow* project, an innovative NLP solution designed to generate Hinglish auto-suggestions. Hinglish, the combination of Hindi and English, is commonly used in everyday communication, and this project leverages NLP techniques to process and understand Hinglish text for more accurate auto-suggestions. 

---

## Project Overview

Our project focuses on building an NLP pipeline that can preprocess Hinglish text, tokenize it, and generate contextually relevant auto-suggestions. We use a variety of natural language processing techniques, such as text cleaning, tokenization, and exploration through data analysis to ensure optimal performance.

---

## Dataset Links

We are using the following datasets for training and validation, available on Hugging Face:

- [Training Dataset](https://huggingface.co/datasets/DanArnin/Hinglish/viewer/default/train)
- [Validation Dataset](https://huggingface.co/datasets/DanArnin/Hinglish/viewer/default/validation)

These datasets contain Hinglish text, making them ideal for training the model to understand and predict Hinglish auto-suggestions.

---

## Preprocessing and Data Analysis

### 1. **Data Extraction**
   - The dataset consists of a column named `hi_ng`, containing Hinglish sentences. 
   - We filtered the data to include only sentences that had more than one word, ensuring meaningful input for the model.

### 2. **Data Cleaning**
   - To ensure that the data is clean and usable, we performed the following:
     - Removed unwanted elements such as URLs, email addresses, and alphanumeric words.
     - Stripped out non-letter characters (special characters or digits).
     - Removed extra spaces to ensure uniformity in the text.

### 3. **Normalization**
   - All the text was converted to lowercase to eliminate variations due to case sensitivity, making it more consistent for processing.

---

## Exploratory Data Analysis (EDA)

Before building the model, we performed an **Exploratory Data Analysis (EDA)** to gain insights into the dataset. EDA helps in understanding the distribution of text, identifying key features, and visualizing important patterns, which guide the preprocessing and model training process.

### Key Insights from EDA:

1. **Text Length Distribution**  
   We analyzed the distribution of text lengths in terms of word count. This revealed valuable insights into how long the sentences in the dataset are, which could affect the performance of tokenization and model training.

2. **Most Frequent Words**  
   A visualization of the most frequent words in the dataset helped us identify common terms in Hinglish. Understanding word frequency is crucial for generating auto-suggestions based on the most commonly used terms.

3. **Word Cloud Visualization**  
   We created a word cloud to visually represent the frequency of words in the combined training and validation datasets. This gave us a high-level view of the most common words and their relative importance.

4. **N-grams Analysis**  
   We explored common bigrams and trigrams in the Hinglish text to capture recurring word pairs and triples. This helps in generating more relevant and context-aware suggestions for the user.

5. **Text Similarity Analysis**  
   We performed a Jaccard similarity analysis to measure the overlap between the training and validation datasets. This helped us understand how similar the two datasets are, which is important for evaluating the model’s generalization capabilities.

---

## Tokenizing the Dataset

After preprocessing and EDA, we moved on to tokenization, breaking down sentences into individual words (tokens). Tokenization is a crucial step for any NLP task, as it converts raw text into structured data.

### Tokenization Steps:

1. **Load the Dataset**  
   - The dataset was loaded from CSV files containing Hinglish text in the `phrases` column.

2. **Clean the Data**  
   - Rows with non-string values were identified and removed to ensure only valid text data was included.

3. **Apply Tokenization**  
   - We used the `word_tokenize` function from the NLTK library to tokenize each sentence into words.

4. **Save the Tokenized Data**  
   - The tokenized data was saved into new CSV files for further use in training and validation.

---

## Model Training

After preprocessing and tokenization, the next step will involve training a model using the preprocessed data. We aim to build a model that can predict the next word or phrase, given a partial input, providing users with accurate and contextually relevant Hinglish auto-suggestions.

---

## Requirements

To run this project, you’ll need to install the following libraries:

- `pandas`
- `nltk`
- `matplotlib`
- `seaborn`
- `wordcloud`
- `scikit-learn`

You can install the required dependencies using the following command:

```bash
pip install pandas nltk matplotlib seaborn wordcloud scikit-learn

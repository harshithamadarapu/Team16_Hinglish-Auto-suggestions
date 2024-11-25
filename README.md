# The TextFlow Project: Hinglish Auto-suggestions

**Team Number**: 16

TextFlow focuses on building an NLP-based auto-suggestion system for Hinglish—a blend of Hindi and English widely used in India. Our goal is to preprocess Hinglish text, analyze it, and train a model for generating context-aware suggestions.

---

## Dataset Links

We use the following datasets from Hugging Face:

- [Training Dataset](https://huggingface.co/datasets/DanArnin/Hinglish/viewer/default/train)  
- [Validation Dataset](https://huggingface.co/datasets/DanArnin/Hinglish/viewer/default/validation)

---

## Preprocessing Steps

1. **Data Extraction**  
   - Extracted sentences with more than one word from the `hi_ng` column for meaningful input.

2. **Data Cleaning**  
   - Removed URLs, emails, alphanumeric words, special characters, and extra spaces.

3. **Normalization**  
   - Converted text to lowercase for consistency.

4. **Tokenization**  
   - Split sentences into words using `word_tokenize` from NLTK.

---

## Exploratory Data Analysis (EDA)

- Analyzed sentence length distribution.  
- Identified common words using frequency plots and word clouds.  
- Explored bigrams and trigrams for contextual understanding.  
- Compared training and validation sets for similarity.

---

## Next Steps

We aim to train a model capable of generating accurate Hinglish auto-suggestions by leveraging this clean, preprocessed dataset.

---

## Requirements

Install the required libraries:

```bash
pip install pandas nltk matplotlib seaborn wordcloud scikit-learn

# TextFlow: Hinglish Auto-Suggestions

**Team Number**: 16

TextFlow focuses on building an NLP-based auto-suggestion system for Hinglish—a blend of Hindi and English widely used in India. Our goal is to preprocess Hinglish text, analyze it, and train a model for generating context-aware suggestions.

---

## Dataset Links

We are using the following datasets from Hugging Face:

- [Training Dataset](https://huggingface.co/datasets/DanArnin/Hinglish/viewer/default/train)
- [Validation Dataset](https://huggingface.co/datasets/DanArnin/Hinglish/viewer/default/validation)

---

## Preprocessing Steps

1. **Data Extraction**  
   - Extracted meaningful sentences by filtering out single-word entries from the `hi_ng` column.

2. **Data Cleaning**  
   - Removed URLs, emails, alphanumeric words, special characters, and unnecessary spaces.

3. **Normalization**  
   - Converted all text to lowercase for uniformity.

4. **Tokenization**  
   - Used NLTK's `word_tokenize` to split sentences into words for further analysis.

---

## Dataset Overview

- **Training Dataset**: Contains 188,525 sentences with 38,200 unique words.
- **Structure**: The dataset has a single column, "Phrases," containing Hinglish sentences.

---

## Exploratory Data Analysis (EDA)

- Analyzed sentence length distribution.
- Identified common words through frequency plots and word clouds.
- Explored bigrams and trigrams to understand word relationships.
- Compared the training and validation sets to assess their similarity.

---

## Bigram-Based Auto-Suggestions

We implemented a bigram-based approach to generate word suggestions by creating pairs of consecutive words (bigrams). This method predicts the next word based on the previous word, but it has limitations:

- **Short-Range Context**: Bigrams focus on local word pairs and do not capture longer dependencies or deeper contextual understanding.
- **Limited Context**: They cannot consider broader sentence context or semantic meaning, making them less effective for complex language tasks.

---

## Bigram Model Workflow

1. **Dataset Loading**:
   - The Hinglish phrases are loaded from an Excel file located at `/content/data.xlsx`.

2. **Preprocessing**:
   - A `preprocess_dataset()` function cleans the text, removes numbers, and generates bigrams by extracting consecutive word pairs.
   - The 5 most common following word pairs for each word are selected.

3. **Saving Processed Data**:
   - The top word pairs are saved to a JSON file (`top_word_pairs.json`) for efficient access.

4. **Gradio Interface**:
   - The `get_next_word_suggestions()` function generates word suggestions based on user input, using the preprocessed bigrams.
   - A live Gradio interface allows users to input text and receive up to 5 suggestions for the next word.

5. **Interface Launch**:
   - The Gradio interface is launched for real-time interaction, enabling users to test the auto-suggestions.

![Gradio Interface](images/gradio.jpeg)


[Watch the video on YouTube](https://youtu.be/9Ds56z9EykM)

---

## Next Steps

To enhance the suggestion system, we plan to explore more advanced techniques like neural language models, which can capture deeper relationships and context within Hinglish text.


---

## Next Steps

We aim to improve the suggestion system by exploring more advanced techniques, such as neural language models, which can capture more complex relationships and context within the Hinglish language.

---

### Training using Distill bert

we used distil bert model for training as it is light weight and is one the faster in all bert model. but since the dataset have 1.8L sentences and whereas the unique words are only 38200. because of the ratio between words and sentence is too less.the model is overfitting. we tried to use different parameters still the result is similar.

### Fine tuneing the model(INDIC Bert)

since the main dataset is quitebig so i used a dataset with 25000sentences extracted from main dataset.it has around 19k unique words.
again since the words are many compared to dataset.the loss is quite big.

### Training with LSTM + DISTIL BERT



## Requirements

Install the required libraries:

```bash
pip install pandas nltk gradio matplotlib seaborn wordcloud scikit-learn


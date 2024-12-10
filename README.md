# TextFlow: Hinglish Auto-Suggestions

**Team Number**: 16

The goal of this project is to develop a next-word suggestion system specifically for Hinglish, a blend of Hindi and English commonly used in everyday conversations. The challenge lies in creating a model that can accurately predict the next word while handling the unique nature of Hinglish, including code-switching and informal communication.

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

- **Training Dataset**: Contains 1.4L+ sentences with 38,200 unique words.
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

![Using Bigram for Next Word Prediction](https://github.com/harshithamadarapu/Team16_Hinglish-Auto-suggestions/blob/main/images/Using%20bigram%20for%20next%20word%20prediction_gradio.jpeg)




[Watch the video on YouTube](https://youtu.be/9Ds56z9EykM)

---
## **DistilBERT Model:**  
To improve predictions, I fine-tuned **DistilBERT**, an efficient version of **BERT**, on the Hinglish dataset.  
- **Benefits**: Enabled context-aware suggestions through advanced transformer-based modeling.

### **Data Preparation:**  
- **Tokenizer & Masking**: Used **DistilBertTokenizer** to preprocess sentences, applying a 15% masking probability to create training and validation datasets with a custom `HinglishDataset` class.  
- **Data Loaders**: Batched datasets using **DataLoader** for efficient training.

### **Model Training:**  
- Fine-tuned the **DistilBERT multilingual-cased** model using **masked language modeling (MLM)** on the Hinglish dataset.  
- Configured **AdamW** optimizer (learning rate: 5e-5) with a linear scheduler and trained for three epochs, reducing loss from **1.77** (epoch 0) to **0.232** (epoch 2).  
- Utilized GPU when available for faster training.
  
![](https://github.com/harshithamadarapu/Team16_Hinglish-Auto-suggestions/blob/main/images/IMG-20241210-WA0007.jpg)


### **Evaluation and Prediction:**  
- Created a prediction pipeline using the pipeline API for next-word suggestions.  
- Users can input Hinglish text, and the model predicts the top five next words with confidence scores.  
- **Visualization**: Plotted a graph showing the decline in training loss across epochs, indicating model convergence.
  
![Training Loss Across Epochs](https://github.com/harshithamadarapu/Team16_Hinglish-Auto-suggestions/blob/main/images/IMG-20241210-WA0010.jpg)
### **Results:**
![](https://github.com/harshithamadarapu/Team16_Hinglish-Auto-suggestions/blob/main/images/IMG-20241210-WA0011.jpg)
![](https://github.com/harshithamadarapu/Team16_Hinglish-Auto-suggestions/blob/main/images/IMG-20241210-WA0008.jpg)
![](https://github.com/harshithamadarapu/Team16_Hinglish-Auto-suggestions/blob/main/images/IMG-20241210-WA0009.jpg)


### **Demo:**  
- The **Bigram** model was integrated with **Gradio**, allowing real-time Hinglish next-word predictions.  
- In contrast, **DistilBERT** could take inputs directly from the user through the command line, as shown above.

### **Acknowledgements:**  
Thanks to online resources, YouTube (Google tutorials), **ChatGPT**, and research papers for their valuable support in this project.  

### **Special Thanks**  
I would like to express my gratitude to **Nidhi Mam** for her invaluable guidance and support throughout this project.










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

![image](https://github.com/user-attachments/assets/f7f5e92f-ddf8-483d-8686-df139c93bca6)


![results](https://github.com/user-attachments/assets/0a0aad9e-f905-4d91-8d50-c6e084b206f4)

I have incoperated LSTM+DISTILBERT model as LSTM is very good at semantic knowledge and BERT is encode-only model

I wanted to get the best of the both models

## Requirements

Install the required libraries:

```bash
pip install pandas nltk gradio matplotlib seaborn wordcloud scikit-learn


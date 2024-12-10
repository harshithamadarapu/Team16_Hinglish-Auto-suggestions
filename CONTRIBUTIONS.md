## REPORT ON WHAT EACH TEAM MATE DID

### SE22UARI080:

- [Hinglish Auto-suggestion Dataset on Kaggle](https://www.kaggle.com/datasets/bhuvanavijaya/nlp-autosuggestion)

- [Fine-tuning with Indic BERT](https://github.com/harshithamadarapu/Team16_Hinglish-Auto-suggestions/blob/main/FineTuneing(indic%20bert%20).ipynb)

- [Distill BERT Training](https://github.com/harshithamadarapu/Team16_Hinglish-Auto-suggestions/blob/main/distill%20bert(train)%20.ipynb)

1. **Preprocessing the Data**: Using regex, removed all the non-alphabets.

2. **Tokenization**: Tokenized the data using `split()` because, since it is auto-suggestion, I thought every word is important. But when it comes to training with BERT models, I used the model’s tokenizer, and for LSTM, I used normal tokenization.

3. **Training and Fine-Tuning the Model**: Even though there were failures, I experimented with several models like multilingual BERT too. However, the model was too heavy to execute fully. I worked with **Indic BERT** for fine-tuning.

4. **Word Embeddings and Context Embeddings**: Context embeddings were created with **LSTM**.






## SE22UARI087:

- **Data Analysis**: Analyzed the Hinglish dataset to understand the structure and distribution of words. I focused on identifying patterns in the dataset that could help improve the auto-suggestions.

- **Bigram Model**: Implemented a bigram-based approach to predict the next word. This method utilizes pairs of consecutive words to suggest the next word based on the current word.

- **DistilBERT Model**: Fine-tuned DistilBERT, a lighter version of BERT, on the Hinglish dataset. This helped generate context-aware suggestions by leveraging the model's understanding of language.

- **TinyBERT Experimentation**: Experimented with TinyBERT, a smaller version of BERT, to optimize for faster processing and reduced model size. However, due to GPU limitations in Colab, I was unable to fully run and fine-tune TinyBERT.

---

### Code for Bigrams and Fine-Tuning with DistilBERT:

1. **Bigram Prediction**:
   - Developed a bigram-based model that suggests the next word by utilizing pairs of consecutive words. This approach was implemented to generate predictions based on the cleaned dataset.

2. **Fine-Tuning DistilBERT**:
   - Fine-tuned DistilBERT on the Hinglish dataset using a masked language model approach. This allowed the model to learn contextual relationships between words and generate better suggestions.

3. **TinyBERT Experimentation**:
   - Explored TinyBERT for faster predictions and a smaller model size. Unfortunately, due to GPU constraints in Colab, the full training and fine-tuning process was not completed.

---

### Visuals:
- ![Using Bigram for Next Word Prediction](https://raw.githubusercontent.com/harshithamadarapu/Team16_Hinglish-Auto-suggestions/a7b8da4a2ce4088c0ac00eeeac5a0c97da1cc30d/Using%20bigram%20for%20next%20word%20prediction_gradio.jpeg)

---

### Additional Work:
- Developed a Gradio interface to demonstrate the real-time next-word prediction using both the bigram model and the fine-tuned DistilBERT model. This interface allows users to input Hinglish text and receive suggested next words in real-time.

### Links to Notebooks:
- [Next Word Prediction Using DistilBERT](https://github.com/harshithamadarapu/Team16_Hinglish-Auto-suggestions/blob/main/nextwordusingdistilbert.ipynb)
- [Bigram Model with Gradio Interface](https://github.com/harshithamadarapu/Team16_Hinglish-Auto-suggestions/blob/main/bigram_gradio.ipynb)


## REPORT ON WHAT EACH TEAM MATE DID

### SE22UARI080:

- [Hinglish Auto-suggestion Dataset on Kaggle](https://www.kaggle.com/datasets/bhuvanavijaya/nlp-autosuggestion/code)

- [Fine-tuning with Indic BERT](https://github.com/harshithamadarapu/Team16_Hinglish-Auto-suggestions/blob/main/FineTuneing(indic%20bert%20).ipynb)

- [Distill BERT Training](https://github.com/harshithamadarapu/Team16_Hinglish-Auto-suggestions/blob/main/distill%20bert(train)%20.ipynb)

- ![image](https://github.com/user-attachments/assets/9c786577-3f5d-42de-9759-83ad54021c8c)
this is result of LSTM + DISTIL BERT

1. **Preprocessing the Data**: Using regex, removed all the non-alphabets.

2. **Tokenization**: Tokenized the data using `split()` because, since it is auto-suggestion, I thought every word is important. But when it comes to training with BERT models, I used the model’s tokenizer, and for LSTM, I used normal tokenization.

3. **Training and Fine-Tuning the Model**: Even though there were failures, I experimented with several models like multilingual BERT too. However, the model was too heavy to execute fully. I worked with **Indic BERT** for fine-tuning.

4. **Word Embeddings and Context Embeddings**: Context embeddings were created with **LSTM**.




---


## SE22UARI087:

---
- **Wrote README**

- **Data Analysis**: I analyzed the Hinglish dataset to understand the structure and distribution of words. I focused on identifying patterns in the dataset that could help improve the auto-suggestions.
  - [NLP Data Analysis Notebook](https://github.com/harshithamadarapu/Team16_Hinglish-Auto-suggestions/blob/main/NLP_DataAnalysis.ipynb)

- **Bigram Model**: I implemented a bigram-based approach to predict the next word. This method uses pairs of consecutive words to suggest the next word based on the current word.
  - ![Using Bigram for Next Word Prediction](https://raw.githubusercontent.com/harshithamadarapu/Team16_Hinglish-Auto-suggestions/a7b8da4a2ce4088c0ac00eeeac5a0c97da1cc30d/Using%20bigram%20for%20next%20word%20prediction_gradio.jpeg)
  - [Bigram Model with Gradio Interface](https://github.com/harshithamadarapu/Team16_Hinglish-Auto-suggestions/blob/main/bigram_gradio.ipynb)
  
  **Note**: While bigram models are useful for predicting the next word based on a pair of consecutive words, they have limitations. They struggle to capture long-distance relationships between words and lack the ability to account for broader sentence context, making them less effective for tasks that require deeper understanding.

- **DistilBERT Model**: I fine-tuned DistilBERT, a lighter version of BERT, on the Hinglish dataset. This allowed for generating more context-aware suggestions by leveraging the model’s deeper understanding of language.
    - [Fine-Tuning DistilBERT Notebook](https://github.com/harshithamadarapu/Team16_Hinglish-Auto-suggestions/blob/main/nextwordusingdistilbert.ipynb)
![image](https://github.com/harshithamadarapu/Team16_Hinglish-Auto-suggestions/blob/main/images/IMG-20241210-WA0007.jpg)
---
![image](https://github.com/harshithamadarapu/Team16_Hinglish-Auto-suggestions/blob/main/images/IMG-20241210-WA0010.jpg)
---
![image](https://github.com/harshithamadarapu/Team16_Hinglish-Auto-suggestions/blob/main/images/IMG-20241210-WA0011.jpg)
---
![image](https://github.com/harshithamadarapu/Team16_Hinglish-Auto-suggestions/blob/main/images/IMG-20241210-WA0008.jpg)
---
![image](https://github.com/harshithamadarapu/Team16_Hinglish-Auto-suggestions/blob/main/images/IMG-20241210-WA0009.jpg)
  

- **TinyBERT Experimentation**: I also experimented with TinyBERT, a smaller version of BERT, to optimize for faster processing and reduced model size. However, due to GPU limitations in Colab, I wasn’t able to fully run and fine-tune TinyBERT.


---

## SE22UARI081:

---

- **Data Analysis**: I analyzed the Hinglish dataset to understand the structure and distribution of words. I focused on identifying patterns in the dataset that could help improve the auto-suggestions.
  - [EDA Notebook](https://github.com/harshithamadarapu/Team16_Hinglish-Auto-suggestions/blob/main/experiments/EDA.ipynb)

- **DistilBERT Model**: I fine-tuned DistilBERT, a lightweight version of BERT, on the Hinglish dataset. This allowed for generating more context-aware suggestions while maintaining faster processing times.
  - [Fine-Tuning DistilBERT Notebook](https://github.com/harshithamadarapu/Team16_Hinglish-Auto-suggestions/blob/main/experiments/DistilBERTTraining_Finetuning%26Evaluate.ipynb)
  - ![image](https://github.com/harshithamadarapu/Team16_Hinglish-Auto-suggestions/blob/main/images/Screenshot%202024-12-10%20211057.png)
  - ![image](https://github.com/harshithamadarapu/Team16_Hinglish-Auto-suggestions/blob/main/images/Screenshot%202024-12-10%20211111.png)
  - ![image](https://github.com/harshithamadarapu/Team16_Hinglish-Auto-suggestions/blob/main/images/Screenshot%202024-12-10%20213545.png)
  - ![image](https://github.com/harshithamadarapu/Team16_Hinglish-Auto-suggestions/blob/main/images/Screenshot%202024-12-10%20220031.png)

- **Multilingual BERT (mBERT) Model**: I fine-tuned mBERT to handle Hinglish text, benefiting from its multilingual capabilities to generate accurate suggestions for code-switched languages.
  - [Fine-Tuning mBERT with Word2Vec Notebook](https://github.com/harshithamadarapu/Team16_Hinglish-Auto-suggestions/blob/main/FineTuningMultiLingualBERTwithWORD2VEC.ipynb)
  - ![image](https://github.com/harshithamadarapu/Team16_Hinglish-Auto-suggestions/blob/main/images/Screenshot%202024-12-10%20211158.png)
  - ![image](https://github.com/harshithamadarapu/Team16_Hinglish-Auto-suggestions/blob/main/images/Screenshot%202024-12-10%20211218.png)

-----

SE22UARI153

------
---


SE22UARI153

---

-My Contribution:
In the Hinglish Next Word Generator group project, my primary contribution was implementing and training the LSTM-based model for next-word prediction. I developed and tested the preprocessing pipeline,and fine-tuned hyperparameters to optimize its performance. I also prepared the final model and tokenizer files (hinglish_auto_suggestion_model.h5 and tokenizer.json) for deployment. I also searched for the dataset and preprocessed it in the 1st 15 days submission.Additionally, I contributed to the project slides and actively collaborated with my teammates, providing support and ideas throughout the project. Although the finalized code was derived from a teammate's implementation, I was closely involved in its development and testing, ensuring a seamless integration of efforts.

*LSTM model*:https://github.com/harshithamadarapu/Team16_Hinglish-Auto-suggestions/blob/main/experiments/LSTMtraining.ipynb

*LSTM model*:https://github.com/harshithamadarapu/Team16_Hinglish-Auto-suggestions/blob/main/experiments/hinglish_auto_suggestions/LSTM.ipynb
Image: ![image](https://github.com/user-attachments/assets/e254bd15-97fb-407a-b9b0-2a6381890639)


https://github.com/harshithamadarapu/Team16_Hinglish-Auto-suggestions/blob/main/experiments/hinglish_auto_suggestions/hinglish_auto_suggestion_model%20(1).h5

https://github.com/harshithamadarapu/Team16_Hinglish-Auto-suggestions/blob/main/experiments/hinglish_auto_suggestions/tokenizer.json

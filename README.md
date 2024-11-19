## Team Number: 16 
# TextFlow: Hinglish Auto-suggestions


This repository contains the work we've done for our NLP project on Hinglish Auto-suggestions. The project focuses on using NLP techniques to preprocess Hinglish text and generate accurate Auto-suggestions.  



---

## Dataset Links  
 We’re using the following datasets for training and validation, available on Hugging Face:

- [Training Dataset](https://huggingface.co/datasets/DanArnin/Hinglish/viewer/default/train)  
- [Validation Dataset](https://huggingface.co/datasets/DanArnin/Hinglish/viewer/default/validation)

## Preprocessing and Data Analysis  

To ensure high-quality input for our model, we performed the following steps:

1. **Data Extraction**:  
   - We extracted the 'hi_ng' sentences from the column in the dataset.The data was filtered to include only those sentences that contained more than one word, ensuring meaningful input for the model.

 
2. **Data Cleaning**:  
   - We removed unnecessary elements such as URLs, email addresses, alphanumeric words, and non-letter characters from the sentences.

   - Extra spaces were also removed, ensuring clean and readable text.
     
3. **Normalization**: 
   - All text was converted to lowercase to avoid case-sensitive variations.
  
## Tokenizing the Dataset

After the preprocessing steps, we tokenized the dataset using the word_tokenize function from NLTK. The tokenization process breaks down each sentence into individual words (tokens). Below are the steps we followed for tokenization:

**Steps:**
1. **Load the Dataset:** The dataset is loaded from CSV files, containing the phrases column with Hinglish text.
   
2. **Clean the Data:** Rows containing non-string values were identified and removed.
   
3. **Apply Tokenization:** The word_tokenize function was applied to the clean text.
   
4. **Save the Tokenized Data:** The tokenized phrases were saved into new CSV files for further use in training and validation.

   

   
     


  

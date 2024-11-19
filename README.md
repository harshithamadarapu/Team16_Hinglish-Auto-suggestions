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
     


  

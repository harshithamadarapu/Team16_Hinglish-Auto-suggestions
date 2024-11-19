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

1. **Data Cleaning**:  
   - We removed any unnecessary elements such as URLs, special characters, and extra spaces from the dataset.
   - The cleaned data was saved as `cleaned_data.csv `.

2. **Normalization**:  
   - All text was converted to lowercase to maintain uniformity and avoid case-sensitive variations.
   - Saved the normalized data as `normalized_data.csv`.  

3. **Tokenization**:  
   - Split the text into individual tokens (words).  
   - Saved the tokenized data as `tokenized_data.csv`.  

4. **Word Frequency Analysis**:  
   - We analyzed the dataset to identify the most frequently occurring words.
   - Here are the top 10 words along with their counts:

     - `ke`: 81,318  
     - `liye`: 55,985  
     - `hai`: 55,913  
     - `ko`: 55,262  
     - `kya`: 38,535  
     - `me`: 32,989  
     - `kare`: 28,297  
     - `mujhe`: 23,965  
     - `alarm`: 23,196  
     - `mere`: 20,463  

5. **Unique Word Count**:  
   - Total number of unique words in the dataset: **38,356**.  

6. **Visualizations**:  
   - Generated a **Word Cloud** to visualize the most frequent words in the dataset.  
   - Created a bar chart showing the frequencies of the top 20 most common words.

---

# Sentiment Analysis of Public Opinion on Donald Trump's Import Tariff Policy Towards Indonesia on X (Twitter) using SVM and Bi-LSTM

![Python](https://img.shields.io/badge/Python-3.10%2B-blue)
![License](https://img.shields.io/badge/License-MIT-green)
![Status](https://img.shields.io/badge/Status-Completed-brightgreen)

## Project Description
This project aims to analyze public sentiment in Indonesia on **X (formerly Twitter)** regarding the 32% import tariff policy imposed by the United States President Donald Trump on Indonesian products.  
Two main approaches are compared:
- **Support Vector Machine (SVM)** with **TF-IDF** feature extraction.
- **Bidirectional Long Short-Term Memory (Bi-LSTM)** with **FastText** word embeddings.

## Objectives
1. Classify Indonesian public opinion related to the import tariff policy using data from X.
2. Compare the performance of **SVM** and **Bi-LSTM** in classifying positive, negative, and neutral sentiments.

## Dataset
- **Source**: X (Twitter)
- **Period**: May 1, 2024 – May 30, 2025
- **Initial size**: 10,450 tweets  
- **Cleaned size**: 10,154 tweets  
- **Keywords**: “tarif impor”, “kebijakan impor”, “tarif 32%”, “donald trump”, “ekspor”, “phk”, “negosiasi”, “inflasi”, “daya saing”, etc.  
- **Dataset link**: [Google Spreadsheet](https://docs.google.com/spreadsheets/d/16q5nzeH8AZ688QNeGXw3QRmzK8OC8tshM91c31_oAi4/edit?usp=sharing)

## Methodology
### 1. Preprocessing
- **Cleansing**: Remove URLs, mentions, hashtags, numbers, punctuation, non-ASCII characters, and extra spaces.
- **Case Folding**: Convert all text to lowercase.
- **Tokenization & Stopword Removal**.
- **Normalization**: Convert slang to formal words.
- **Stemming**: Reduce words to their base form.

### 2. Data Annotation
Lexicon-based approach with sentiment scores ranging from **-5** to **+5** for each word.

### 3. Feature Extraction
- **TF-IDF** for SVM.
- **FastText** (300 dimensions, cc.id.300.vec) for Bi-LSTM.

### 4. Sentiment Classification
- **SVM**: Hyperparameter tuning (C) using GridSearchCV, feature selection using chi-square.
- **Bi-LSTM**: FastText embeddings, 128-unit bidirectional LSTM, dropout, and softmax output for 3-class classification.

### 5. Evaluation Metrics
- Accuracy
- Precision
- Recall
- F1-Score

## Results
**Sentiment distribution:**
- Positive: 4,774 tweets (49.9%)
- Negative: 3,549 tweets (35.5%)
- Neutral: 1,831 tweets (14.6%)

**Model performance:**

| Model  | Accuracy | Precision | Recall | F1-Score |
|--------|----------|-----------|--------|----------|
| SVM    | 81%      | ~85%      | 37%-88%| 45%-88%  |
| BiLSTM | **91%**  | >90%      | **96%**| **90%**  |

**Key Findings:**
- Bi-LSTM significantly outperforms SVM, especially in detecting **neutral** sentiment (Recall: 96% vs 37%).
- The bidirectional architecture and FastText embeddings allow Bi-LSTM to capture contextual meaning better than SVM.

## Contributors

Thanks to the following people for their contributions to this project:

<table>
  <tr>
    <td align="center">
      <a href="https://github.com/sitifatiharh">
        <img src="https://avatars.githubusercontent.com/username1" width="100px;" alt=""/>
        <br />
        <sub><b>Siti Fatiha Rahmah</b></sub>
      </a>
    </td>
    <td align="center">
      <a href="https://github.com/username3">
        <img src="https://avatars.githubusercontent.com/nabilaekasd" width="100px;" alt=""/>
        <br />
        <sub><b>Nabila Eka Syntia Dewi</b></sub>
      </a>
    </td>
  </tr>
</table>

## Presentations

[Analysis of Public Opinion Sentiment toward Donald Trump's Import Tariff Policy on Indonesia on Social Media X Using SVM and BiLSTM](https://drive.google.com/file/d/1TFnM4M-gZRqaYCD4162Zo_AFgFUt_LNd/view?usp=drive_link)

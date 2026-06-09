# Vietnamese News Classification

## Introduction

Vietnamese News Classification is a Natural Language Processing (NLP) project that focuses on automatically categorizing Vietnamese news articles into predefined categories using machine learning and transformer-based approaches.

The project aims to investigate the effectiveness of different text classification techniques on Vietnamese news data and compare the performance of traditional machine learning models with modern deep learning and transformer architectures.

This project was developed as part of an academic research assignment at Ton Duc Thang University.

---

## Objectives

The main objectives of this project are:

* Explore Vietnamese text classification techniques.
* Perform data preprocessing and feature engineering.
* Train and evaluate multiple classification models.
* Compare traditional machine learning methods with transformer-based models.
* Analyze classification performance using standard evaluation metrics.

---

## Dataset

The experiments were conducted on a Vietnamese news dataset containing articles collected from various online news sources.

Each sample consists of:

* News title
* News content
* Category label

### Dataset Availability

The dataset is not included in this repository due to GitHub file size limitations.

Users can replace the dataset with their own Vietnamese news corpus and adapt the preprocessing pipeline accordingly.

---

## Methodology

### Data Preprocessing

The following preprocessing techniques were applied:

* Text normalization
* Lowercase conversion
* Removal of special characters
* Stopword filtering
* Vietnamese tokenization
* Text cleaning

### Feature Representation

Different text representation methods were explored:

* TF-IDF
* Word Embeddings
* Transformer Embeddings

### Classification Models

#### Traditional Machine Learning

* Naive Bayes
* Logistic Regression
* Support Vector Machine (SVM)

#### Deep Learning

* TextCNN
* BiGRU

#### Transformer-Based Models

* PhoBERT
* XLM-RoBERTa
* Multilingual BERT (mBERT)

---

## Evaluation Metrics

Model performance was evaluated using:

* Accuracy
* Precision
* Recall
* F1-Score

The comparison of these metrics helps determine the most effective approach for Vietnamese news classification.

---

## Repository Structure

```text
.
├── Source_code.ipynb
├── baocao.pdf
├── 522H0093_522H0104_Poster.pptx
├── README.md
├── LICENSE
└── .gitignore
```

### Files Description

| File                          | Description                                                           |
| ----------------------------- | --------------------------------------------------------------------- |
| Source_code.ipynb             | Main notebook containing preprocessing, training, and evaluation code |
| baocao.pdf                    | Project report                                                        |
| 522H0093_522H0104_Poster.pptx | Project poster presentation                                           |
| README.md                     | Project documentation                                                 |
| LICENSE                       | Project license                                                       |

---

## Installation

Clone the repository:

```bash
git clone https://github.com/huynhdang0987/vietnamese-news-classification.git
```

Move to the project directory:

```bash
cd vietnamese-news-classification
```

Install the required dependencies:

```bash
pip install -r requirements.txt
```

---

## Usage

Open the notebook:

```text
Source_code.ipynb
```

using:

* Jupyter Notebook
* JupyterLab
* Visual Studio Code
* Google Colab

Run all cells sequentially to reproduce the experiments.

---

## Experimental Results

The project compares multiple approaches for Vietnamese news classification.

Transformer-based models generally achieve better performance than traditional machine learning models due to their ability to capture contextual information in Vietnamese text.

Detailed experimental results, analysis, and discussions can be found in:

* baocao.pdf
* 522H0093_522H0104_Poster.pptx

---
## Research Findings

### RQ1 — Architecture Impact

**Research Question:**
To what extent does model architecture — spanning traditional machine learning, deep learning, and transformer-based approaches — affect classification performance across different news categories?

**Findings:**
The experimental results reveal that model architecture has a substantial impact on Vietnamese news classification performance. Contrary to common expectations, traditional machine learning and deep learning models consistently outperformed transformer-based approaches on the BN-VN3S dataset.

#### Overall Classification Performance

| Family         | Model               | Accuracy (%) | Precision (%) | Recall (%) | Macro-F1 (%) | AUC (%)   |
| -------------- | ------------------- | ------------ | ------------- | ---------- | ------------ | --------- |
| Traditional ML | Naïve Bayes         | 87.06        | 86.03         | 87.09      | 86.36        | 98.83     |
| Traditional ML | Logistic Regression | 91.92        | 90.83         | 92.04      | 91.36        | 99.55     |
| Traditional ML | LinearSVC           | 92.92        | 92.38         | 92.31      | 92.33        | 99.55     |
| Traditional ML | SGDClassifier       | 87.73        | 86.55         | 87.68      | 87.03        | 98.95     |
| Deep Learning  | TextCNN             | 91.91        | 91.32         | 91.23      | 91.27        | 99.41     |
| Deep Learning  | **BiGRU**           | **93.01**    | **92.43**     | **92.47**  | **92.42**    | **99.61** |
| Deep Learning  | TextRCNN            | 92.74        | 92.12         | 92.20      | 92.16        | 99.59     |
| Transformer    | mBERT               | 79.84        | 78.10         | 80.30      | 78.73        | 97.04     |
| Transformer    | XLM-R               | 82.65        | 80.80         | 82.78      | 81.60        | 97.94     |
| Transformer    | PhoBERT             | 87.67        | 86.10         | 87.98      | 87.98        | 99.01     |

#### Key Observations

* **BiGRU achieved the best overall performance**, reaching an Accuracy of **93.01%** and a Macro-F1 score of **92.42%**.
* **LinearSVC** was the strongest traditional machine learning model, achieving a Macro-F1 score of **92.33%**, only **0.09 points** behind BiGRU.
* **TextRCNN** and **TextCNN** also demonstrated highly competitive performance, with Macro-F1 scores above **91%**.
* Within the transformer family, **PhoBERT** achieved the best results, obtaining a Macro-F1 score of **87.98%**.
* **mBERT** produced the weakest performance among all evaluated models, with a Macro-F1 score of only **78.73%**.
* Traditional machine learning and deep learning models consistently outperformed transformer-based approaches across all evaluation metrics.

**Conclusion:**
The results demonstrate that architecture choice significantly affects Vietnamese news classification performance. On the BN-VN3S benchmark, deep learning models—particularly BiGRU—achieved the strongest overall performance, while transformer-based models were unable to match the effectiveness of the best traditional and deep learning approaches.

---

### RQ2 — Temporal Impact

**Research Question:**
Does the publication period of news articles introduce temporal distribution shifts that degrade model performance when training and testing data span different time intervals?

**Findings:**
[Summarize how model performance changes across different publication periods.]

**Key Results:**

* Most robust model: [Model Name]
* Largest performance drop: [Model Name]
* Average performance change: [Value]

**Conclusion:**
[State whether temporal distribution shift significantly affects classification performance and which models are most resilient.]

---

### RQ3 — Source Impact

**Research Question:**
Does the originating news publisher introduce source-specific stylistic or topical biases that systematically affect classification accuracy across publishers?

**Findings:**
[Summarize the impact of training and testing on different news sources.]

**Key Results:**

* Most robust model across publishers: [Model Name]
* Largest source-specific degradation: [Model Name]
* Performance difference across publishers: [Value]

**Conclusion:**
[State whether source-specific bias exists and how it influences model performance.]

---

### RQ4 — Data Scale Impact

**Research Question:**
How sensitive are different model families to the volume of available training data, and what minimum data requirements are needed for reliable classification performance?

**Findings:**
[Summarize how model performance changes as training data increases.]

**Key Results:**

* Best low-resource model: [Model Name]
* Best high-resource model: [Model Name]
* Data scale threshold: [Value]

**Conclusion:**
[State how different model families respond to increasing training data and identify practical data requirements.]

---

## Summary of Findings

| Research Question | Main Finding |
| ----------------- | ------------ |
| RQ1               | [Summary]    |
| RQ2               | [Summary]    |
| RQ3               | [Summary]    |
| RQ4               | [Summary]    |

Overall, the study demonstrates that [Overall conclusion of the project].


## Future Work

Potential future improvements include:

* Multi-label news classification
* News recommendation systems
* Explainable AI for text classification
* Fine-tuning large language models (LLMs)
* Real-time news categorization
* Retrieval-Augmented Generation (RAG) integration

---

## Supervisor

**Mr. Tran Thanh Phuoc**

Faculty of Information Technology

Ton Duc Thang University

---

## Team Members

| Student ID | Full Name     |
| ---------- | ------------- |
| 522H0104   | Khoa Huynh    |
| 522H0093   | Chau Bao Nhan |

---

## Acknowledgements

We would like to express our sincere gratitude to our supervisor, **Mr. Tran Thanh Phuoc**, for his guidance, valuable feedback, and continuous support throughout the development of this project.

We also thank the Faculty of Information Technology, Ton Duc Thang University, for providing the academic environment and resources necessary for completing this work.

---

## License

This project is licensed under the MIT License.

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

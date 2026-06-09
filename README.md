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
## Project Poster

![Poster](poster.png)

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
To investigate temporal distribution shift, all models were trained on news articles published between **2019 and 2022** and evaluated on articles from **2023**, **2024**, and **2025**. The results reveal a consistent decline in classification performance over time, indicating that temporal distribution shift negatively affects model generalization to newer data.

#### Key Observations

* All evaluated models experienced performance degradation when tested on articles published after the training period.
* Traditional machine learning models (Naïve Bayes, Logistic Regression, LinearSVC, and SGDClassifier) showed noticeable decreases in Macro-F1 scores across evaluation years.
* Deep learning models (TextCNN, BiGRU, and TextRCNN) also suffered from temporal drift, although their performance remained relatively competitive.
* Transformer-based models demonstrated greater robustness to temporal changes, exhibiting smaller performance drops compared to traditional and deep learning approaches.
* **PhoBERT achieved the most stable performance across all evaluation years**, indicating a stronger ability to capture evolving linguistic patterns in Vietnamese news content.

#### Implications

The results suggest that language usage, topics, and writing styles in online news continuously evolve over time. As a consequence, models trained on historical data may gradually lose effectiveness when applied to more recent articles.

These findings highlight the importance of:

* Periodic model retraining.
* Continuous dataset updates.
* Monitoring temporal drift in production environments.

**Conclusion:**
Temporal distribution shift is a significant challenge for Vietnamese news classification systems. Although all models experienced performance degradation over time, transformer-based approaches—particularly PhoBERT—demonstrated superior robustness and maintained more stable performance when evaluated on newer news articles.

---

### RQ3 — Source Impact

**Research Question:**
Does the originating news publisher introduce source-specific stylistic or topical biases that systematically affect classification accuracy across publishers?

**Findings:**
To investigate source-level bias, we conducted leave-one-source-out experiments, where each model was trained on articles from two news publishers and evaluated on the held-out third publisher. The results reveal that source-specific characteristics have a substantial impact on classification performance, indicating the presence of source bias in Vietnamese news datasets.

#### Leave-One-Source-Out Performance (Macro-F1)

| Family         | Model               | VnExpress | VietNamNet | Dân Trí | All Sources |
| -------------- | ------------------- | --------- | ---------- | ------- | ----------- |
| Traditional ML | Naïve Bayes         | 83.83     | 81.35      | 86.31   | 86.36       |
| Traditional ML | Logistic Regression | 84.92     | 84.56      | 87.84   | 91.36       |
| Traditional ML | LinearSVC           | 84.26     | 84.85      | 86.69   | 92.33       |
| Traditional ML | SGDClassifier       | 83.50     | 82.53      | 86.54   | 87.03       |
| Deep Learning  | TextCNN             | 82.22     | 83.32      | 85.61   | 91.27       |
| Deep Learning  | BiGRU               | 82.71     | 83.61      | 86.59   | 92.42       |
| Deep Learning  | TextRCNN            | 83.12     | 83.32      | 87.13   | 92.16       |
| Transformer    | mBERT               | 77.51     | 74.36      | 78.67   | 78.73       |
| Transformer    | XLM-R               | 79.44     | 77.99      | 81.27   | 81.60       |
| Transformer    | PhoBERT             | 83.81     | 82.57      | 85.56   | 87.98       |

#### Key Observations

* The largest performance degradation occurred when models were evaluated on **VnExpress**, suggesting stronger source-specific characteristics compared to the other publishers.
* **BiGRU** showed the highest sensitivity to source bias, experiencing a performance drop of **9.71 Macro-F1 points** when evaluated on VnExpress.
* **TextCNN** and **TextRCNN** also suffered substantial degradation, with performance losses exceeding **8 points** in several configurations.
* Among traditional machine learning approaches, **LinearSVC** experienced considerable drops of **8.07 points** on VnExpress and **7.48 points** on VietNamNet.
* **Naïve Bayes** demonstrated the strongest robustness among traditional models, showing relatively small declines across all publishers.
* Within the transformer family, **mBERT** exhibited the smallest performance drops across source shifts, indicating greater resilience to publisher-specific variations.
* **PhoBERT** achieved stronger overall classification performance than mBERT but experienced larger decreases when evaluated on unseen publishers.

#### Conclusion

The results confirm that source-specific stylistic and topical biases significantly influence Vietnamese news classification performance. Models trained on data from certain publishers do not always generalize effectively to articles from unseen sources. Deep learning models, particularly BiGRU, achieved excellent overall performance but were more vulnerable to source shifts. In contrast, Naïve Bayes and mBERT demonstrated greater robustness under cross-source evaluation. These findings highlight the importance of incorporating diverse news sources during training to improve model generalization and reduce source bias.


---

### RQ4 — Data Scale Impact

**Research Question:**
How sensitive are different model families to the volume of available training data, and what minimum data requirements are needed for reliable classification performance?

**Findings:**
To evaluate sample efficiency, all models were trained on six subsets of the training data, corresponding to **1%, 5%, 10%, 25%, 50%, and 100%** of the full training set. Class distributions were preserved at each scale to ensure fair comparison. The resulting learning curves reveal substantial differences in how model families benefit from increasing amounts of training data.

#### Key Observations

* In extremely low-data settings (**1–5%** of the full dataset), traditional machine learning models demonstrated superior sample efficiency.
* **LinearSVC** and **Logistic Regression** consistently achieved higher Macro-F1 scores than transformer-based models when only limited training data was available.
* Among transformer architectures, **PhoBERT** and **XLM-R** achieved moderate performance under low-resource conditions, while **mBERT** showed the weakest results.
* As the amount of training data increased, transformer models exhibited significantly steeper learning curves and benefited more from additional samples than traditional machine learning approaches.
* The most notable performance improvements for transformers occurred between **5% and 25%** of the available training data.
* Transformer models reached their performance plateau later than classical models, indicating stronger scalability and higher capacity to leverage large datasets.
* The crossover point, where transformer-based approaches began outperforming the best traditional machine learning models, occurred at approximately **10–25%** of the full training dataset.

#### Summary of Model Behavior

| Data Regime | Best Performing Family      | Characteristics                                            |
| ----------- | --------------------------- | ---------------------------------------------------------- |
| 1–5%        | Traditional ML              | High sample efficiency and strong low-resource performance |
| 10–25%      | Competitive Transition Zone | Transformers rapidly close the performance gap             |
| 25–100%     | Transformers                | Superior scalability and stronger final performance        |

#### Conclusion

The results demonstrate a clear trade-off between sample efficiency and scalability. Traditional machine learning models are more effective in extremely low-resource scenarios, making them suitable when labeled data is scarce. In contrast, transformer-based models require larger training datasets but ultimately achieve superior performance once sufficient data becomes available. These findings suggest that model selection should depend not only on architecture but also on the amount of available training data.


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
Email:tranthanhphuoc@tdtu.edu.vn

---

## Team Members

| Student ID | Full Name | Email |
|------------|-----------|--------|
| 522H0104 | Khoa Huynh | 522h0104@student.tdtu.edu.vn |
| 522H0093 | Chau Bao Nhan | 522h0093@student.tdtu.edu.vn |

---

## Acknowledgements

We would like to express our sincere gratitude to our supervisor, **Mr. Tran Thanh Phuoc**, for his guidance, valuable feedback, and continuous support throughout the development of this project.

We also thank the Faculty of Information Technology, Ton Duc Thang University, for providing the academic environment and resources necessary for completing this work.

---

## License

This project is licensed under the MIT License.

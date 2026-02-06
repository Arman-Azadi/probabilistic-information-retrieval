# Probabilistic Information Retrieval System
**Author:** Arman Azadi
**Institution:** Iran University of Science and Technology (IUST)

## 📌 Project Overview
This project implements and evaluates advanced Information Retrieval (IR) models to rank documents for a given query. The system compares the performance of **Probabilistic Models (BM25, Language Models)** against a **Vector Space Model (TF-IDF)** baseline.

The implementation is built from scratch in Python, including a custom Inverted Index and a modular preprocessing pipeline.

## 🔬 Methodology
The system architecture consists of three core components:

### 1. Preprocessing Pipeline
* **Tokenization:** Extracting terms from raw text.
* **Normalization:** Lowercasing and punctuation removal.
* **Stopword Removal:** Filtering common English stopwords.
* **Stemming:** Applying **Porter Stemmer** to reduce words to their roots.

### 2. Retrieval Models
The following ranking functions were implemented and tuned:
* **TF-IDF (Vector Space Model):** Uses `log(1+tf) * log(N/df)` weighting.
* **Okapi BM25:** A probabilistic model optimizing for term saturation ($k_1$) and document length normalization ($b$).
* **Unigram Language Model (LM):**
    * **Smoothing:** Implemented **Jelinek-Mercer (JM)** smoothing (Linear Interpolation) to handle data sparsity and zero-probability terms.

### 3. Evaluation
The models were evaluated on the **CISI Collection** (1,460 documents, 112 queries).
* **Metrics:** Mean Average Precision (MAP), Precision at K (P@5, P@10), and R-Precision.
* **Analysis:** Interpolated Precision-Recall curves were generated to visualize the retrieval performance across different recall levels.

## 📊 Key Results
As detailed in the `Performance_Analysis_Report.pdf`:
* **BM25** generally outperformed the TF-IDF baseline, particularly when tuning parameters $k_1$ and $b$.
* **Language Models** with JM smoothing showed competitive performance, demonstrating the importance of the smoothing parameter ($\lambda$) in balancing foreground and background probabilities.

*(See the attached PDF for the full Precision-Recall plots and parameter sensitivity analysis.)*

## 🛠️ Tech Stack
* **Language:** Python 3.x
* **Libraries:** `NLTK` (for stemming/stopwords), `NumPy` (for vector operations), `Matplotlib` (for plotting P-R curves).

## 🚀 Usage
1.  Clone the repository:
    ```bash
    git clone [https://github.com/armanazadi/probabilistic-information-retrieval.git](https://github.com/armanazadi/probabilistic-information-retrieval.git)
    ```
2.  Run the notebook:
    ```bash
    jupyter notebook retrieval_system.ipynb
    ```

# Beyond Accuracy: A Decision-Impact Analysis of Sentiment Classification Errors

This repository contains the experimental pipelines and results for a four-tier comparative analysis of sentiment classification technologies. The study moves beyond aggregate metrics (Accuracy/F1) to evaluate models based on a multi-level error-based evaluation scheme, mapping technical failures to commercial risks.

## 📂 Repository Structure

### `notebooks/`
End-to-end Python pipelines.

- **`Tier 2&3 Ashwani.ipynb`**  
  Implementation of Statistical ML (Logistic Regression, NB, RF) and BERT.

- **`Tier 1&4 Ashwani.ipynb`**  
  Implementation of VADER and Generative LLM/SLM recovery (Mistral, Gemini, Phi-3, TinyLlama).

### `results/`

- **`Results Tables.xlsx`**  
  The master spreadsheet containing all 10 analysis tables, including performance metrics, confusion matrices, and the 7-point diagnostic error taxonomy.

## 📊 Dataset

The research utilizes the **Amazon Reviews for Sentiment Analysis** dataset, a large-scale collection of **4 million reviews** (**3.6M training, 400K testing**).

- **Source:** Kaggle — *[Amazon Reviews for Sentiment Analysis](https://www.kaggle.com/datasets/bittlingmayer/amazonreviews)*
- **Format:** fastText format
- **Task:** Binary classification
- **Labels:** Positive / Negative

## 🔬 Methodology: The 4-Tier Framework

The research evaluates the evolutionary variety of NLP technologies across four generations:

- **Tier 1 (Lexicon):** VADER
- **Tier 2 (Statistical ML):** Logistic Regression, Naive Bayes, Random Forest
- **Tier 3 (Transformer):** BERT
- **Tier 4 (Generative):** Mistral-7B, Gemini-1.5-Flash, Phi-3-mini, TinyLlama-1.1B

### Key Innovation: Residual Error Recovery

Tier 4 models were evaluated specifically on the residual errors of BERT, representing the **2,000 cases BERT misclassified**. This isolates the models' ability to handle complex linguistic bottlenecks such as aspect-level conflict and implicit sentiment.

## 📈 Key Findings

- **The Ambiguity Indicator:** Tier 4 models disagreed on **97.30%** of BERT’s residual errors, suggesting that some e-commerce sentiment is mathematically irreducible due to inherent linguistic ambiguity.
- **Recovery Leader:** **Mistral** achieved the highest recovery rate (**67.17%**) with the most balanced operational profile.
- **Operational Risk:** **TinyLlama** exhibited a severe positive prediction bias, making it operationally hazardous for churn detection as it systematically suppresses negative signals.
- **The Cascading Pipeline:** The study recommends a hybrid architecture using **BERT** for high-speed primary triage and **Mistral** for targeted escalation of ambiguous cases.
- ## 👤 Author

**Ashwani Kumar**  
Master’s Student in AI and Data Science  
Berlin, Germany

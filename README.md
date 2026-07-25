# Cross-Linguistic Analysis of Social Bias in English and Persian Language Models

> **Master’s Thesis** | Stockholm University | Multilingual NLP, Empirical Language Analysis & Responsible AI

[![Python](https://img.shields.io/badge/Python-3.10%2B-blue.svg)](https://www.python.org/)
[![Hugging Face](https://img.shields.io/badge/Hugging%20Face-Transformers-orange.svg)](https://huggingface.co/)
[![License](https://img.shields.io/badge/License-MIT-green.svg)](LICENSE)

## Overview

This repository contains the data, notebooks, analysis code, and thesis materials for an empirical cross-linguistic study of social bias in English and Persian large language models.

The research compares **LLaMA** and **PersianLLaMA** using an English–Persian adaptation of the **StereoSet** benchmark. It examines how bias patterns vary across languages and models, and how linguistic and technical factors—including tokenisation, morphology, prompt formulation, and evaluation metrics—can influence the results.

The study focuses on four bias categories:

- gender
- race
- religion
- profession

Rather than treating model outputs as direct evidence of social bias, the project considers several possible explanations for observed differences, including language structure, cultural adaptation, model training, tokenizer behaviour, and limitations of the evaluation method.

## Thesis

**Official thesis title:**  
*Bias Evaluation in Large Language Models for Non-English Languages*

**Study focus:**  
An empirical cross-linguistic comparison of English and Persian model behaviour.


## Research Questions

The project addresses the following questions:

1. How do social-bias patterns differ between English and Persian language models?
2. Do the models behave differently across gender, race, religion, and profession categories?
3. How do tokenisation and morphological differences affect cross-linguistic evaluation?
4. How sensitive are the results to the choice of evaluation metric?
5. Which findings appear stable, and which may reflect methodological or dataset-related effects?

## Data

The study uses a bilingual adaptation of **StereoSet**, with parallel English and Persian material.

The dataset preparation involved:

- translating and adapting English prompts into Persian
- checking semantic and cultural suitability
- preserving stereotype, anti-stereotype, and unrelated labels
- organising examples by bias category
- preparing model-specific input formats
- adding tokenizer and sentence-level features for further analysis

The dataset is intended for controlled comparison rather than as a complete representation of social bias in either language or culture.

## Models

| Model | Language focus | Role in the study |
|---|---|---|
| LLaMA | English / multilingual baseline | Evaluation of English examples |
| PersianLLaMA | Persian-adapted model | Evaluation of Persian examples |

The comparison is cross-linguistic, but it is not assumed that the two models are identical apart from language. Differences in model adaptation, training data, tokenisation, and linguistic structure are considered when interpreting the findings.

## Methods

The analysis combines multilingual dataset preparation, model evaluation, linguistic comparison, and quantitative analysis.

### Evaluation metrics

- **Pseudo-Log-Likelihood (PLL)**
- **Categorical Bias (CB)**
- **Approximate next-token probability (APX)**
- **Pairwise stereotype–anti-stereotype comparisons**

### Linguistic and tokenizer analysis

- token count and sequence length
- subword fragmentation
- differences in tokenisation across English and Persian
- morphology-related variation
- category-level and language-specific patterns
- relationships between tokenizer features and bias scores

### Research workflow

1. Dataset translation and adaptation
2. Data cleaning and annotation checks
3. Model-specific preprocessing
4. Bias-score calculation
5. Tokenizer analysis
6. Cross-language and cross-model comparison
7. Statistical analysis and visualisation
8. Interpretation of linguistic and methodological factors

## Main Findings

The analysis shows that:

- bias patterns vary across languages, models, and social categories;
- English and Persian inputs are tokenised differently, affecting sentence representation and probability-based evaluation;
- no single metric fully captures model behaviour;
- category-level findings can change depending on the model and evaluation method;
- cross-linguistic differences should not automatically be interpreted as purely cultural or linguistic effects;
- careful validation is needed to separate model behaviour from tokenizer, dataset, and metric-related influences.

The broader conclusion is that multilingual bias evaluation requires attention not only to model outputs, but also to language structure, data adaptation, tokenisation, and the assumptions built into the evaluation framework.

## Repository Structure

```text
.
├── README.md
├── Thesis_Evaluating LLMs_Bias in Non English Languages_26Nov.pdf
├── notebooks/
│   ├── model evaluation notebooks
│   ├── PLL, CB, and APX analyses
│   ├── tokenizer analysis
│   └── combined results and visualisations
├── data/
│   ├── bilingual English–Persian dataset
│   ├── model-level evaluation results
│   ├── category-level results
│   └── tokenizer features
└── requirements.txt
```

## Reproducibility

### Requirements

- Python 3.10 or later
- Jupyter Notebook or Google Colab
- Hugging Face Transformers
- access to the required model weights
- GPU recommended for model evaluation

### Installation

```bash
git clone https://github.com/soroushbagheri/LLM-Low-resource-Language_Bias-Evaluation.git
cd LLM-Low-resource-Language_Bias-Evaluation
pip install -r requirements.txt
```

The notebooks document the main stages of the analysis. Depending on model access and computational resources, some experiments may need to be run in Google Colab or another GPU-enabled environment.

## Research Contribution

This project contributes an English–Persian case study of multilingual bias evaluation and highlights the difficulty of comparing model behaviour across languages.

Its main contribution is not only the comparison of bias scores, but also the examination of how linguistic structure, tokenisation, dataset adaptation, and metric choice shape the conclusions that can be drawn from such evaluations.

The project reflects a broader research interest in:

- empirical and computational linguistics
- multilingual language analysis
- under-represented languages in NLP
- linguistic variation across languages and models
- transparent and reproducible evaluation methods
- responsible language technology

## Limitations

This study has several limitations:

- the evaluation is based on one main benchmark family;
- translated or adapted examples may not capture all language- and culture-specific stereotypes;
- the compared models differ in training and adaptation, not only in language;
- probability-based metrics are affected by tokenisation and model architecture;
- the findings should not be generalised to all English or Persian speakers, datasets, or language models.

These limitations are treated as part of the research problem rather than as purely technical issues.

## Related Work

- Nadeem et al. (2021), *StereoSet: Measuring Stereotypical Bias in Pretrained Language Models*
- Nangia et al. (2020), *CrowS-Pairs: A Challenge Dataset for Measuring Social Biases in Masked Language Models*
- Touvron et al. (2023), *Llama 2: Open Foundation and Fine-Tuned Chat Models*
- Liang et al. (2022), *Holistic Evaluation of Language Models*

## Author

**Soroush Bagheri**  
MSc in Computer and Systems Sciences, Stockholm University

Research interests: empirical and computational linguistics, multilingual NLP, language-model evaluation, linguistic variation, interpretability, and responsible AI.

[GitHub profile](https://github.com/soroushbagheri)

## License

This repository is released under the [MIT License](LICENSE). Dataset and model use may also be subject to the licences and terms of their original providers.

## Acknowledgements

This research was completed as a master’s thesis at Stockholm University. I am grateful to my supervisors and colleagues for their guidance and feedback throughout the project.

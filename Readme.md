# Food Review NLP with Emotion and Explainability

Course project for Natural Language Processing focused on large-scale food review analysis, emotion mining, transformer-based rating prediction, and explainable NLP.

## Project Summary

This project studies user reviews from Food.com to answer three related questions:

1. What emotional signals appear in food reviews and how do they relate to ratings?
2. Can ingredient mentions and review text improve our understanding of user preferences?
3. Which transformer model gives the best balance of predictive quality and practical usability?

The notebook combines exploratory analysis, lexicon-based emotion detection, ingredient extraction, transformer training, explainability, and embedding analysis in one reproducible workflow.

## Main Highlights

- End-to-end notebook covering EDA, preprocessing, emotion analysis, modeling, explainability, and comparison.
- Support for BERT, RoBERTa, DistilBERT, an improved DistilBERT variant, and an enhanced RoBERTa model.
- Portable dataset loading with automatic path resolution based on the project location.
- Local artifact management under `artifacts/` instead of machine-specific absolute paths.
- Reviewer-friendly notebook structure with section headers and clearer setup messaging.

## Repository Layout

```text
.
|-- NLP Food Review.ipynb
|-- Readme.md
|-- requirements.txt
|-- .gitignore
|-- data/                         # recommended dataset location
`-- artifacts/                    # generated automatically for models and plots
```

## Dataset

Source: Food.com Recipes and Interactions Dataset  
Paper link: https://aclanthology.org/D19-1613/

Expected files:

- `RAW_recipes.csv`
- `RAW_interactions.csv`
- `interactions_train.csv`

The notebook looks for these files in the following locations, in this order:

- path defined by `FOOD_REVIEW_DATA_DIR`
- `./data`
- `./dataset`
- `./datasets`
- `./Food.com Recipes and Interactions Dataset`
- project root

## Quick Start

1. Create and activate a Python environment.
2. Install dependencies:

```bash
pip install -r requirements.txt
```

3. Put the dataset files in `data/` or set `FOOD_REVIEW_DATA_DIR`.
4. Open `NLP Food Review.ipynb`.
5. Run the notebook from top to bottom.

## What the Notebook Covers

### 1. Environment and Dataset Setup

- Validates dependencies
- Detects the project root automatically
- Resolves dataset files dynamically
- Creates `artifacts/` for saved outputs

### 2. Exploratory Data Analysis

- Dataset structure and missing-value inspection
- Rating distribution analysis
- Review-length and preparation-time visualization
- Early inspection of tags, ingredients, and review text

### 3. Preprocessing

- Cleaning of recipe ingredients and steps
- Review normalization
- Merging recipe and interaction data
- Preparation of train, validation, and test splits

### 4. Emotion and Aspect Analysis

- NRC lexicon-based emotion extraction
- Emotion-by-rating comparisons
- Cuisine-level emotion patterns
- Ingredient mention recovery with spaCy phrase matching

### 5. Transformer Modeling

- BERT baseline
- RoBERTa model
- DistilBERT model
- Improved DistilBERT experiment
- Enhanced RoBERTa final model

### 6. Explainability and Representation Analysis

- LIME explanations
- SHAP explanations
- t-SNE and PCA visualization
- Clustering and similarity analysis

## Reported Model Results

| Model | Accuracy | Weighted F1 | Loss | Notes |
| --- | ---: | ---: | ---: | --- |
| BERT | 77.32% | 78.18% | 1.7360 | Strong baseline |
| RoBERTa | 76.76% | 77.93% | 1.1838 | Better loss, similar classification quality |
| DistilBERT | 74.89% | 76.49% | 1.0959 | Smaller and faster |
| Enhanced RoBERTa | 79.62% | 79.61% | 0.7608 | Best overall result |

## Reproducibility Notes

- The notebook saves trained models, plots, and embeddings under `artifacts/`.
- GPU availability affects training time and may slightly affect final results.
- Some sections, especially SHAP, t-SNE, and full model training, are computationally expensive.
- If you only want to inspect the project, the notebook can still be read section by section without rerunning every training block.

## Suggested Review Angle

If this work is being reviewed by a professor, evaluator, or hiring panel, the strongest parts to focus on are:

- the clear problem framing across emotion analysis and recommendation-oriented modeling
- the progression from lexicon-based analysis to neural models
- the comparison across multiple transformer families
- the inclusion of explainability rather than only headline accuracy
- the portability improvements that remove machine-specific assumptions

## Authors

- Eshmam Rayed
- Mubeen Khan
- Sabah Fiaz

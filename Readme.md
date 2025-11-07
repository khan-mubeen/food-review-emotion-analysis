# 🧠 Food Review NLP with Emotion and Explainability  

**Authors:** Eshmam Rayed, Mubeen Khan, Sabah Fiaz  
**Course Project:** Natural Language Processing (Project 19)  

---

## 🎯 Goal  
Use **emotion detection**, **Named Entity Recognition (NER)**, and **explainable NLP** to analyze food reviews and enhance recommendation systems.  
This project combines *emotion classification*, *aspect-based sentiment analysis*, *ingredient-level entity extraction*, and *explainable transformer models* to understand user perceptions in online food platforms.  

---

## 📊 Dataset  
**Source:** [Food.com Recipes and Interactions Dataset](https://aclanthology.org/D19-1613/)  
- ~1.1M user reviews across ~230K recipes  
- Covers 18 years of user interactions  
- Strong class imbalance: 72% of reviews rated 5 stars  

---

## ⚙️ Project Pipeline  

### 1. **Exploration of Review Dataset**  
- Analyze linguistic patterns (review length, top adjectives).  
- Visualize sentiment-bearing words like *“delicious”*, *“bland”*.  

### 2. **Emotion Classification**  
- Classify reviews using **NRC Emotion Lexicon** and **Transformer models** (BERT, RoBERTa, DistilBERT).  
- Detect 8 emotions: *joy, trust, fear, sadness, anger, disgust, surprise, anticipation*.  

### 3. **Emotion vs. Rating Correlation**  
- Compute Pearson correlations between emotions and user ratings.  
- *Joy* shows positive correlation (+0.073) while *anger* and *disgust* correlate negatively.  

### 4. **Cuisine-Based Emotion Analysis**  
- Compare emotional tone across cuisines (Italian, Indian, Mexican, etc.).  
- *French* and *Indian* cuisines evoke the most joyful responses.  

### 5. **NER for Ingredient Mentions**  
- Use **spaCy** to extract ingredient entities.  
- Identify top “joy-inducing” ingredients (e.g., *white chocolate curls*, *lamb chops*).  

### 6. **Aspect-Based Sentiment Analysis**  
- Examine aspects like *preparation time*, *difficulty*, and *healthiness*.  
- Visualize emotion-specific word clouds for each aspect.  

### 7. **Explainable Classification Models**  
- Fine-tune **BERT**, **RoBERTa**, **DistilBERT**, and **Enhanced RoBERTa**.  
- Use **LIME** and **SHAP** for interpretability.  

### 8. **Enhanced RoBERTa Optimization**  
- Implemented cosine annealing learning rate, label smoothing, dropout=0.25, weight decay=0.01, gradient clipping=1.0, and class rebalancing.  
- Achieved **79.62% test accuracy** and **56.18% loss reduction** over baseline BERT.  

---

## 🧩 Results  

| Model | Accuracy | F1-Score | Loss Reduction | Params | Train Time |
|--------|-----------|----------|----------------|---------|-------------|
| BERT | 77.32% | 78.18% | – | 110M | 139m |
| RoBERTa | 76.76% | 77.93% | 31.8% | 125M | 134m |
| DistilBERT | 74.89% | 76.49% | 36.9% | 66M | 74m |
| **Enhanced RoBERTa** | **79.62%** | **79.61%** | **56.18%** | **125M** | **76m** |

- **LIME Analysis:** reveals strong reliance on sentiment-rich words like *“terrific”* and *“wonderful”*.  
- **Error Cases:** model struggles with mixed or negated sentiment (“tasted real good” misclassified).  

---

## 📈 Evaluation  
- **Classification Metrics:** Accuracy, F1, Confusion Matrix  
- **Recommendation Metrics:** RMSE, Precision@N  
- **Visualization:** t-SNE for embedding clustering  

---

## 💡 Key Insights  
- Emotional language (esp. *joy* and *trust*) correlates with higher ratings.  
- Ingredient mentions like *chocolate* and *lamb* drive positive emotion.  
- Enhanced RoBERTa provides superior stability and generalization.  
- Dataset imbalance remains the main bottleneck — oversampling or SMOTE is recommended for future work.  

---

## 🧠 Tools & Libraries  
- **Python 3.9**, **PyTorch**, **Transformers (HuggingFace)**  
- **spaCy**, **NRCLex**, **NLPAug**, **scikit-learn**, **Matplotlib**, **WordCloud**  
- **Explainability:** LIME, SHAP  


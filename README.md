# MinneMUDAC-2025-Mentorship-Matching
This repository contains our solution to the 2025 **MinneMUDAC Data Science Challenge**, in partnership with **Big Brothers Big Sisters (BBBS)**. Our goal: uncover what makes a mentorship match succeed or fail — using unstructured data like email exchanges, call transcripts, and free-text surveys.

# 🤝 Predicting Successful Mentorship Matches – MinneMUDAC 2024

This repository contains our solution to the 2024 **MinneMUDAC Data Science Challenge**, in partnership with **Big Brothers Big Sisters (BBBS)**. Our goal: uncover what makes a mentorship match succeed or fail — using unstructured data like email exchanges, call transcripts, and free-text surveys.

🏆 **Top 5 out of 70+ teams** — Presented to 25+ executive judges including the CEO of BBBS.

---

## 🧠 Problem Statement

**What separates a successful mentorship match from a failed one?**

While no match is guaranteed to succeed, we explored controllable factors (communication, engagement, emotional tone, delays, etc.) and modeled them to predict match outcomes and suggest interventions.

---

## 🔍 Key Contributions

- **Preprocessed 12,000+ unstructured interactions**: emails, support call transcripts, survey free-text.
- **Built NLP pipelines** with HuggingFace Transformers: tokenization, embeddings, cleanup.
- **Extracted features** using:
  - **BERTopic** for topic modeling
  - **RoBERTa** for emotion & sentiment scores
- **Trained & tuned supervised models** (e.g., XGBoost, logistic regression)
- **Built a weighted ensemble** that reduced RMSE from `0.24 → 0.12` (50% improvement)
- **Presented insights to stakeholders** with actionable strategies

---

## 🧪 NLP & Modeling Pipeline

1. **Data Preprocessing**
   - Cleaned text: stopword removal, spell correction, tokenization
   - Extracted features from unstructured fields using Transformers

2. **Sentiment & Emotion Scoring**
   - Used `RoBERTa-base` to score sadness, joy, and frustration
   - Example: Unsuccessful matches had nearly **2x the average sadness** in support calls

3. **Topic Modeling**
   - Used **BERTopic** to cluster themes across survey responses and call notes

4. **Feature Engineering**
   - Created interaction metrics: word count, introversion index, delay periods, etc.

5. **Modeling**
   - Supervised models trained on structured + NLP features
   - Models stacked into an ensemble using weighted averaging
   - Final model validated with 5-fold cross-validation

---

## 📈 Results

| Metric                  | Baseline | Final Model |
|-------------------------|----------|-------------|
| RMSE (5-fold CV)        | 0.24     | **0.12**     |
| Positive Predictive Power | Low     | **Significantly improved** |
| Human Interpretability  | ✓✓✓      | ✓✓✓✓✓        |

---

## 📊 Key Findings

| Feature                        | Successful Matches | Unsuccessful Matches |
|-------------------------------|--------------------|----------------------|
| Avg. Sadness Score (calls)    | 9                  | 17                   |
| Avg. Introversion Index       | 27                 | 32                   |
| Wait Time Before Match        | 63 days            | 88 days              |
| Avg. Word Count in Rationale  | 70 words           | 55 words             |

- ~70% of off-cadence support calls occurred within 6 months of match closure
- Top closure causes: life changes (24.6%), lost contact (15%), time constraints (13.9%)

---

## 🛠️ Intervention Strategy

Based on our insights, we propose a **survey-triggered intervention plan**:

- Gather early warning signs via key survey questions
- Confirm Big's willingness to continue
- Connect struggling Bigs with veteran mentors (alumni network)
- Create personalized action plans + follow-ups

Sample Survey Questions:
- “On a scale of 1–10, how satisfactory have your recent match meetings been?”
- “Do you expect significant change in your availability?”
- “Would you like to discuss challenges with our team?”



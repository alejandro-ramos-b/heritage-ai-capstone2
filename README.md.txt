# Heritage AI Capstone 2

A two-part AI project combining computer vision and recommendation systems applied to cultural heritage and tourism.

---

## Part 1: Historical Architecture Classifier

### Overview
A CNN image classifier built with transfer learning (VGG16) to identify 10 categories of historical architectural structures.

### Model
- **Base:** VGG16 pre-trained on ImageNet (frozen layers)
- **Custom head:** Flatten → Dense(256, ReLU) → Dropout(0.5) → Dense(10, Softmax)
- **Optimizer:** Adam | **Loss:** Categorical Crossentropy

### Results
| Model | Val Accuracy |
|-------|-------------|
| Baseline (no augmentation) | 70.77% |
| Augmented | 70.24% |

### Key Observations
- Mild overfitting: train accuracy ~80% vs val accuracy ~70%
- Augmentation stabilized early validation performance
- Both models converged consistently across 10 epochs

### Files
- `best_model.keras` — baseline model
- `best_model_aug.keras` — augmented model
- `model_comparison.png` — training curves

---

## Part 2: Tourism Recommendation Engine

### Overview
A recommendation system built on Indonesian tourism data using three approaches.

### Dataset
- `tourism_with_id.xlsx` — 437 tourist places across 5 Indonesian cities
- `tourism_rating.csv` — 10,000 user ratings
- `user.csv` — 300 user profiles

### Approaches
| Method | Technique | Output |
|--------|-----------|--------|
| Content-Based | TF-IDF + Cosine Similarity | Places with same category & city |
| Collaborative | User Similarity Matrix | Places liked by similar users |
| Hybrid | Content + Collaborative | Personalized + relevant recommendations |

### Key Observations
- Content-based filtering groups places by category and city effectively
- Collaborative filtering introduces diversity across cities and categories
- Hybrid approach balances relevance with personalization ranked by rating

### Limitations
- Cold start problem for new users
- Limited to 5 Indonesian cities
- Time_Minutes column excluded (53% missing values)

### Files
- `recommendation_results.json` — sample outputs from all three approaches

---

## Tools & Libraries
- TensorFlow / Keras
- Scikit-learn
- Pandas / NumPy
- Matplotlib

## Author
Alex Ramos | Microsoft AI Engineering Certification — Simplilearn
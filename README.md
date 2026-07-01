# Fake Review Detection using Random Forest & Behavioral Features

Detects fake and misleading online reviews by combining text-based signals with reviewer behavioral patterns, using a Random Forest classifier trained and benchmarked against a baseline model.

## Overview

Online platforms lose user trust when fake reviews go undetected — inflating ratings, misleading buyers, and undermining marketplace integrity. This project builds a supervised machine learning pipeline that classifies reviews as **genuine** or **suspicious** by analyzing both the review text and the behavioral patterns of the reviewer (posting frequency, rating deviation, account activity, etc.).

Two models were trained and compared to measure the real impact of behavioral feature engineering:

- **Baseline model:** Random Forest (100 trees) using text features only
- **Modified model:** Random Forest (200 trees) using text + engineered behavioral features

The modified model outperformed the baseline across every metric, most notably in recall — the metric that matters most for fraud detection, since a missed fake review is costlier than a false alarm.

## Results

Trained and evaluated on a Kaggle dataset of 100,000+ Amazon reviews (40,432 rows after cleaning, 10,108 held-out test samples).

| Metric    | Basic RF (100 trees, text only) | Modified RF (200 trees + behavioral features) | Improvement |
|-----------|:---:|:---:|:---:|
| Accuracy  | 73.8% | **80.9%** | +7.06% |
| Precision | 73.5% | **79.6%** | +6.13% |
| Recall    | 75.3% | **83.5%** | +8.19% |
| F1-Score  | 74.4% | **81.5%** | +7.12% |

**Key takeaway:** adding behavioral features and expanding the ensemble produced consistent gains across every metric, with the largest improvement in recall — indicating the model got meaningfully better at catching fake reviews rather than just avoiding false positives.

## Features Used

**Text-based features**
- [e.g., review length, TF-IDF vectors, sentiment polarity — fill in your actual ones]

**Behavioral features**
- [e.g., reviewer posting frequency / burst rate]
- [e.g., rating deviation from the product's average rating]
- [e.g., reviewer account age or activity history]
- [e.g., verified purchase flag]

*(Replace the placeholders above with the exact features you engineered — this is usually the first thing reviewers/interviewers ask about.)*

## Tech Stack

- **Language:** Python
- **ML:** Scikit-learn (Random Forest)
- **Data Processing:** Pandas, NumPy
- **Visualization:** Matplotlib
- **Interface:** Interactive HTML demo (`index.html`) for uploading a dataset and viewing live results

## Project Structure

```
├── index.html          # Interactive demo — upload dataset, run analysis, view results
├── file                # [rename/describe this — e.g., model training script, notebook, etc.]
└── README.md
```

## How It Works

1. **Load & clean data** — remove nulls, duplicates, and malformed entries from the raw review dataset
2. **Feature engineering** — extract text features and compute behavioral signals per reviewer
3. **Train baseline model** — Random Forest (100 trees) on text features only
4. **Train modified model** — Random Forest (200 trees) on text + behavioral features
5. **Evaluate** — compare both models on accuracy, precision, recall, and F1-score
6. **Visualize** — side-by-side metric comparison, improvement chart, and confusion matrices

## Applications

- E-commerce review monitoring
- Fraud detection systems
- Online marketplace trust & safety
- Social media review analysis

## Future Enhancements

- NLP-based text analysis using transformer embeddings (e.g., BERT) instead of traditional text features
- Real-time review monitoring pipeline for live platform integration

## Dataset

Source: [Kaggle — add exact dataset name/link here]
Size: ~100,000 reviews (40,432 rows after preprocessing)

## Author

[Your name] — [LinkedIn/GitHub link]
#project UI
<img width="926" height="744" alt="image" src="https://github.com/user-attachments/assets/882b1d99-53d3-4e7b-8cda-6993ce4f47f9" />

<img width="829" height="332" alt="image" src="https://github.com/user-attachments/assets/808d22a1-dfe4-4843-9e1f-287188efa2d0" />

#results
<img width="666" height="383" alt="image" src="https://github.com/user-attachments/assets/eca7e293-7656-4e08-a50f-fa0723a50beb" />



Author
Anwesha
B.Tech Student

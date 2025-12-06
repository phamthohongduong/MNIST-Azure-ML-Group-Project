# MNIST Handwritten Digit Classification
### A Comparative Study of Six Machine Learning Algorithms

## Project Overview

This project evaluates six machine learning algorithms on the MNIST handwritten digit classification task using **Microsoft Azure Machine Learning Designer**. Our objective was to achieve at least **95% F1-score** across all digit classes.

**Key Results:**
- **3 models exceeded 95% target**
- Best performer: **Multiclass Boosted Decision Tree (98.13% accuracy)**
- Comprehensive comparison of linear vs. ensemble vs. neural network approaches

---

## Video Presentation

**Watch our 15-minute project presentation:**  
*Link included in the Final_Report.pdf*
*Note: The video covers project overview, methodology, results, and future work recommendations.*

---

## Full Report

**[View PDF Report](./Final_Report.pdf)**

**Report Contents:**
1. Introduction & Dataset Description
2. Data Preprocessing Pipeline
3. Six Classification Models & Hyperparameter Tuning
4. Results & Performance Evaluation
5. Discussion: Model Complexity vs. Accuracy Trade-offs
6. Conclusion & Future Work

---

## Models Evaluated

| Rank | Model | Accuracy | F1-Score | Status |
|:---:|:---|:---:|:---:|:---:|
| 1 | **Multiclass Boosted Decision Tree** | 98.13% | 0.9813 | Exceeds target |
| 2 | **Multiclass Neural Network** | 97.99% | 0.9799 | Exceeds target |
| 3 | **Multiclass Decision Forest** | 96.98% | 0.9698 | Exceeds target |
| 4 | Multiclass Logistic Regression | 92.58% | 0.9258 | Below target |
| 5 | SVM + One-vs-All Multiclass | 91.79% | 0.9179 | Below target |
| 6 | Averaged Perceptron + One-vs-All | 88.84% | 0.8884 | Below target |

---

## Methodology

**Platform:** Microsoft Azure Machine Learning Designer  
**Dataset:** MNIST (70,000 images: 60,000 train / 10,000 test)  
**Preprocessing:** 
- Binary format (.ubyte) → CSV conversion
- Flattened 28×28 images → 784 features
- 80/20 train-validation split

**Hyperparameter Tuning:**
- Grid search with F-score optimization
- Separate validation set for model selection
- Final evaluation on held-out test set

**Evaluation Metrics:**
- Accuracy, Precision (Macro/Micro), Recall (Macro/Micro)
- F1-Score, Confusion Matrices

---

## Key Findings

### What Worked
- **Ensemble methods vastly outperformed linear models** (6-10% accuracy gap)
- **Boosted Trees** achieved best performance through iterative error correction
- **Neural Networks** effectively captured non-linear patterns despite simple architecture

### Challenges
- **Linear models struggled with curved digits** (e.g., 3 vs. 5, 8 vs. 9)
- Consistent confusion between visually similar digit pairs across all models
- ~200 errors (2%) on test set concentrated on genuinely ambiguous samples

### Insights
- Model complexity directly correlates with accuracy on image tasks
- Handwriting variability (incomplete strokes, style differences) causes most errors
- Even state-of-the-art models plateau due to inherent dataset ambiguity

---

## Future Work

1. **Implement CNNs** (Convolutional Neural Networks) using PyTorch/TensorFlow
   - Expected improvement: 98% → 99%+
   
2. **Ensemble Stacking**
   - Combine predictions from top 3 models (Boosted Tree + Neural Net + Random Forest)
   
3. **Investigate PyTorch and TensorFlow 2**
   - Manually analyze ~200 errors to identify patterns

---

## Repository Structure

├── Final_Report.pdf          # Complete project report
├── README.md
├── Training jobs output/
│   ├── 1. Multiclass Logistic Regression/
│   │   ├── Screenshots/
│   │   ├── output_data.csv
│   │   ├── Job_evaluate_model_OutputsAndLogs.zip
│   ├── 2. MultiClass Boosted Decision Tree/
│   │   ├── Screenshots/
│   │   ├── output_data.csv
│   │   ├── Job_evaluate_model_OutputsAndLogs.zip
│   └── 3. Two-Class Support Vector Machine +One-vs-All Multiclass/
│   │   ├── Screenshots/
│   │   ├── output_data.csv
│   │   ├── Job_evaluate_model_OutputsAndLogs.zip
│   ├── 4. Multiclass Neural Network
│   │   ├── Screenshots/
│   │   ├── output_data.csv
│   │   ├── Job_evaluate_model_OutputsAndLogs.zip
│   ├── 5. Multiclass Decision Forest
│   │   ├── Screenshots/
│   │   ├── output_data.csv
│   │   ├── Job_evaluate_model_OutputsAndLogs.zip
│   └── 6. Averaged Perceptron
│   │   ├── Screenshots/
│   │   ├── output_data.csv
│   │   ├── Job_evaluate_model_OutputsAndLogs.zip
│   └── Cancelled -MultiClass Boosted Decision Tree
│   │   ├── Screenshots/
│   │   ├── output_data.csv
│   │   ├── Job_evaluate_model_OutputsAndLogs.zip
└── convert_csv_notebook.ipynb

---

## Technologies Used

- **Platform:** Microsoft Azure Machine Learning Designer
- **Programming:** Python (for data preprocessing)
- **Libraries:** NumPy, Pandas
- **Dataset:** MNIST (LeCun et al., 1998) https://www.kaggle.com/datasets/hojjatk/mnist-dataset

---

## Team Members

- [Tigor Tenorio De Melo]
- [Daria Khareva]
- [Bonnie Huo]
- [Tho Hong Duong Pham]

**Course:** Intro to Machine Learning - AIGC-5102-0TA  
**Institution:** [Humber Polytechnic]  
**Date:** December 2025

---

## Acknowledgments

- Professor [Hossein Pourmodheji] for project guidance
- Azure for Students program for cloud computing credits

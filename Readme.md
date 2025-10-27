# **Prediction of NSCLC Using Machine Learning and Deep Learning**

## **Project Overview**

This project focuses on predicting **Non-Small Cell Lung Cancer (NSCLC)** using **binary classification** approaches with **machine learning (ML)** and **deep learning (DL)**. The study leverages gene expression data from the GEO dataset **GSE81089**, distinguishing between **Normal** and **Tumor** samples.

The project demonstrates the versatility of ML algorithms and compares their performance with a deep learning model, uncovering complex patterns in NSCLC gene expression data.

---

## **Dataset**

* Source: [GEO Database](https://www.ncbi.nlm.nih.gov/geo/)
* Accession Number: **GSE81089**
* Format: `.tsv` downloaded → converted to `.csv`
* Features: Ensemble gene IDs and gene expression counts
* Target: **Binary classification** — 0: Normal, 1: Tumor

---

## **Software & Tools**

* **Python:** Jupyter Notebook, 
* **Libraries:** scikit-learn, TensorFlow/Keras, pandas, numpy, matplotlib, seaborn
* **R:** RStudio, DESeq2/edgeR for Differential Gene Expression (DGE) analysis
* **Database:** GEO

---

## **Machine Learning & Deep Learning Models**

1. **Logistic Regression** – baseline model
2. **Support Vector Machines (SVM)**

   * Linear kernel
   * Polynomial kernel
   * Radial Basis Function (RBF) kernel
3. **Artificial Neural Network (ANN)** – captures complex, nonlinear relationships

---

## **Results**

### **1. t-SNE Visualization**

* Shows clear separation of **Normal** and **Tumor** samples.
  *(Include figure: `results/tsne_plot.png`)*

### **2. Confusion Matrices & Performance Metrics**

| Model               | Accuracy | Precision | Recall | F1-Score | ROC-AUC |
| ------------------- | -------- | --------- | ------ | -------- | ------- |
| Linear SVM          | 96%      | 98%       | 98%    | 98%      | 0.776   |
| Polynomial SVM      | 96%      | 96%       | 100%   | 98%      | 0.792   |
| RBF SVM             | 96%      | 96%       | 100%   | 98%      | 0.952   |
| Logistic Regression | 93%      | 98%       | 94%    | 96%      | 0.843   |
| ANN                 | 90%      | 98%       | 92%    | 95%      | 0.813   |

### **3. ROC Curve Comparison**

* RBF SVM achieved the highest ROC-AUC (0.952), indicating superior discrimination.
* Combined ROC curves of all models provide a visual comparison.
  *(Include figure: `results/combined_roc_curves.png`)*

### **4. Precision vs Recall**

* Bar plot comparing precision and recall for all models.
* Shows trade-offs between sensitivity (recall) and specificity (precision).
  *(Include figure: `results/precision_vs_recall.png`)*

### **5. Heatmap of NSCLC Gene Expression**

* Heatmap of top 50 variable genes illustrates molecular differences between Normal and Tumor samples.
  *(Include figure: `results/nsclc_heatmap.png`)*

---

## **Differential Gene Expression (DGE) Analysis**

* Conducted in **R** using DESeq2/edgeR.
* Identified key genes differentially expressed between tumor and normal samples.
* Supports predictive modeling and biological interpretation.

---

## **Conclusion**

* SVM with RBF kernel showed the best overall performance for NSCLC prediction.
* ANN performed well, capturing complex patterns, while Logistic Regression provided a simple baseline.
* Heatmaps and t-SNE plots confirm the discriminatory power of gene expression features.
* Integration of ML, DL, and DGE analysis demonstrates a robust workflow for cancer prediction.
* Insights from this project may support **early detection, treatment planning, and improved patient outcomes**.

---

## **Repository Structure**

```
NSCLC-ML-Prediction/
│
├── data/
│   ├── raw/             # Original GEO .tsv files
│   └── processed/       # Cleaned CSV files
│
├── notebooks/
│   ├── 00_Data_Preparation.ipynb
│   ├── 01_TSNE_Visualization.ipynb
│   ├── 02
│   └── 03
│   ├── 04
│   └── 05
│   ├── 06
│   └── 07
│
├── src/                 # Python scripts for preprocessing and training
├── R/                   # R scripts for DGE analysis
├── results/             # Plots and heatmaps
├── models/              # Saved ML/DL models
├── requirements.txt     # Python dependencies
├── README.md
└── LICENSE
```

---

## **Usage**

1. Clone the repository:

```bash
git clone https://github.com/yourusername/NSCLC-ML-Prediction.git
```

2. Install Python dependencies:

```bash
pip install -r requirements.txt
```

3. Open Jupyter Notebooks to explore EDA, ML/DL training, and visualizations.
4. Check **R scripts** for differential gene expression analysis.

---

## **References**

* GEO Database: [GSE81089](https://www.ncbi.nlm.nih.gov/geo/query/acc.cgi?acc=GSE81089)
* Pedregosa et al., 2011. *Scikit-learn: Machine Learning in Python*
* Chollet, 2015. *Keras Documentation*
* Love et al., 2014. *DESeq2: Differential gene expression analysis*

---
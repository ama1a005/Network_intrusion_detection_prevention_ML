
# 🚨 Network Intrusion Detection & Prevention System (NIDPS)

This project implements a Machine Learning-based Intrusion Detection System using the **KDDCup'99** dataset.  
It focuses on identifying and mitigating malicious network activities across four major attack categories:

- **DoS** (Denial of Service)
- **Probe**
- **R2L** (Remote-to-Local)
- **U2R** (User-to-Root)
- And **Normal** connections for baseline comparison

---

## 🧠 Objective
To build a robust classification model that:
- Handles severe dataset imbalance using **Safe-SMOTE**
- Removes noise/outliers using **Isolation Forest**
- Achieves high detection accuracy across **all** attack categories

---

## 📊 Dataset Details
- Dataset: **KDDCup’99** (10% subset)
- Total samples after preprocessing: **197,609**
- Attack categories mapped into 4 major classes
- Trailing dots removed from labels
- Encoded categorical features (`protocol_type`, `service`, `flag`)
- Standardization applied to numeric features

---

## ⚙️ Methodology
| Step | Description |
|------|-------------|
| **1. Data Cleaning** | Label stripping + Filtering only valid attack mappings |
| **2. Encoding** | LabelEncoder for categorical features |
| **3. Class Balancing** | Safe-SMOTE with controlled sampling |
| **4. Outlier Detection** | Removed 3,128 outliers (1.0002%) via Isolation Forest |
| **5. Train-Test Split** | 60/40 split with stratification |
| **6. Scaling** | StandardScaler applied |
| **7. Model Training** | Classifier trained post-balancing |
| **8. Evaluation & Visualization** | Classification metrics + Data distribution graphs |

---

## ✨ Safe-SMOTE Sampling Summary
| Class | Samples Added |
|--------|--------------|
| Probe | 12,320 |
| R2L | 6,760 |
| U2R | 620 |

🧹 Outliers Removed: **3,128 (1.00%)**  
Outlier distribution (major classes only):

| Class | Count |
|--------|------|
| Probe | 1229 |
| Normal | 1196 |
| R2L | 375 |
| DoS | 259 |
| U2R | 69 |

---

## 🏆 Model Performance (Final Results)

### 📌 Enhanced Classification Report
| Class | Precision | Recall | F1-Score | Support |
|-------|-----------|--------|---------|---------|
| DoS | 1.0000 | 0.9999 | 0.9999 | 156,584 |
| Normal | 0.9984 | 0.9997 | 0.9990 | 38,911 |
| Probe | 0.9994 | 0.9897 | 0.9945 | 1,643 |
| R2L | 0.9906 | 0.9378 | 0.9635 | 450 |
| U2R | 0.7143 | 0.7143 | 0.7143 | 21 |

**Overall Accuracy:** `99.96%`  
**Macro Average F1-Score:** `93.42%`  
**Weighted F1-Score:** `99.96%`

---

## 📈 Visualizations
✔ Attack category distribution across Train/Test  
✔ Overall dataset pie chart  
✔ Imbalance analysis charts  

> All plots are generated automatically during execution.

---

## 🏗️ Folder Structure (Recommended)

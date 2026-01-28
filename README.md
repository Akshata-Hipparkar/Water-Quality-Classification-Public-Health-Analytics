# DS02: Water Quality Classification & Public Health Analytics

## 📌 Project Overview
Access to clean and safe water is a critical public health requirement. Manual monitoring of water quality is time-consuming and often inconsistent across regions. This project uses **machine learning** to automatically classify water bodies in Maharashtra into **water quality classes (A, B, C, E)** based on physicochemical and biological parameters.

The project follows a complete data science workflow including **EDA, preprocessing, feature selection, handling class imbalance, model training, evaluation, and interpretation of results**.

---

## 🎯 Project Objectives
- Perform exploratory data analysis (EDA) on real-world environmental data  
- Clean and preprocess water quality data  
- Handle missing values and class imbalance  
- Build and evaluate multiclass classification models  
- Identify key water quality indicators affecting classification  
- Generate insights relevant to **public health and water resource management**

---

## 📊 Dataset Information
- **Source:** National Water Monitoring Programme (NWMP), Maharashtra Pollution Control Board (MPCB)
- **File:** `NWMP_August2025_MPCB_0.csv`
- **Size:** ~225 rows × 54 columns
- **Target Variable:** `Use Based Class`

### Water Quality Classes
| Class | Description |
|------|------------|
| A | Drinking water source (after disinfection) |
| B | Outdoor bathing (organized) |
| C | Drinking water source (conventional treatment required) |
| E | Irrigation, industrial cooling, controlled waste |

---

## 🔬 Key Features Used
- **pH** – Acidity/alkalinity of water  
- **DO (Dissolved Oxygen)** – Oxygen availability for aquatic life  
- **BOD (Biochemical Oxygen Demand)** – Organic pollution indicator  
- **COD (Chemical Oxygen Demand)** – Total organic matter  
- **TDS (Total Dissolved Solids)** – Mineral content  
- **Temperature** – Affects oxygen solubility and biological activity  

---

## 🧹 Data Preprocessing
The following preprocessing steps were applied:

- Removed irrelevant and identifier columns (station details, administrative fields)
- Removed rows with undefined target class (`No Information`)
- Dropped non-numeric columns before modeling
- Handled missing values using **median imputation**
- Encoded target labels using **LabelEncoder**
- Standardized numeric features using **StandardScaler**

---

## 📈 Exploratory Data Analysis (EDA)
EDA included:
- Dataset structure and statistical summaries
- Missing value analysis
- Target class distribution visualization
- Feature histograms and boxplots
- Correlation heatmap
- Pairplots for key water quality parameters

EDA revealed:
- Strong class imbalance (Class A dominating)
- High correlation between pollution indicators (BOD, COD, DO)
- Presence of outliers in pollution-related features

---

## ⚖️ Handling Class Imbalance
The dataset exhibited severe class imbalance, which negatively affected minority class predictions.

**Solution applied:**
- Used **RandomOverSampler** to balance training data
- Ensured minority classes (B, C, E) were adequately learned by models

---

## 🤖 Models Implemented
Two multiclass classification models were trained and evaluated:

### 1. Logistic Regression
- Multi-class strategy: One-Vs-Rest (OVR)
- Baseline linear classifier

### 2. Random Forest Classifier
- 300 estimators
- Handles non-linear relationships
- Provides feature importance

---

## 📏 Model Evaluation
Models were evaluated using:
- Accuracy
- Precision, Recall, F1-score (per class)
- Confusion Matrix

### Results Summary
- **Random Forest outperformed Logistic Regression**
- Balanced data significantly improved minority class predictions
- Reduced bias toward Class A
- Random Forest achieved better overall generalization

---

## 🔍 Feature Importance (Random Forest)
Top influential features identified:
1. BOD (Biochemical Oxygen Demand)
2. COD (Chemical Oxygen Demand)
3. DO (Dissolved Oxygen)
4. pH
5. TDS

These features are scientifically aligned with standard water quality assessment practices.

---

## 🌍 Public Health & Environmental Impact
- Enables automated and scalable water quality classification
- Helps identify polluted water bodies early
- Supports decision-making for drinking water safety and irrigation
- Assists pollution control authorities in prioritizing monitoring efforts

---

## 🧪 Technologies & Libraries Used
- Python
- pandas, numpy
- matplotlib, seaborn
- scikit-learn
- imbalanced-learn (RandomOverSampler)

---

---

## ✅ Conclusion
This project successfully demonstrates the application of machine learning to environmental and public health data. By combining robust preprocessing, imbalance handling, and ensemble modeling, the system accurately classifies water quality into regulatory classes, providing actionable insights for sustainable water management.

---

## 📌 Future Enhancements
- Add data from multiple months for temporal analysis
- Try advanced models (XGBoost, LightGBM)
- Deploy a Streamlit dashboard for real-time predictions
- Integrate GIS mapping for spatial visualization

---

## 📚 References
- National Water Monitoring Programme (NWMP): https://data.gov.in/
- Maharashtra Pollution Control Board (MPCB)



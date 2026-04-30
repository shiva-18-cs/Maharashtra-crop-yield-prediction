# 🌾 Maharashtra Crop Yield Prediction

A complete Machine Learning pipeline to predict crop yield (kg/hectare) 
across Maharashtra districts using real data from the DiCRA Government API.

---

## 📌 Problem Statement
Predicting agricultural crop yield is critical for food security and 
farmer planning. This project builds an ML model that predicts yield 
based on environmental and agricultural features.

---

## 📊 Dataset
- **Source:** DiCRA API (Government of India)
- **Records:** 5,544
- **Districts:** 33 Maharashtra districts
- **Crops:** Rice, Wheat, Sugarcane, Cotton, Soybean, Jowar, Bajra
- **Years:** 2000–2023

---

## 🔧 Features Used
- District, Crop Type, Year
- NDVI (Vegetation Index)
- Rainfall (mm), Temperature (°C), Soil Moisture
- Area (Hectares)
- Engineered: NDVI × Rainfall, NDVI × Soil Moisture, Rainfall/Temp

---

## 🤖 Models Trained
| Model | Test R² | RMSE |
|---|---|---|
| Linear Regression | 0.35 | 2227 kg/ha |
| Random Forest | 0.9879 | 305 kg/ha |
| **Gradient Boosting** ✅ | **0.9885** | **296 kg/ha** |

**Best Model:** Gradient Boosting with **98.85% R² score**

---

## 🛠️ Tech Stack
- Python, Pandas, NumPy
- Scikit-learn (Random Forest, Gradient Boosting)
- Matplotlib, Seaborn
- Joblib (model saving)
- DiCRA REST API

---

## 📁 Project Structure
```
├── Maharashtra_Crop_Yield.ipynb  # Main notebook
├── models/
│   ├── best_model.pkl            # Gradient Boosting model
│   ├── random_forest_model.pkl
│   └── model_metadata.json
├── predict.py                    # Ready-to-use prediction script
└── README.md
```

---

## 🚀 How to Run
```bash
git clone https://github.com/shiva-18-cs/maharashtra-crop-yield
cd maharashtra-crop-yield
pip install pandas numpy scikit-learn matplotlib seaborn xgboost lightgbm joblib
jupyter notebook Maharashtra_Crop_Yield.ipynb
```

---

## 🎯 Sample Prediction
```python
predict_crop_yield(
    district='Pune',
    crop='Rice',
    year=2024,
    ndvi=0.6,
    rainfall=850,
    temperature=28,
    soil_moisture=0.4,
    area=100
)
```
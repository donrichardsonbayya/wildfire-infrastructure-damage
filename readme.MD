# Linking Wildfire Risk with Infrastructure Damage  
**Business Challenge II – MBAN Program**

This project investigates the link between wildfire intensity (via Fire Weather Index - FWI) and resulting infrastructure damage across five high-risk European countries: **Portugal, Spain, France, Italy, and Greece**. It combines **dynamic data engineering, geospatial analysis, and machine learning** to support proactive disaster planning.

---

##  Summary of Business Problem

As climate events grow in frequency and severity, governments and insurers must better understand the drivers of infrastructure damage from wildfires. Using wildfire data from 2012–2024, this study examines how **climate risk metrics like FWI** correlate with infrastructure vulnerability and damage severity.

---

##  Key Features

### 🔄 Dynamic Data Engineering
- Programmatically constructs web URLs to **automatically download event-level wildfire data** by country and year (no static datasets required).
- Cleans and structures multiple JSON/CSV sources into a unified, analysis-ready format.

###  Geospatial Analysis with Shapefiles
- Leverages country-level **shapefiles** to map infrastructure, wildfire zones, and **WUI (Wildland-Urban Interface)** labels.
- Performs spatial joins to assess **infrastructure type** (`obj_type`) and exposure to fire-prone areas.

### Predictive Modeling & EDA
- Investigates patterns in **damage_grade vs. FWI** with box plots and correlation analysis.
- Trains:
  - **Logistic Regression**: for binary classification of severe vs. low/no damage.
  - **Random Forest**: to improve accuracy and handle nonlinearity.
- Visualizes `obj_type` and `wui_label` distribution to identify high-risk infrastructures.

---

##  Business Insights (from Final Report)

- **FWI is a strong predictor** of higher infrastructure damage grades (Grades 3–5).
- The most vulnerable object types include:
  - Power grid stations
  - Transportation hubs
  - Telecommunication nodes
- France shows **higher correlation** between fire risk and severe damage than other countries.
- Including **WUI classification** improves geographic targeting of high-risk zones.
- The Random Forest model outperforms logistic regression in **predictive performance**.

---

##  Stakeholder Recommendations

- Public authorities should **integrate climate indicators (FWI)** into infrastructure resilience planning.
- Focus fire prevention funding on **WUI-adjacent critical infrastructure**.
- Use model insights to inform **early warning systems** and **insurance pricing**.

---

##  Project Structure

wildfire-infrastructure-risk/
├── notebooks/
│ └── wildfire_risk_model.ipynb # Full analysis and model pipeline
├── visuals/
│ └── charts and exported plots # EDA and model result images
├── README.md
├── requirements.txt
└── .gitignore


---

##  Technologies Used

- **Python**: `pandas`, `geopandas`, `matplotlib`, `seaborn`, `scikit-learn`, `requests`
- **Dynamic ingestion**: programmatically pulls JSON/CSV from structured URLs
- **GIS**: shapefile integration, spatial joins, and region-wise fire mapping
- **Machine Learning**: binary classification (logistic regression & random forest)

---

##  Data Notes

- No static CSVs — all data is **downloaded dynamically** via parameterized URL templates.
- **Shapefiles** are essential for mapping infrastructure to WUI zones and country boundaries.
- Data spans **2012–2024**, including over **100,000+ infrastructure entries**.

---

##  How to Run

1. Clone this repo
2. Open the notebook in `notebooks/wildfire_risk_model.ipynb`
3. Run all cells — required data will download automatically
4. Output charts and model metrics will appear in-line or in `visuals/`

---

## 👤 Author

**Don Richardson Bayya**  

---


# 🏡 Predictive Insight Engine
### House Price Prediction using Machine Learning

<p align="center">
  <strong>📊 Explore real-estate data · 🤖 Train regression models · 📈 Evaluate predictions</strong>
</p>

<p align="center">
  <img alt="Python" src="https://img.shields.io/badge/Python-3.9%2B-3776AB?logo=python&logoColor=white">
  <img alt="Pandas" src="https://img.shields.io/badge/Pandas-Data%20Analysis-150458?logo=pandas&logoColor=white">
  <img alt="Scikit--learn" src="https://img.shields.io/badge/scikit--learn-Regression-F7931E?logo=scikitlearn&logoColor=white">
  <img alt="Jupyter" src="https://img.shields.io/badge/Jupyter-Notebook-F37626?logo=jupyter&logoColor=white">
  <img alt="Status" src="https://img.shields.io/badge/Project-Educational%20%7C%20ML-blue">
</p>

---

## 🌟 Overview

**Predictive Insight Engine** is a machine-learning project that explores house-price prediction using a real-estate dataset. It loads and inspects housing data, selects relevant property features, trains regression models, and compares their performance using common evaluation metrics.

The project is implemented in a Jupyter Notebook and demonstrates a practical end-to-end regression workflow—from data loading and train/test splitting to model evaluation and visual analysis.

> 🎯 **Primary objective:** predict `house_price_inr` from property characteristics and compare different regression approaches.

## ✨ Key Features

- 🧾 **Dataset inspection** — preview records, check dataset dimensions, and inspect missing-value counts.
- 🏠 **Property feature selection** — use property size, rooms, location score, age, distance, lot size, amenities, and renovation information.
- 📏 **Simple Linear Regression** — model the relationship between floor area and house price.
- 🧠 **Multiple Linear Regression** — use multiple property attributes to predict price.
- 🌀 **Polynomial Regression** — explore a degree-2 relationship between floor area and price.
- ⚙️ **Gradient Descent from scratch** — implement a basic one-feature optimization loop with scaled values.
- 📊 **Model evaluation** — calculate MSE, MAE, RMSE, R², and Adjusted R².
- 📉 **Visual analysis** — plot actual versus predicted prices and a gradient-descent learning curve.
- 🔍 **Model comparison** — compare model metrics on the same held-out test split.

## 🧰 Tech Stack

| Technology | Purpose |
|---|---|
| 🐍 Python | Core programming language |
| 🧮 NumPy | Numerical operations and gradient-descent calculations |
| 🐼 Pandas | Tabular data loading and manipulation |
| 📊 Matplotlib | Charts and visual analysis |
| 🤖 scikit-learn | Train/test split, regression models, polynomial features, evaluation metrics |
| 📓 Jupyter Notebook | Interactive execution and experimentation |
| 📁 Excel (`.xlsx`) | Source dataset |

## 📂 Project Structure

```text
Predictive-Insight-Engine/
├── Predictive_Insight_Engine.ipynb
├── RealEstate_HousePrice_Dataset_4200.xlsx
└── README.md
```

Keep the notebook and Excel dataset in the same directory unless you update the dataset path in the notebook.

## 🗃️ Dataset Details

The supplied Excel dataset contains **4,200 rows and 12 columns**.

### Target variable 🎯

| Column | Description |
|---|---|
| `house_price_inr` | House price in Indian rupees (INR); the value the models aim to predict |

### Input columns 🏘️

| Column | Description |
|---|---|
| `area_sqft` | House area in square feet |
| `bedrooms` | Number of bedrooms |
| `bathrooms` | Number of bathrooms |
| `location_score` | Numeric score representing location |
| `age_years` | Property age in years |
| `distance_city_km` | Distance from the city in kilometres |
| `lot_size_sqft` | Lot size in square feet |
| `has_garage` | Garage indicator (0/1 in the supplied sample) |
| `has_pool` | Pool indicator (0/1 in the supplied sample) |
| `renovation_years_ago` | Years since renovation, as represented in the dataset |
| `house_id` | Record identifier; not included in the model feature list |

The notebook selects 10 input features and uses `house_price_inr` as the target. The dataset's actual data definitions should be checked before using the predictions for real-world decisions.

## 🧪 Models Implemented

### 1. 📏 Simple Linear Regression
Uses only `area_sqft` to predict house price. The notebook prints the fitted slope and intercept and plots the test observations with a regression line.

### 2. 🧠 Multiple Linear Regression
Uses all 10 selected property features. It also plots actual prices against predicted prices to help visually inspect prediction quality.

### 3. 🌀 Polynomial Regression (Degree 2)
Transforms `area_sqft` into degree-2 polynomial features and fits a linear regression estimator to explore a curved relationship. This model uses area only, not all 10 features.

### 4. ⚙️ Gradient Descent from Scratch
Implements a basic gradient-descent loop for an area-only model. The training area and price values are standardized using training-set statistics, then the model is optimized over 1,000 epochs with a learning rate of `0.01`. A loss-history plot shows the scaled mean-squared error recorded during training.

## 📐 Evaluation Metrics

The notebook reports these metrics for each model:

| Metric | What it tells you | Preferred direction |
|---|---|---|
| **MSE** — Mean Squared Error | Average squared prediction error | Lower |
| **MAE** — Mean Absolute Error | Average absolute prediction error, in target units | Lower |
| **RMSE** — Root Mean Squared Error | Error scale in target units; penalizes large errors more than MAE | Lower |
| **R² Score** | Proportion of target variation explained by the model, relative to a mean baseline | Usually higher |
| **Adjusted R²** | R² adjusted for the number of predictors and sample size | Usually higher |

📌 **Interpretation tip:** compare RMSE and R² together, and consider the intended use and data quality. Metrics alone do not establish that a model is suitable for property valuation.

## 🚀 Getting Started

### Prerequisites

Install Python and Jupyter Notebook/JupyterLab. Python 3.9 or newer is a reasonable starting point; use package versions compatible with your environment.

### 1. Clone or download the project

If you place the files in a Git repository, clone it:

```bash
git clone <your-repository-url>
cd <your-project-folder>
```

Or simply download the notebook and dataset into one folder.

### 2. Create and activate a virtual environment (recommended)

**Windows (PowerShell):**
```powershell
python -m venv .venv
.\.venv\Scripts\Activate.ps1
```

**macOS / Linux:**
```bash
python3 -m venv .venv
source .venv/bin/activate
```

### 3. Install dependencies

```bash
python -m pip install pandas numpy matplotlib scikit-learn openpyxl jupyter
```

`openpyxl` allows Pandas to read the Excel `.xlsx` file.

### 4. Launch Jupyter

```bash
jupyter notebook
```

Open `Predictive_Insight_Engine.ipynb` in the browser.

### 5. Run the notebook ▶️

Run the cells **from top to bottom**. The notebook reads the Excel file using:

```python
data = pd.read_excel("RealEstate_HousePrice_Dataset_4200.xlsx")
```

If your dataset is stored elsewhere, update this path accordingly. Ensure the Excel file is available before running the first code cell.

## 🔬 Workflow at a Glance

```text
📁 Load Excel dataset
        ↓
🔎 Inspect rows, shape, and missing values
        ↓
🎯 Select 10 features and target price
        ↓
✂️ Split data: 80% train / 20% test
        ↓
🤖 Train regression approaches
        ↓
📊 Evaluate predictions with error metrics
        ↓
📈 Visualize and compare model performance
```

The train/test split uses `test_size=0.20` and `random_state=42` for repeatable splitting.

## 📊 Results and Reproducibility

The notebook calculates results when its cells are executed. **No fixed performance scores are stated here**, because the results should be generated from the supplied dataset in your own environment.

For a fair comparison:
- Use the same test set when comparing models, as the notebook currently does.
- Review the printed metrics and charts rather than relying on a single score.
- Remember that the polynomial and gradient-descent implementations use only `area_sqft`, while multiple linear regression uses 10 features.
- Check data quality and model assumptions before drawing conclusions.

## ⚠️ Current Scope & Limitations

This repository is a learning and experimentation project, not a production valuation service.

- 🧪 The notebook checks missing-value counts but does not implement a complete data-cleaning pipeline.
- 📏 The models are basic regression baselines; the notebook does not include cross-validation or hyperparameter search.
- 🏙️ The dataset's location score and other fields may not capture all factors affecting real property prices.
- 🔎 The gradient-descent implementation is a one-feature demonstration, not a multi-feature model.
- 📦 The notebook does not currently provide a deployed web app, API, or command-line prediction interface.
- 🛡️ Predictions should not be treated as financial, investment, or official property-valuation advice.

## 🛠️ Possible Future Improvements

- ✅ Add robust missing-value and outlier handling.
- 📊 Add residual plots and richer exploratory data analysis.
- 🔁 Add cross-validation and compare against tree-based regressors.
- 🧪 Add automated tests and a reproducible dependency file such as `requirements.txt`.
- 💾 Save trained models and add a reusable prediction function.
- 🌐 Build a simple Streamlit or Flask interface for entering property details.
- 📦 Add a documented prediction API and model-version tracking.
- 🧭 Investigate feature importance and model interpretability.
- 📉 Check for data leakage, unusual values, and generalization on unseen data.

## 🤝 Contributing

Ideas, bug reports, and improvements are welcome. If you extend the project, keep the notebook reproducible, document new dependencies, and explain changes to the modeling workflow.

1. Fork the repository.
2. Create a feature branch.
3. Make and test your changes.
4. Submit a pull request with a clear summary.

## 📜 License

No license is specified in the supplied project files. Add a `LICENSE` file before redistributing the project if you want to define permissions and conditions for reuse.

## 👨‍💻 Author

**Indrajeet Maheshwari**

*Predictive Insight Engine — House Price Prediction*

---

<p align="center">
  💡 <em>Turning real-estate data into predictive insights, one model at a time.</em> 🏡
</p>

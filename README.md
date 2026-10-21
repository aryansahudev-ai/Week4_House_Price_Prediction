# House Price Prediction Using Linear Regression

## Project Overview
This project is an end-to-end machine learning application that predicts an estimated house price from property details. It uses a Linear Regression model trained on a house price dataset and provides a simple web interface built with Streamlit so users can enter property information and receive a prediction.

This project was developed as the **Week 4 — Final AI/ML Project** for the four-week AI/ML internship plan.

## Problem Statement
Estimating a house price can depend on several property characteristics, including its size, number of bedrooms and bathrooms, year of construction, garage size, lot size, and neighborhood quality. This project uses these features to estimate a house price with a supervised regression model.

## Objectives
- Load and explore the house price dataset.
- Check data types, missing values, duplicate rows, and potential outliers.
- Clean and preprocess the data.
- Explore distributions and relationships using visualizations and correlation analysis.
- Scale the input features and train a Linear Regression model.
- Evaluate model performance using R-squared and adjusted R-squared.
- Save the trained model and scaler for reuse.
- Provide a deployed Streamlit interface for interactive predictions.

## Dataset Source
The dataset was obtained from Kaggle:

**Home Value Insights**  
https://www.kaggle.com/datasets/prokshitha/home-value-insights

The project dataset file is `house_price_prediction.csv`. It contains **1,000 rows and 8 columns**.

### Dataset Features

| Column | Description |
|---|---|
| `Square_Footage` | House area in square feet |
| `Num_Bedrooms` | Number of bedrooms |
| `Num_Bathrooms` | Number of bathrooms |
| `Year_Built` | Year the house was built |
| `Lot_Size` | Size of the lot |
| `Garage_Size` | Garage size value recorded in the dataset |
| `Neighborhood_Quality` | Neighborhood quality score |
| `House_Price` | Target value used to train the model |

Please refer to the Kaggle dataset page for the original dataset description, licensing, and usage conditions.

## Technologies and Libraries
- **Python** — programming language.
- **Pandas** — dataset loading, cleaning, and tabular data processing.
- **NumPy** — numerical operations.
- **Matplotlib** and **Seaborn** — data visualization.
- **Scikit-learn** — feature scaling, train-test splitting, Linear Regression, and evaluation.
- **SciPy** — Pearson correlation calculations.
- **Joblib** — saving and loading the trained model and scaler.
- **Jupyter Notebook** — model development and analysis.
- **Streamlit** — interactive prediction interface.

## Project Workflow
1. Load `house_price_prediction.csv` using Pandas.
2. Inspect the dataset shape, column data types, descriptive statistics, missing values, and duplicate rows.
3. Clean invalid numeric values and fill missing feature values using the median; inspect the cleaning results.
4. Use boxplots and the interquartile range (IQR) method to examine potential outliers.
5. Create histograms, a correlation heatmap, and a scatter plot comparing square footage with house price.
6. Calculate Pearson correlations to examine the relationship between selected features and the target.
7. Apply `StandardScaler` to the seven input features.
8. Split the data into training and testing sets using an 80:20 split with `random_state=42`.
9. Train a `LinearRegression` model using the training data.
10. Generate predictions for the test set and evaluate the model.
11. Save the trained model as `house_price_model.pkl` and the scaler as `house_price_scaler.pkl`.
12. Use the Streamlit application (`app.py`) to collect property details, apply the saved scaler, and display the predicted price.

## Model Evaluation
The notebook reports the following results on the test set:

| Evaluation Metric | Result |
|---|---:|
| R-squared (R²) | 0.998426 |
| Adjusted R-squared | 0.998369 |

The R-squared score is approximately **99.84%** on this test split. This indicates that the model explains a high proportion of the variation in house prices in the test data. These results are specific to this dataset and split and do not guarantee similar performance on new or real-world housing data.

## Deployed Prediction Application
The Streamlit application allows users to enter:
- Square footage
- Number of bedrooms
- Number of bathrooms
- Year built
- Garage size
- Lot size
- Neighborhood quality

After the user selects **Predict House Price**, the application scales the inputs, arranges them in the expected feature order, and displays the model's estimated house price.

**Live Demo:** https://aryansahu-house-price-prediction.streamlit.app/

## Run the Project Locally
1. Clone or download this project repository.
2. Make sure the following files are available in the same working directory:
   - `app.py`
   - `house_price_prediction.csv`
   - `house_price_model.pkl`
   - `house_price_scaler.pkl`
3. Install the required libraries:

   ```bash
   pip install streamlit pandas scikit-learn joblib
   ```

   For running the notebook and its analysis, you may also need:

   ```bash
   pip install numpy matplotlib seaborn scipy jupyter
   ```

4. Start the Streamlit application:

   ```bash
   streamlit run app.py
   ```

5. Open the local URL printed by Streamlit in your browser.

> The model and scaler files must be available before launching the app because `app.py` loads them at startup.

## Project Files
- `Project.ipynb` — data exploration, cleaning, visualization, preprocessing, training, and evaluation.
- `app.py` — Streamlit application for interactive house price prediction.
- `house_price_prediction.csv` — dataset used for the project.
- `house_price_model.pkl` — saved Linear Regression model.
- `house_price_scaler.pkl` — saved feature scaler.
- `README.md` — project documentation.

## Limitations and Future Improvements
- Test the model on additional data from different locations and time periods.
- Compare Linear Regression with other regression algorithms.
- Evaluate additional metrics such as MAE, MSE, and RMSE.
- Improve validation with cross-validation and checks for data leakage.
- Add clearer descriptions and units for dataset features.
- Add input validation and more informative error handling to the web application.
- Include screenshots and the actual deployment URL in the repository.

## Conclusion
This Week 4 project demonstrates an end-to-end machine learning workflow, from dataset inspection and preprocessing to regression model training, evaluation, and deployment through Streamlit. The application provides an accessible interface for experimenting with house details and viewing model-generated price estimates. Predictions are estimates only and should not be treated as guaranteed market values.

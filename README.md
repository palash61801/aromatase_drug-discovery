# An Exploratory Data Analysis and Machine Learning Approach to Drug Discovery

This repository contains an end-to-end approach to drug discovery using exploratory data analysis (EDA) and machine learning (ML) techniques. The project aims to identify molecules with potential inhibitory effects on aromatase, an enzyme involved in estrogen production, by analyzing molecular properties and applying predictive modeling.

## Project Structure

- **`source code.ipynb`**: Jupyter Notebook containing both the EDA and ML components. This file covers molecular property analysis, Lipinski’s rule of five, ChEMBL database integration, IC50 to pIC50 conversion, and machine learning models for predicting molecule effectiveness.

## Project Workflow

This project is organized into two main parts:

### 1. Exploratory Data Analysis (EDA)

The EDA section focuses on understanding molecular activity and properties, including:
- **Lipinski's Rule of Five**: Filters molecules based on drug-likeness criteria.
- **ChEMBL Database**: Integrates with ChEMBL to obtain biochemical and structural information.
- **IC50 to pIC50 Conversion**: Standardizes inhibitory concentration (IC50) data for consistency in model input.

### 2. Machine Learning Modeling

This section applies machine learning techniques to predict the effectiveness of molecules as potential drugs. The notebook includes:
- **Random Forest Regressor**: Predicts molecular activity based on structural features.
- **Support Vector Regressor**: Offers an alternative regression approach for molecule activity prediction.

## Requirements

To install the necessary packages, run:

```bash
pip install -r requirements.txt
```

## Usage

1. **Run the Jupyter Notebook**: Open `source code.ipynb` to start the analysis and modeling process.

   ```bash
   jupyter notebook "source code.ipynb"
   ```

2. **Steps in the Notebook**:
   - Load and preprocess molecule data.
   - Conduct EDA to filter molecules based on Lipinski’s rule and calculate pIC50 values.
   - Apply machine learning models to predict molecular efficacy and identify promising candidates.

## Example

Here’s an example of using a Random Forest Regressor on molecular data:

```python
from sklearn.ensemble import RandomForestRegressor
from sklearn.model_selection import train_test_split

# Load molecular dataset
X = dataset[['feature1', 'feature2', 'feature3']]
y = dataset['pIC50']

# Split data
X_train, X_test, y_train, y_test = train_test_split(X, y, test_size=0.2, random_state=42)

# Train Random Forest model
rf_model = RandomForestRegressor()
rf_model.fit(X_train, y_train)

# Make predictions
predictions = rf_model.predict(X_test)
```

## Results

The output of this project includes both visual and quantitative insights into molecule activity, filtered by Lipinski's rule. The predictive models identify promising molecules that can be further explored for potential drug development.

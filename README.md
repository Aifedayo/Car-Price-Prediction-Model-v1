# Car Price Prediction Model v1

## Overview
This project is designed to predict the prices of used cars based on various features using machine learning models. With the rise in the used car market, predicting accurate car prices is crucial for both buyers and sellers. The project uses historical data on car sales to train a predictive model that can estimate the price of a car based on its attributes like brand, model, production year, mileage, and more.

The backend is built with Python, utilizing machine learning libraries like scikit-learn and pandas for data manipulation, feature engineering, and model building.

## Case Study
The used car market presents several challenges in price estimation due to the variety of factors influencing a car’s value, including make, model, mileage, condition, and more. In this case study, we examine the following:

- **Data Acquisition**: The dataset contains information on various cars sold, including their make, model, year, and other relevant features.
- **Data Preprocessing**: Handling missing values, encoding categorical data (such as car brands), and normalizing numerical features.
- **Model Selection**: Various regression models were tested, including Linear Regression, Random Forest, and XGBoost, to determine the best approach for predicting car prices.
- **Model Evaluation**: The models were evaluated based on their predictive performance using metrics like RMSE (Root Mean Squared Error) and R-squared.

The case study aims to highlight the importance of data-driven decision-making in the used car market and how machine learning models can assist in predicting accurate prices.

## Solution
The solution provides a complete pipeline for car price prediction:

1. **Data Collection and Cleaning**: The data is cleaned by removing missing values and outliers. Features are encoded, and numerical values are normalized or scaled.
   
2. **Model Training**: Different regression models (such as Linear Regression, Random Forest, and XGBoost) are trained on the dataset. After testing several models, the one with the best performance is selected for deployment.

3. **Car Price Prediction API**: A Flask-based API serves the trained model, allowing users to send car details via POST requests and receive a predicted price in return.

### Features:
- **Make and Model Encoding**: Car brands and models are encoded into numerical values.
- **Numerical Feature Scaling**: Features like mileage, engine size, and year are scaled for better model performance.
- **REST API**: The Flask API allows users to interact with the model by sending a request with car features and receiving a predicted price.
  
## How to Test

### 1. Clone the Repository
To get started, clone the repository:
```bash
git clone https://github.com/Aifedayo/Car-Price-Prediction-Model-v1.git
cd Car-Price-Prediction-Model-v1
```

### 2. Set Up a Virtual Environment
It's recommended to create a virtual environment to isolate dependencies.
```bash
python3 -m venv venv
source venv/bin/activate  # On Windows, use `venv\Scripts\activate`
```

### 3. Install Dependencies
Install the necessary Python libraries using the `requirements.txt` file:
```bash
pip install -r requirements.txt
```

### 4. Train the Model
You can retrain the model by running the training script. This script preprocesses the data and trains the model using the dataset provided in the project.
```bash
python train_model.py
```

### 5. Run the Flask Server
Once the model is trained, start the Flask server to serve the predictions:
```bash
python app.py
```

The server will run locally at `http://127.0.0.1:5000/`. You can use a web browser or Postman to interact with the API.

### 6. Test the API
You can use `curl` or Postman to test the API by sending a POST request with car details. Here’s an example using `curl`:
```bash
curl -X POST http://127.0.0.1:5000/predict \
  -H "Content-Type: application/json" \
  -d '{"make": "Toyota", "model": "Camry", "year": 2015, "mileage": 60000, "engine_size": 2.5, "fuel_type": "Gasoline", "transmission": "Automatic"}'
```

This will return a predicted price based on the provided input.

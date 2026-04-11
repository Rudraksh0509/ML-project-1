# Student Exam Performance Indicator

An end-to-end Machine Learning project that predicts a student's mathematics score based on various demographic data, test preparation strategies, and partial academic history (reading and writing scores).

## Project Overview

This project implements a complete Machine Learning pipeline, providing modular, production-ready components to scrape, clean, process, and model data. The backend is served using a **Flask API**, while the frontend features a sleek, responsive, glassmorphism UI for seamless user interaction.

### Key Features
- **Data Ingestion**: Automated data ingestion and train-test splits.
- **Data Transformation**: Complete feature engineering pipeline handling imputation, scaling (StandardScaler), and encoding (OneHotEncoder) for both numeric and categorical features.
- **Model Training**: Evaluates multiple state-of-the-art algorithms (including Random Forest, Decision Trees, CatBoost, and XGBoost) using GridSearchCV to select and save the best-performing model.
- **Web Interface**: A premium dark-mode, glassmorphism web UI where users can input student metrics and receive instant model predictions.

## Project Structure

```text
├── artifacts/                  # Pickled models, preprocessors, and raw/split datasets
├── notebook/                   # Jupyter notebooks (EDA and Model experimentation)
├── src/
│   ├── components/             # Core ML pipeline modules
│   │   ├── data_ingestion.py     # Reads data and prepares train/test sets
│   │   ├── data_transformation.py# Pipeline for feature scaling/encoding
│   │   └── model_trainer.py      # Tunes and trains the best machine learning models
│   ├── pipeline/               # Orchestrates predictions and custom data objects
│   │   └── predict_pipeline.py   # Uses saved models to generate predictions
│   ├── logger.py               # Custom logging handler
│   ├── exception.py            # Custom exception handling
│   └── utils.py                # Helper functions for saving/loading objects & evaluation
├── templates/                  # Frontend HTML templates
│   ├── index.html                # App landing page
│   └── home.html                 # Main prediction dashboard 
├── application.py              # Flask backend server application
├── requirements.txt            # Project dependencies
└── setup.py                    # Project setuptools configuration
```

## Setup & Installation

**1. Clone the repository**
```bash
git clone https://github.com/your-username/mlproject.git
cd mlproject
```

**2. Create and activate a Virtual Environment**
Using base Python `venv`:
```bash
python -m venv venv
# On Windows:
venv\Scripts\activate
# On Mac/Linux:
source venv/bin/activate
```

**3. Install Dependencies**
```bash
pip install -r requirements.txt
```

## Usage

**Running the Web App**

To start the Flask server and access the interactive frontend UI:
```bash
python application.py
```
Open a browser and navigate to `http://localhost:5000/`.

**Retraining the Model**

If you update the dataset or want to retrain the ML components, simply run the data ingestion module:
```bash
python -m src.components.data_ingestion
```
*This will orchestrate the transformation and training sequences, successfully overwriting the existing models in the `artifacts/` folder with updated ones.*

## Technologies Used
- **Python 3**
- **Scikit-Learn, Pandas, Numpy**
- **CatBoost & XGBoost**
- **Flask**
- **HTML5 & CSS3**
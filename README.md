### Network Security MLOps Project
An end-to-end MLOps pipeline for Network Intrusion Detection using machine learning. This project leverages MLflow, FastAPI, DVC, and DagsHub to automate training, tracking, and deployment of classification models for detecting malicious network activity.
### Project Structure
mlopsproject/
├── app.py                          # FastAPI app entry point
├── main.py                         # CLI training interface
├── config/                         # Configuration files
├── networksecurity/               # Core pipeline components
│   ├── components/                 # Data ingestion, transformation, training, etc.
│   ├── entity/                     # Custom data classes (e.g., artifacts, configs)
│   ├── exception/                  # Custom exception class
│   ├── logger/                     # Logging setup
│   ├── pipeline/                   # Orchestration layer for training/inference
├── artifacts/                      # Outputs (saved models, metrics, etc.)
├── logs/                           # Logging output
├── notebooks/                      # EDA, development notebooks
└── requirements.txt                # Python dependencies
### Features 
. Modular pipeline with custom components

. FastAPI interface for triggering training

. MLflow integration for tracking models and metrics

. Supports multiple classifiers with evaluation metrics

. DVC (Data Version Control) ready

. Deployed and tracked via DagsHub
### Getting Started
1. Clone the repository
git clone https://github.com/ahmed95059/mlopsproject.git
cd mlopsproject
2. Create & activate a virtual environment
python -m venv venv
venv\Scripts\activate     # on Windows
# source venv/bin/activate # on Linux/macOS
3. Install dependencies
pip install -r requirements.txt
### Run the Training Pipeline
You can run training using:
    python main.py
Or trigger it via the FastAPI web app:
    uvicorn app:app --reload
Then navigate to: http://127.0.0.1:8000/train
### MLflow + DagsHub
MLflow tracking is configured to log runs and artifacts to DagsHub.

Example run URL:https://dagshub.com/ahmed95059/mlopsproject.mlflow/#/experiments/0
### Evaluation
Models are evaluated using:

. Accuracy

. Precision / Recall

. F1-score

. ROC-AUC

The best model is saved under artifacts/model.
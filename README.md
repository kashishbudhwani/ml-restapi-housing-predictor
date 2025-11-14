# ml-restapi-housing-predictor
A robust Python project demonstrating the deployment of a scikit-learn model (California Housing price predictor) as an accessible and documented REST API using FastAPI. End-to-end example of building a machine learning microservice: training the model, saving it with joblib, and serving predictions via a high-performance FastAPI endpoint.


FastAPI ML Model Deployment: Housing Price Predictor robust, end-to-end Python project demonstrating how to deploy a trained Machine Learning model as a fast, accessible, and documented REST API using FastAPI and scikit-learn.

Project OverviewThis repository contains the necessary scripts to:Train a Random Forest Regressor model using the California Housing dataset. Serialize and save the trained model using joblib. Load the saved model into a FastAPI application. Expose a /predict endpoint to receive house feature inputs and return a predicted median house value.

Getting StartedFollow these steps to set up and run the API on your local machine.
Prerequisites
You need Python 3.8+ installed.
1. Clone the RepositoryBashgit clone https://github.com/YourUsername/fastapi-ml-deployment-housing.git
cd fastapi-ml-deployment-housing

2. Set up the EnvironmentCreate a virtual environment (recommended) and install the dependencies: Bash# Create and activate environment (Linux/macOS)
python -m venv venv
source venv/bin/activate

# Install required libraries
pip install -r requirements.txt

3. Train the ModelYou must train the model and save the .joblib file before running the API. Bash python train.py
This script will output a file named california_housing_model.joblib.

Running the API ServerStart the FastAPI server using uvicorn. The --reload flag is useful for development.
Bash uvicorn main: app --reload
The server will start 

API Endpoints & Documentation: FastAPI automatically generates interactive documentation for testing and exploration. 
Interactive Documentation (Swagger UI) https://heated-usb-compile-preliminary.trycloudflare.com/docs

Health CheckMethodEndpointDescriptionGET/Returns a welcome message (API status check).
Prediction EndpointMethodEndpointDescriptionPOST/predictPredicts the median house value based on input features.Input Payload Example (/predict):

The API expects a JSON object matching the HouseFeatures schema:
JSON{
  "MedInc": 8.3252,
  "HouseAge": 41.0,
  "AveRooms": 6.9841,
  "AveBedrms": 1.0238,
  "Population": 322.0
}
Successful Response: JSON{
  "predicted_median_house_value": 4.526
}


![WhatsApp Image 2025-11-14 at 2 24 00 PM](https://github.com/user-attachments/assets/1159fb2d-af9c-46bb-ad52-d6d28a8d4712)
![WhatsApp Image 2025-11-14 at 2 24 55 PM](https://github.com/user-attachments/assets/55d009f9-2a4e-4a32-9570-459a0bd7d79b)
![WhatsApp Image 2025-11-14 at 2 26 14 PM](https://github.com/user-attachments/assets/a16b2855-d9c5-46fd-9680-0e6077418119)
![WhatsApp Image 2025-11-14 at 2 26 32 PM](https://github.com/user-attachments/assets/8351d413-41a4-4239-87d7-672da988bdf9)


Technology Stack: Python 3.10+, API Framework: FastAPI (for high performance and automatic documentation), Web Server: Uvicorn (ASGI server), Machine Learning: scikit-learn (RandomForestRegressor), Data Handling: Pandas, Serialization: Joblib

This project is licensed under the MIT License - see the LICENSE file for details.

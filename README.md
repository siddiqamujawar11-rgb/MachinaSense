
MachinaSense — AI-Powered Predictive Maintenance System

MachinaSense is a machine learning–powered API built to help maintenance teams catch equipment failure before it happens. It replaces manual inspection schedules and guesswork with a single service that takes live sensor readings — temperature, pressure, vibration, humidity, RPM, torque, machine age, and operating hours — and returns an instant, data-backed health prediction, with every prediction logged for later review.

Features

🔮 Real-time failure prediction from 8 live sensor and operational inputs
📊 Confidence scores for both the healthy and failure outcomes, not just a single label
🗄️ Persistent prediction history stored in PostgreSQL for audit and analysis
📖 Auto-generated interactive API docs via Swagger UI
🧩 Clean, modular architecture with routes, schemas, models, and data access kept separate
Tech Stack

Backend: Python, FastAPI, SQLAlchemy, PostgreSQL
ML / Inference: scikit-learn, joblib
Validation: Pydantic
Server: Uvicorn
Getting Started Backend

bash
cd machinasense
python -m venv venv
.\venv\Scripts\Activate.ps1   # Windows
pip install -r requirements.txt
python create_tables.py
uvicorn app:app --reload
API Once running, the API is live at http://127.0.0.1:8000, with interactive docs at http://127.0.0.1:8000/docs.

GET / — health check
POST /predict — send sensor readings, get back a prediction with healthy/failure probabilities
GET /history — retrieve every prediction made so far
Project Status Built as a predictive maintenance mini-project demonstrating an end-to-end ML inference pipeline — from a trained scikit-learn model, through a FastAPI service layer, to a persisted prediction history.

Future Scope

Authentication for API endpoints
Docker / docker-compose containerization
A monitoring dashboard for prediction trends over time
Automated model retraining pipeline with versioning



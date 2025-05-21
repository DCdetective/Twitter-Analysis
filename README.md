Twitter Sentiment Analysis & Word Frequency Dashboard 🐦📊
This project is a real-time Twitter sentiment analysis system designed to fetch tweets based on trending hashtags (like #football), analyze their sentiment, and visualize the insights on a Flask-based dashboard. The entire project follows an MLOps workflow with proper ETL structure, version control, and deployment practices using DVC, MLflow, and Docker, and hosted on AWS EC2.

🔁 Real-Time ETL Pipeline Overview
Extract:

Tweets are extracted every 10 minutes using Twikit with specific hashtags (e.g., #football, #sports, etc.).

Transform:

Preprocessing includes lowercasing, stopword removal, and emoji/URL stripping.

Sentiment analysis is applied using pre-trained models (TextBlob/VADER or custom fine-tuned models).

NLP tasks include tokenization, frequency analysis, and keyword extraction.

Load:

Cleaned and processed tweet data is loaded into MongoDB Atlas.

Word frequency and sentiment stats are persisted for dashboard access.

📊 Dashboard Features (Flask Web App)
Page 1: Sentiment Overview

Realtime classification of tweets into Positive, Negative, and Neutral sentiments.

Dynamic pie chart and sentiment trendline updated based on the latest fetch.

Page 2: Word Cloud & Tweet Highlights

Displays the most frequent terms, top liked tweets, and word clouds for trending hashtags.

🔧 Tech Stack
Language: Python

Web Framework: Flask

NLP & ML: NLTK, VADER/TextBlob, Scikit-learn

ETL & Data Handling: Twikit, Pandas

Storage: MongoDB Atlas

MLOps: MLflow, DVC, GitHub Actions

Deployment: Docker, AWS EC2

Monitoring: Prometheus + Grafana (optional for extension)

🛠 Project Structure
bash
Copy code
project-root/
│
├── src/
│   ├── data_ingestion.py
│   ├── data_preprocessing.py
│   ├── feature_engineering.py
│   ├── model_building.py
│   ├── model_evaluation.py
│   ├── logger.py
│
├── dvc.yaml
├── params.yaml
├── flask_app/
│   ├── app.py
│   ├── templates/
│   ├── static/
│
├── tests/
│
├── .github/
│   └── workflows/ci.yaml
🚀 Deployment
CI/CD configured via GitHub Actions.

Image is containerized with Docker and can be run locally or deployed on AWS EC2.

Model tracking and versioning through MLflow hosted on Dagshub.

Data versioning and pipeline tracking with DVC, using AWS S3 as remote.

✅ To-Do / Extensions
Integrate HuggingFace Transformers for advanced sentiment models

Add Prometheus & Grafana for monitoring

Add Redis for caching tweets

Deploy as a microservice using FastAPI & Kubernetes


##Network security project for phising Data
Network Security: Phishing Detection System

Overview:
This project implements an end-to-end MLOps pipeline for detecting phishing attacks in network traffic. It includes data ingestion, preprocessing, model training, evaluation, deployment, and monitoring using modern ML and DevOps tools.

Key Features:
- Automated data ingestion and preprocessing
- ML model training and evaluation for phishing detection
- Model tracking and versioning with MLflow
- Real-time prediction via FastAPI
- CI/CD deployment using GitHub Actions, Docker, and AWS EC2

Tech Stack:
- Python
- Scikit-learn
- MongoDB Atlas
- MLflow
- Docker
- FastAPI
- AWS EC2
- GitHub Actions

Project Structure:
networksecurity/
├── .github/workflows/        - CI/CD workflows
├── Network_Data/             - Raw and cleaned data
├── data_schema/              - Data schema definition
├── final_model/              - Model artifacts
├── logs/                     - Log files
├── mlruns/                   - MLflow tracking logs
├── networksecurity/          - Application code
├── prediction_output/        - Sample prediction outputs
├── templates/                - Frontend templates
├── valid_data/               - Validated data files
├── .gitignore                - Git ignore rules
├── Dockerfile                - Docker config
├── README.md                 - Project documentation
├── app.py                    - FastAPI main app
├── main.py                   - Entry point
├── push_data.py              - Script to push data to DB
├── requirements.txt          - Python dependencies
├── setup.py                  - Setup configuration
└── test_mongodb.py           - MongoDB test script

Installation Instructions:

1. Clone the repository:
   git clone https://github.com/shivam-kr935/networksecurity.git
   cd networksecurity

2. Create and activate a virtual environment:
   python -m venv venv
   On Windows: venv\Scripts\activate
   On Mac/Linux: source venv/bin/activate

3. Install dependencies:
   pip install -r requirements.txt

4. Set up a .env file:
   Include MongoDB URI and any other necessary config.

5. Run the app:
   python app.py

Testing:
- Test MongoDB connection: python test_mongodb.py
- Test predictions via FastAPI endpoint using Postman or browser.

Deployment:
- Docker:
    docker build -t phishing-detection .
    docker run -d -p 8000:8000 phishing-detection

- AWS EC2:
    Launch EC2 instance
    Install Docker
    Pull & run the container

MLflow Usage:
To track experiments:
  mlflow ui
Visit http://localhost:5000

License:
This project is licensed under the MIT License.

Contributing:
Contributions are welcome! Please fork the repo and submit a pull request.

Contact:
Author: Shivam Kumar
GitHub: https://github.com/shivam-kr935

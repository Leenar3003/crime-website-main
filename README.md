***Crime Analysis and Prediction Website – Project Overview***

📁 Project Structure
app.py: Main Flask application entry point

routes.py: Handles routing for all web pages and API endpoints

prediction.py: Contains the logic for crime prediction using ML models

webscapper.py: Automates data collection through web scraping

templates/: Stores all HTML templates (Jinja2)

static/: Contains static resources like CSS, JavaScript, and images

actualdata2.csv: Core dataset for crime statistics and model training

🚀 Application Setup (app.py)
Built using the Flask web framework

Enables Flask-Compress for response compression

(Optional) Integrates Google Sheets API (currently commented out)

Configures application behavior:

Template auto-reload

Compression settings

Error handling for common HTTP errors (404, 500)

🌐 Routes and Web Pages (routes.py)
The app includes several user-facing routes:

/ or /index: Homepage

/crime-charts: Visual representation of crime data (graphs, trends)

/crime-locator: Map view showing crime hotspots

/crime-predictor: User inputs location/year/crime type to get predictions

/feed: Displays latest crime-related news

/predict: API endpoint for backend crime prediction logic

🧠 Prediction Engine (prediction.py)
Two main approaches are used for forecasting:

1. Linear Regression Prediction
Function: predict_crime(state, year, crime_type)

Inputs: State, Year, Crime Type

Process:

Reads from actualdata2.csv

Encodes states using LabelEncoder

Trains a linear regression model

Output: Predicted crime numbers for given parameters

2. Time Series Forecasting (Facebook Prophet)
Function: predictfun()

Process:

Loads historical data

Forecasts for the next 365 days

Generates visual plots and saves predictions as JSON

Use Case: Long-term crime trend analysis

🔄 Data Flow
Historical crime data resides in actualdata2.csv

webscapper.py can update the dataset via automated scraping

Prediction results are:

Calculated via regression or time series models

Rendered as interactive charts/maps

Exchanged as JSON data between frontend and backend

⭐ Key Features
Interactive Crime Forecasting by location, year, and type

Time Series Projections using Prophet

Data Visualization through charts and maps

Upload Capability: Users can add new data files

Error Handling for invalid inputs and routes

REST API Support for prediction services

🔧 Technical Highlights
Framework: Flask

Machine Learning: Scikit-learn (Linear Regression), Prophet

Data Handling: Pandas, NumPy

Visualization: Matplotlib, Plotly

JSON APIs for data exchange

Handles both GET and POST requests

Validation for uploaded files and prediction inputs

🔒 Security Considerations
Input validation (forms, API)

Safe file uploads

Proper error messaging (404/500)

Secure routing and parameter handling

🚀 Deployment-Ready
Procfile included for deployment on Heroku or similar platforms

Configurable environment (port, debug mode)

Static files served efficiently

Scalable and modular for future enhancements

📦 External Dependencies (requirements.txt)
Flask

Pandas

Scikit-learn

Prophet

Matplotlib

Flask-Compress

Other supportive libraries for scraping, visualization, and utilities

🧩 Summary
This Crime Analysis and Prediction System combines:

Web Development (Flask, HTML/CSS/JS)

Machine Learning (Linear Regression)

Time Series Forecasting (Facebook Prophet)

Interactive Visuals (charts, maps)

***The modular structure ensures easy maintenance, scalability, and enhancement potential. This platform not only provides real-time crime insights but also predicts future crime trends to support awareness and proactive planning.***


# Stock Price Analysis and Forecasting Web App

This project is a full-stack web application built with Flask and a SQLite database. It performs stock price analysis and forecasting by integrating multiple data sources and visualization libraries. Users can view interactive stock charts, run Monte Carlo simulations, analyze moving averages, explore joint and pair plots, and even leverage machine learning to forecast stock prices. User authentication is provided via a simple database, enabling secure sign-up and login.

## Overview

The web app consists of three main components:

- **Analysis Module:**  
  Contains functions to fetch stock data from Quandl, calculate moving averages, generate various visualizations (using Bokeh, Matplotlib, and Seaborn), run Monte Carlo simulations for forecasting, and build machine learning models to predict future prices.

- **Database Integration:**  
  Uses SQLite to store user credentials. Passwords are hashed with Passlib for secure authentication. Basic functions handle creating the user table, adding new users, and authenticating logins.

- **Flask Views:**  
  Implements multiple routes for the different pages of the application (home, about, sign-in, sign-up, and various analysis views). These routes combine the analysis outputs and database functions to deliver dynamic, interactive content.

## Features

- **Data Acquisition and Analysis:**
  - Retrieves historical stock data from Quandl.
  - Processes and merges data for multiple stocks (e.g., Coca Cola, Apple, Google).
  - Calculates moving averages and other key metrics.
  
- **Visualizations:**
  - Interactive plots using Bokeh for moving averages and Monte Carlo simulations.
  - Seaborn joint and pair plots for exploring relationships between stock returns.
  - Monte Carlo distribution histograms with risk metrics (e.g., Value at Risk).

- **Machine Learning:**
  - Uses scikit-learn to build and evaluate regression models (Linear Regression, optionally SVR) for forecasting stock prices.
  - Prepares data by scaling and splitting into training and testing sets.

- **User Authentication and Database Integration:**
  - Implements sign-up and login functionality with SQLite.
  - Uses Passlib to securely hash and verify passwords.
  - Basic error handling and feedback for users during authentication.

- **Flask Web Framework:**
  - Clean routing and templating for rendering dynamic HTML pages.
  - Supports multiple views including home, about, sign-in, sign-up, stock price analysis, Monte Carlo simulation, and machine learning forecasts.

## Installation

### Prerequisites

- Python 3.7 or higher
- Virtual environment (recommended)

### Dependencies

Install the required packages using the provided `requirements.txt` file. The project relies on the following key libraries:

- Flask
- pandas
- numpy
- quandl
- bokeh
- scikit-learn
- matplotlib
- seaborn
- passlib

### Setup

1. **Clone the Repository:**

    ```bash
    git clone https://github.com/yourusername/stock-price-analysis.git
    cd stock-price-analysis
    ```

2. **Create and Activate a Virtual Environment:**

    ```bash
    python -m venv venv
    source venv/bin/activate  # On Windows use: venv\Scripts\activate
    ```

3. **Install Dependencies:**

    ```bash
    pip install -r requirements.txt
    ```

4. **Configure API Keys:**

   Update the Quandl API key and any other required tokens in your code (e.g., in the analysis module) with your credentials.

5. **Initialize the Database:**

   Ensure the SQLite database file (e.g., `tutorials.db`) is created and the users table is set up by running the provided database setup functions.

## Usage

1. **Run the Flask App:**

    ```bash
    flask run
    ```

    Or if you use an app runner script (e.g., `python app.py`), run that script instead.

2. **Access the Application:**

   Open your browser and navigate to [http://127.0.0.1:5000](http://127.0.0.1:5000).

3. **Explore the Features:**

   - **Home & About:** General information about the app.
   - **Sign In / Sign Up:** Secure user authentication.
   - **Stock Prices:** View moving average plots and historical stock data.
   - **Plots:** Explore joint and pair plots for stock returns.
   - **Monte Carlo Simulation:** Run simulations to forecast future stock prices and view risk metrics.
   - **Machine Learning:** See predictions for stock prices based on regression models.

## Project Structure

```plaintext
stock-price-analysis/
├── app.py                 # Main Flask application file
├── analysis.py            # Module with stock analysis and forecasting functions
├── db.py                  # Database connection and user authentication functions
├── views.py               # Flask route definitions for various app views
├── templates/             # HTML templates for rendering the web pages
│   ├── home.html
│   ├── about.html
│   ├── signin.html
│   ├── signup.html
│   ├── stockprices.html
│   ├── plots.html
│   ├── montecarlo.html
│   └── machinelearning.html
├── static/                # Static assets (CSS, JavaScript, images)
├── tutorials.db           # SQLite database file (generated on first run)
├── requirements.txt       # List of required Python packages
└── README.md              # This README file

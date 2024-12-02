
# 🌤️ Building an ETL Pipeline with Apache Airflow

This repository contains the code for an **ETL pipeline** designed to extract weather data from the **OpenWeatherMap API**, transform it, and load it into a **PostgreSQL database**. The project demonstrates the use of **Apache Airflow**, **Astronomer**, **Docker**, and other tools to automate and orchestrate the data pipeline efficiently.

---

## 📖 Project Overview

This project focuses on automating the process of weather data collection, transformation, and storage. It highlights:
- **Extracting** weather data, such as temperature, humidity, and wind speed, using the OpenWeatherMap API.
- **Transforming** the raw JSON data into a structured format.
- **Loading** the processed data into a PostgreSQL database for further analysis.

The pipeline is built with **Apache Airflow** to ensure reliability, scalability, and automation.

You can find a detailed explanation of this project in my Medium article:  
[**Building an ETL Pipeline with Apache Airflow: Extracting Weather Data to PostgreSQL**](https://medium.com/@yadavprachi5898/building-an-etl-pipeline-with-apache-airflow-extracting-weather-data-to-postgresql-5a36a5290040)

---

## 🛠️ Tools and Technologies

The following tools and technologies were used in this project:

- **Apache Airflow**: Orchestrates the ETL pipeline through tasks and DAGs.
- **Astronomer**: Simplifies the deployment and management of Airflow.
- **Docker**: Containerizes the application for portability and consistency.
- **PostgreSQL**: Stores the processed weather data.
- **OpenWeatherMap API**: Provides real-time weather data.
- **Python**: Used for scripting the ETL logic.

---

## 🏗️ Project Architecture

The ETL pipeline follows a modular and scalable architecture:

1. **Data Extraction**:
   - Fetches real-time weather data from the OpenWeatherMap API.
   - Key data includes temperature, humidity, wind speed, and conditions.

2. **Data Transformation**:
   - Parses the raw JSON data.
   - Converts it into a tabular format, ensuring compatibility with PostgreSQL.

3. **Data Loading**:
   - Inserts the transformed data into a PostgreSQL database.
   - Ensures the database is ready for queries and analytics.

### Data Flow Diagram:
*(You can add an architecture diagram here if you have one.)*

---

## ⚙️ Setup and Installation

Follow these steps to set up and run the project locally:

### Prerequisites
- **Docker**: Ensure Docker is installed on your machine.

## ⚙️ How to Run the Pipeline

Follow these steps to set up and execute the ETL pipeline:

1. **Start the Docker Environment**:
   - In the terminal, navigate to the project directory.
   - Run the following command to start the environment:
     ```bash
     astro dev start
     ```

2. **Access the Airflow Web UI**:
   - Open your browser and go to `http://localhost:8080`.
   - Use the following credentials:
     - Username: `admin`
     - Password: `admin`

3. **Enable the DAG**:
   - Locate the DAG named `weather_etl_dag` in the Airflow UI.
   - Enable it by toggling the switch.

4. **Run the DAG**:
   - You can trigger the DAG manually from the Airflow UI or let it run based on the pre-configured schedule.

---

## 🌀 How the Pipeline Works

### **Apache Airflow DAG**
- The pipeline is orchestrated through an Airflow DAG defined in the `weather_etl_dag.py` file.
- Key tasks in the DAG:
  1. **`extract_weather_data`**: Fetches weather data from the OpenWeatherMap API.
  2. **`transform_weather_data`**: Cleans and structures the raw data.
  3. **`load_weather_data`**: Loads the processed data into the PostgreSQL database.

### **Data Transformation**
- The pipeline processes the raw JSON response from the API.
- Only relevant fields (e.g., temperature, humidity, wind speed) are extracted and cleaned for storage.

### **Data Storage**
- Transformed data is inserted into a PostgreSQL database.
- The stored data can be queried for analytics or used for visualization.

---

This README provides the necessary instructions and insights to run and understand the ETL pipeline. For more details, refer to the rest of the documentation or the source code.

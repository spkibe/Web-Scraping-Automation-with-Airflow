### Buy Rent Kenya Airflow DAG
> This repository contains an **Airflow DAG** for scraping house rental information from the Buy Rent Kenya website. The data is then stored in a SQLite database. The project is set up to run in a Dockerized Airflow environment.

#### How to Use
1. Clone the repo:
```bash
git clone https://github.com/spkibe/Web-Scraping-Automation-with-Airflow
```
2. Navigate to the Project Directory:
```bash
cd <project-directory>
```
3. Build and Run Docker Containers:
```bash
docker-compose up --build
```

4. Access Airflow UI:
*Visit (http://localhost:8080) to access the Airflow web server.*
5. Trigger the DAG:
Trigger the Buy_Rent_Kenya_Dag manually from the *Airflow UI* or wait for the scheduled interval.

#### Overview
The **Airflow DAG** is defined in *Buy_Rent_Kenya_Dag.py* and is scheduled to run daily at 12:05 PM.

Three tasks are included in the DAG:

> 5.1 *create_table_sqlite*: Creates a SQLite table for housing data. <br>
> 5.2 *scraping*: Scrapes house rental information from Buy Rent Kenya and stores it in a CSV file (*buy_rent_kenya_dag.csv*). <br>
> 5.3 *storeNumber*: Stores the data from the CSV file into a SQLite database (*buyrentkenya.db*).

#### Docker Compose
The *docker-compose.yml* file configures services for PostgreSQL, Airflow web server, scheduler, worker, and triggerer.

Ensure the *AIRFLOW_UID* is set in the *.env* file to avoid permission issues with Docker volumes.

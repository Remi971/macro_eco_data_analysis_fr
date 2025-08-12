# Economic Data Analysis Pipeline

## Description

This project is a data pipeline designed to scrape economic data from the INSEE website, process the data, and load it into a PostgreSQL database. The pipeline is orchestrated using Apache Airflow and containerized with Docker for easy deployment and sharing.

## Features

- **Web Scraping**: Extract economic data from multiple sources.
- **Data Processing**: Clean and transform the scraped data.
- **Data Loading**: Load processed data into a PostgreSQL database.
- **Orchestration**: Use Apache Airflow to schedule and monitor the pipeline.
- **Containerization**: Dockerize the entire pipeline for easy deployment.

## Prerequisites

- Docker
- Docker Compose
- Python 3.9+
- PostgreSQL

## Installation

1. **Clone the Repository**:
   ```sh
   git clone https://github.com/yourusername/your-repo.git
   cd your-repo
2. **Initializing environnement**:
   On Linux, the quick-start needs to know your host user id and needs to have group id set to 0. Otherwise the files created in dags, logs, config and plugins will be created with root user ownership. You have to make        sure to configure them for the docker-compose:
   ```
   mkdir -p ./dags ./logs ./plugins ./config
   echo -e "AIRFLOW_UID=$(id -u)" > .env
   ```
3. **Initialize the database**:
   On all operating systems, you need to run database migrations and create the first user account. To do this, run.
   ```
   docker compose up airflow-init
   ```
5. *Build and Start the Docker Containers**:
   ```docker-compose up```
6. **Access Airflow**:
   Open your web browser and go to http://localhost:8080 to access the Airflow web interface.
   ID : airflow
   password : airflow
7. **Create the database**:
   First you need to get the IPAddress of the postgres container, to do that :
   ```
   docker ps
    ```
   Copy the container ID of the postgres container
   ```
   docker inspect [dockerID]
   ```
   At the end of the json in Networks copy the "IPAddress".
   then go to http://localhost:5433 to access pgAdmin and :
   - Create a new server
   - In the General Tab : Give it a name
   - In the Connection Tab :
     * Host name/ address : [Paste the IPAddress]
     * Port: 5433
     * username: airflow
     * password: airflow
   - And Save.
## Usage

  Trigger the Pipeline:
  
  Access the Airflow web interface.
  Trigger the etl_pipeline DAG to start the data scraping, processing, and loading workflow.
  
  Monitor the Pipeline:
  
  Use the Airflow web interface to monitor the progress and status of the pipeline.

## Project Structure
```
  /project
├── /dags
│   └── etl_pipeline.py
├── /src
│   ├── scraper.py
│   ├── processor.py
│   └── loader.py
├── Dockerfile
├── docker-compose.yml
├── requirements.txt
└── README.md
```

## Configuration
Dockerfile: Configures the Docker image for the Airflow environment.
docker-compose.yml: Defines the services for the PostgreSQL database and Airflow.
requirements.txt: Lists the Python dependencies required for the project.
## Contributing
Contributions are welcome! Please fork the repository and create a pull request with your changes.
## License
This project is licensed under the MIT License. See the LICENSE file for more details.
## Contact
For any questions or suggestions, please open an issue or contact me at [your email].

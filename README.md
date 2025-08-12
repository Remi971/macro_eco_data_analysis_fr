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
2. **Set Up Environment Variables**:
   Create a .env file in the root directory and add the necessary environment variables:
   POSTGRES_PASSWORD=secret
   POSTGRES_DB=test
3. *Build and Start the Docker Containers**:
   ```docker-compose up --build```
4. **Access Airflow**:
   Open your web browser and go to http://localhost:8080 to access the Airflow web interface.

## Usage

  Trigger the Pipeline:
  
  Access the Airflow web interface.
  Trigger the etl_pipeline DAG to start the data scraping, processing, and loading workflow.
  
  Monitor the Pipeline:
  
  Use the Airflow web interface to monitor the progress and status of the pipeline.

## Project Structure

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

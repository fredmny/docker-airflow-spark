# Docker Airflow Spark
This repo contains the files to build a Docker environment with Airflow and Spark, ready to connect to AWS. It's intended for development purposes only. 
## How-to
Follow these steps to run it
1. Create the Docker container:
    ```
    cd docker
    docker build -t airflow-fred:latest .
    cd ..
    ```
2. Run the Docker container:
    ```
    docker compose up -d 
    ```
3. Access Airflow at `localhost:8080` in your web browser
    - user: `admin`
    - pwd: `admin`
4. Add following connections in the Airflow UI:
    - Spark local:
        - Name: `spark_local`
        - Connection Type: `Spark`
        - Host: `local[*]
    - AWS (optional):
        - Name: `aws_credentials`
        - Connection Type: `Amazon Web Services`
        - AWS Access Key ID: `<your aws access key id>`
        - AWS Access Key Secret: `< youar awd access key secret>`
5. After finishing, shut down the running container:
    ```
    docker compose down
    ```
## References
It was based on the instructions and repo from [Deploying Airflow with Docker](https://medium.com/lynx-data-engineering/deploying-airflow-with-docker-20c72821bc7b), but with a few important adjustments, mainly to make it run with AWS.

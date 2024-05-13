# Data-Spider
Data Spider is a powerful web scraping tool built with Python and FastAPI. It allows you to effortlessly scrape product information from a catalogue website and store the scraped data in a structured JSON format. The scraper is designed to be run inside a Docker container, providing a seamless and hassle-free setup process.


    
***Scraping Results***
1. **storage of products**
     
  <img width="1244" alt="product-data" src="https://github.com/TusharLakhera/Data-Spider/assets/23501469/3f8346cd-52b6-4992-8c7e-eb7d30b0eb45">

  
2. **Notifications on scraping each page**

  <img width="765" alt="notifications" src="https://github.com/TusharLakhera/Data-Spider/assets/23501469/0cd170d2-367c-4eb4-9e13-4df38f1d8822">

  
3. **storing results in cache which will be only used to update the database if there any price changes**
     
  
   <img width="1435" alt="cachin in redis" src="https://github.com/TusharLakhera/Data-Spider/assets/23501469/03c41f3e-6628-425c-9112-9ee83f878346">


## Prerequisites

Before diving into the installation and setup process, ensure that you have the following prerequisites installed on your system:

- Docker: Data Spider relies on Docker to run the scraper in a containerized environment. Make sure you have Docker installed on your machine. You can download and install Docker from the official website: [Install Docker](https://docs.docker.com/get-docker/).

- Docker Compose: Docker Compose is a tool for defining and running multi-container Docker applications. It simplifies the process of managing and orchestrating multiple Docker containers. Docker Compose is typically installed along with Docker. You can find installation instructions for Docker Compose on the official Docker website: [Install Docker Compose](https://docs.docker.com/compose/install/).


## Installation and Setup

Follow these step-by-step instructions to set up and run the Data Spider scraper on your local machine:

1. **Clone the Repository**:
   Start by cloning the Data Spider repository to your local machine. Open a terminal and run the following command:

   ```bash
   git clone https://github.com/TusharLakhera/Data-Spider.git
   cd Data-Spider
   
2.  **docker commands to initialise app**:
    Build the Docker Image:
    With the configuration in place, you're ready to build the Docker image for the Data Spider scraper. In the terminal, make sure you're still in the project directory and run the following command:
    ```bash
    docker-compose build
    //running the container default port 8000
    docker-compose up
    ```

3.  **import this curl in postman or use fastapi Swagger documentation to initialise the scraper**
    
    make sure to replace the auth token with right key provided
    ```bash
        curl --location 'localhost:8000/scrape?max_pages=10&proxy=' \
        --header 'AUTH-TOKEN: ****-****-'
    ```
    fast api doc link
    ```
    http://localhost:8000/docs

    ```

    <img width="1383" alt="fastAPI docs" src="https://github.com/TusharLakhera/Data-Spider/assets/23501469/a9fdab01-25ac-4f37-a3b3-73666ea70999">
    <img width="1369" alt="API results" src="https://github.com/TusharLakhera/Data-Spider/assets/23501469/1f90ff53-b392-47b7-ae61-5f720037b2a8">

4. ***cached results can be checked by entering redis container using below commands***

   ```bash
    docker exec -it <container-id> sh
    redis-cli
   ```
   
   <img width="976" alt="redis-container" src="https://github.com/TusharLakhera/Data-Spider/assets/23501469/49a1f035-bb72-4e44-b47c-8523bf24e20a">


   


# Vehicle Owner Garage Application

This repository contains the source code for a JavaScript application that manages a vehicle owner's garage using MongoDB as the database.

## API Endpoints

- To retrieve the vehicles in the owner's garage collection, send an HTTP GET request to:
  `/autoCollection/{ownerId}`

  Example:
  ```
  GET http://host:3000/autoCollection/3
  ```

- To create a new owner, send an HTTP POST request to:
  `/autoCollection/{ownerId}`

  Example:
  ```
  POST http://host:3000/autoCollection/3
  Body:
  {
    "model": "tesla",
    "engine": "electric"
  }
  ```

- To add a new vehicle, send an HTTP POST request to:
  `/newCar`

  Example:
  ```
  POST http://host:3000/newCar
  Body:
  {
    "ownerId": 3,
    "store": {
      "model": "audi",
      "engine": "3L"
    }
  }
  ```

## Running the Application

This project combines tasks 2 and 3. It involves running the application as a Linux service, connecting to a MongoDB instance on another EC2 instance, and running the application in a Docker container that also connects to the same MongoDB instance.

- For Task 2:
  - The application is running as a Linux service.
  - Access the application using port 3000.

- For Task 3:
  - The application is running in a Docker container.
  - Access the application using port 80.
  - The Dockerfile for building the container is included in this project.
  - to start container
   ``` sudo docker run -d -p80:3000 -e "MONGO_DATABASE_URL=mongodb://10.1.0.139:27017/?directConnection=true&serverSelectionTimeoutMS=2000" --name collection maluyvova/collection   ```

### Docker hub link https://hub.docker.com/r/maluyvova/collection

##  The public IP of the EC2 instance hosting the application is: 54.219.135.233.

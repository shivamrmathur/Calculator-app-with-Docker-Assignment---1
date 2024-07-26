
## Calculator App with Docker

## Author
Name: Shivam Mathur  
Roll Number: G23AI2103

## Overview
This project is a calculator web application built using Python and Flask. The application allows users to perform basic arithmetic operations: addition, subtraction, multiplication, and division through a web interface. The project is containerized using Docker, ensuring consistent environments for development, testing, and production.

## Table of Contents
1. [Features](#features)
2. [Technologies Used](#technologies-used)
3. [Setup and Installation](#setup-and-installation)
   - [Prerequisites](#prerequisites)
   - [Installation Steps](#installation-steps)
4. [Usage](#usage)
5. [Testing](#testing)
6. [Screenshots](#screenshots)
7. [Docker Configuration](#docker-configuration)
   - [Dockerfile](#dockerfile)
   - [Docker Compose](#docker-compose)
8. [Additional Docker Commands](#additional-docker-commands)
9. [Contributing](#contributing)
10. [License](#license)

## Features
- **Addition**: Add two numbers.
- **Subtraction**: Subtract one number from another.
- **Multiplication**: Multiply two numbers.
- **Division**: Divide one number by another.

## Technologies Used
- **Python**: Programming language used to build the application.
- **Flask**: A lightweight WSGI web application framework for Python.
- **Docker**: Containerization platform used to create consistent environments for the application.

## Setup and Installation

### Prerequisites
- Docker
- Docker Compose

### Installation Steps

1. **Clone the Repository**: Download the project to your local machine.
   ```sh
   git clone https://github.com/shivamrmathur/Calculator-app-with-Docker-Assignment---1.git
   cd calculator_app
   ```

2. **Build the Docker Image**: Create a Docker image for the application. This step reads the Dockerfile and sets up the environment.
   ```sh
   docker-compose build --no-cache
   ```

3. **Run the Application**: Start the application using Docker Compose. This command will create and start the container as defined in the `docker-compose.yml` file.
   ```sh
   docker-compose up
   ```

4. **Access the Application**: Open a web browser and go to `http://localhost:5000`. You should see the simple calculator web application.

## Usage
1. Open a web browser and navigate to `http://localhost:5000`.
2. Enter two numbers in the provided input fields.
3. Select an arithmetic operation (add, subtract, multiply, divide).
4. Click the "Calculate" button to see the result.

## Testing
To run tests (if applicable), follow these steps:
1. Ensure the application is running.
2. Use a testing tool or framework (e.g., pytest) to run the tests.

## Screenshots
Screenshots of the application are available in the `screenshots` folder in the repository.

## Docker Configuration

### Dockerfile
The `Dockerfile` sets up the Docker image for the Flask application. It uses the official Python image, installs the necessary dependencies, and runs the Flask app.

```Dockerfile
# Use the official Python image from the Docker Hub
FROM python:3.9-slim

# Set the working directory in the container
WORKDIR /app

# Copy the current directory contents into the container at /app
COPY . /app

# Install any needed packages specified in requirements.txt
RUN pip install --no-cache-dir -r requirements.txt

# Make port 5000 available to the world outside this container
EXPOSE 5000

# Run app.py when the container launches
CMD ["python", "app.py"]
```

### Docker Compose
The `docker-compose.yml` file sets up the services and ports for the application. It builds the image from the Dockerfile and exposes port 5000.

```yaml
version: '3.8'

services:
  web:
    build: .
    ports:
      - "5000:5000"
    volumes:
      - .:/app
```

## Additional Docker Commands

- **Stop the Containers**: To stop the running containers without removing them, use:
  ```sh
  docker-compose stop
  ```

- **Remove the Containers**: To stop and remove the containers, use:
  ```sh
  docker-compose down
  ```

- **View Running Containers**: To list all running containers, use:
  ```sh
  docker ps
  ```

- **Remove Docker Images**: To remove Docker images to free up space, use:
  ```sh
  docker rmi <image_id>
  ```

## Contributing
If you would like to contribute to this project, please follow these steps:
1. Fork the repository.
2. Create a new branch (`git checkout -b feature/your-feature-name`).
3. Make your changes and commit them (`git commit -m 'Add some feature'`).
4. Push to the branch (`git push origin feature/your-feature-name`).
5. Open a pull request.

## License
This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

# Hello World Application

This project is a simple "Hello World" application designed to demonstrate how to deploy a Docker Compose application using Coolify. It features a basic web UI that displays "Hello World!" and is structured for easy understanding and modification.

## Prerequisites

- Docker installed on your machine.
- Docker Compose installed.
- A Coolify account to deploy the application.

## Project Structure

```txt
hello-world-coolify-docker-compose
├── src
│   ├── app.js          # Main entry point of the application
│   ├── public
│   │   ├── index.html  # HTML structure of the web UI
│   │   └── style.css    # CSS styles for the web UI
│   └── package.json    # npm configuration file
├── .vscode
│   └── settings.json    # Development environment settings
├── context
│   └── context.md       # Additional information about the application
├── Dockerfile           # Instructions for building the Docker image
├── docker-compose.yml    # Service definitions for Docker Compose
└── README.md           # Instructions for deploying the application
```

## Setup Instructions

1. Clone the repository to your local machine.
2. Navigate to the project directory.
3. Build the Docker image using the following command:

   ```bash
   docker-compose build
   ```

4. Start the application with Docker Compose:

   ```bash
   docker-compose up
   ```

5. Open your web browser and go to `http://localhost:3000` to see the "Hello World!" message.

## Deploying on Coolify

1. Log in to your Coolify account.
2. Create a new application and select the Docker Compose option.
3. Upload the `docker-compose.yml` file and any other necessary files.
4. Follow the prompts to configure your application settings.
5. Deploy the application and access it via the provided URL.

## Conclusion

This simple application serves as a foundation for understanding how to deploy applications using Docker Compose on Coolify. Feel free to modify and expand upon it as needed!

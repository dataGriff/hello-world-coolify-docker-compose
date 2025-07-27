# Hello World Coolify Docker Compose

This project is a simple "Hello World" application designed to demonstrate how to deploy a static website using Docker Compose on Coolify. It features a basic HTML page served by NGINX and includes configurations for both local development and production deployment.

## Prerequisites

- Docker installed on your machine
- Docker Compose installed
- Node.js and npm (for convenience scripts)
- A Coolify account for deployment

## Project Structure

```txt
hello-world-coolify-docker-compose
├── web
│   └── index.html              # Static HTML content
├── context
│   └── context.md              # Additional project information
├── Dockerfile                  # NGINX-based Docker image
├── docker-compose.yml          # Base Docker Compose configuration
├── docker-compose.local.yml    # Local development overrides
├── docker-compose.prod.yml     # Production overrides
├── package.json                # npm scripts for convenience
└── README.md                   # This file
```

## Local Development

### Using npm scripts (recommended)

```bash
# Start for local development (exposes port 8080)
npm run docker:local

# Build and start for local development
npm run docker:local:build

# Stop local development containers
npm run docker:local:down
```

### Using Docker Compose directly

```bash
# Start for local development
docker compose -f docker-compose.yml -f docker-compose.local.yml up

# Build and start
docker compose -f docker-compose.yml -f docker-compose.local.yml up --build

# Stop containers
docker compose -f docker-compose.yml -f docker-compose.local.yml down
```

Once running, open your web browser and go to `http://localhost:8080` to see the application.

## Production Testing

Test the production configuration locally:

```bash
# Using npm scripts
npm run docker:prod

# Or directly with Docker Compose
docker compose -f docker-compose.yml -f docker-compose.prod.yml up
```

## Deploying on Coolify

### Repository Setup

1. Push your code to a Git repository (GitHub, GitLab, etc.)
2. Ensure your repository includes:
   - `docker-compose.yml` (base configuration)
   - `Dockerfile`
   - `web/` directory with your static files

### Coolify Deployment

1. Log in to your Coolify instance
2. Create a new application
3. Select "Docker Compose" as the deployment type
4. Connect your Git repository
5. Coolify will automatically use the base `docker-compose.yml` file
6. Deploy the application

Coolify will handle port mapping automatically, so no manual port configuration is needed.

- [Coolify Link](http://oswoss8ggowsooscsk40g0cg.95.217.216.210.sslip.io/)

### Health Monitoring

The application includes built-in health checks that Coolify will use to:

- Monitor application health every 30 seconds
- Automatically restart unhealthy containers
- Provide health status in the Coolify dashboard
- Ensure zero-downtime deployments

## Docker Compose Files Explained

- **`docker-compose.yml`**: Base configuration used by Coolify (no port mapping)
- **`docker-compose.local.yml`**: Local development overrides (adds port 8080:80)
- **`docker-compose.prod.yml`**: Production overrides (adds restart policies)

This multi-file approach ensures your application works seamlessly in both local development and Coolify deployment environments.

## Conclusion

This application demonstrates best practices for deploying static websites with Docker Compose on Coolify. The multi-file Docker Compose approach provides flexibility for different environments while maintaining simplicity. The built-in health checks ensure reliable deployments and monitoring.

Key features:

- **Environment-specific configurations**: Separate files for local and production
- **Health monitoring**: Automatic health checks and container restart
- **Static file serving**: Efficient NGINX-based serving
- **Coolify-ready**: Zero-configuration deployment on Coolify

Feel free to modify the static content in the `web/` directory and extend the configuration as needed!

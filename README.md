# MERN Stack Dockerized Application

This repository contains a MERN (MongoDB, Express.js, React.js, Node.js) stack application that has been Dockerized for easy deployment and development. The project structure includes Dockerfiles for the backend (Express.js) and frontend (React.js), along with a Docker Compose configuration to orchestrate the containers.

## Prerequisites

Make sure you have Docker and Docker Compose installed on your machine.

- [Docker Installation Guide](https://docs.docker.com/get-docker/)
- [Docker Compose Installation Guide](https://docs.docker.com/compose/install/)

## Project Structure

- `client/`: React.js frontend application
- `api/`: Express.js backend application
- `docker-compose.yml`: Docker Compose configuration file
- `api/Dockerfile`: Dockerfile for the Express.js backend
- `client/Dockerfile`: Dockerfile for the React.js frontend
- `.dockerignore`: File to specify files and directories to be ignored during the Docker build

## Getting Started

1. **Clone the repository:**

    ````
    git clone https://github.com/your-username/your-mern-docker-repo.git
    ````

2. **Navigate to the project directory:**

    ````
   cd your-mern-docker-repo
    ````

4. **Build and run the Docker containers:**

    ````
    docker-compose up -d
    ````

    This command will build the Docker images and start the containers in the background.

5. **Access the application:**

   - Frontend: [http://localhost:3000](http://localhost:3000)
   - Backend: [http://localhost:5000](http://localhost:5000)

## Docker Compose Configuration

The `docker-compose.yml` file defines three services:

- `front`: React.js frontend
- `backend`: Express.js backend
- `mongo`: MongoDB

It also specifies a custom network (`mern-stack-network`) and a volume (`mongoData`) for persistent MongoDB data.

## Dockerfiles

### Backend (Express.js)

The `Dockerfile` for the Express.js backend installs dependencies, copies the application code, and exposes port 5000. It then sets the command to run the application using `npm start`.

### Frontend (React.js)

The `client/Dockerfile` for the React.js frontend sets up the working directory, installs dependencies, copies the application code, exposes port 3000, and sets the command to run the application using `npm run start`.

## Additional Notes

- The backend service depends on the `mongo` service, ensuring that the MongoDB container is started before the backend.
- Environment variables for the backend are loaded from the `.env` file in the `api/` directory.

Feel free to customize the Dockerfiles, Docker Compose configuration, and any other files to fit your specific requirements.


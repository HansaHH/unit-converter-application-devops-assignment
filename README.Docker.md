```markdown
#  Unit Converter Application

A full-stack, containerized Unit Converter web application built using the MERN stack (MongoDB, Express.js, React, Node.js) and orchestrated with Docker. It features a secure Nginx reverse proxy to seamlessly connect the frontend and backend.

##  Architecture & Tech Stack

* **Frontend:** React.js (Vite), Tailwind CSS
* **Backend:** Node.js, Express.js
* **Database:** MongoDB Atlas (Cloud)
* **Web Server / Proxy:** Nginx
* **DevOps / Containerization:** Docker, Docker Compose

##  Getting Started (Local Development)

Follow these instructions to get a copy of the project up and running on your local machine using Docker.

### 1. Prerequisites
Ensure you have the following installed on your machine:
* [Docker Desktop](https://www.docker.com/products/docker-desktop/)
* [Git](https://git-scm.com/)

### 2. Environment Setup (Important)
Before building the application, you must configure the database connection. 

1. Navigate to the `backend` directory.
2. Create a file named `.env` (Do NOT commit this file to Git).
3. Add your MongoDB Atlas connection string inside the `.env` file like this:

```text
MONGO_URI=mongodb+srv://hasinduhemal2001_db_user:<your_password>@unitcounter.rdhhaiv.mongodb.net/unitconverter?appName=unitcounter

```

*(Replace `<your_password>` with your actual database password).*

### 3. Build and Run the Application

Open your terminal in the root directory of the project and run the following Docker Compose command:

```bash
docker compose up --build -d

```

This single command will:

1. Build the React frontend and configure the Nginx web server.
2. Build the Node.js backend API.
3. Start all containers in a shared secure Docker network.

### 4. Access the Application

Once the containers are successfully running:

* **Frontend UI:** Open your browser and go to [http://localhost:3000](https://www.google.com/search?q=http://localhost:3000)
* **API Endpoints:** The Nginx reverse proxy automatically routes `/api` requests from port `3000` to the internal backend container running on port `5000`.

##  API Documentation

For detailed information regarding the available API endpoints (Authentication, Conversion, and History), please refer to the [`API_DOCUMENTATION.md`](https://www.google.com/search?q=backend/API_DOCUMENTATION.md) file located in the backend directory.

##  Stopping the Application

To stop the running containers and remove the network, run:

```bash
docker compose down

```

##  Deployment Note

This application is fully containerized and production-ready. It can be easily deployed to any cloud provider that supports Docker (e.g., AWS EC2, DigitalOcean Droplets, or Azure VMs) by cloning the repository, setting up the `.env` file, and running `docker compose up -d`.

```
# Flask With Docker

A simple Flask server with a React frontend. The purpose of this project is to learn how to install and configure Node.js and Python manually on an Ubuntu machine. Additionally, it demonstrates how to run multiple ancillary services related to the main application, such as a PostgreSQL database and Redis, and how to manage them with a single command using Docker Compose.

### Instructions to run locally

Clone the Repository:

```bash
git clone https://github.com/sifatullahsu/flask-with-docker.git
cd flask-with-docker
```

Create a .env file in the root directory and add the following environment variables:

```env
DATABASE_URL=postgresql://postgres:password@db:5432/postgres
REDIS_URL=redis://redis:6379/0
```

To start the application with all its services, run:

```bash
docker compose up -d
```

To stop all running services, run:

```bash
docker compose down
```

**Note:** Make sure you have started the Docker 😉

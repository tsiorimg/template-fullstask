# Template fullstask

This is the root project containing both the frontend and backend services. The project uses Docker for containerization.

## Prerequisites

- Docker
- Docker Compose

## Getting Started

### Cloning the Repository

```bash
git clone --recurse-submodules https://github.com/tsiorimg/template-fullstask.git
cd template-fullstask
```
### Setting Up Environment Variables
Create a .env file in the root directory and add the following environment variables:
```bash
POSTGRES_DB=your_database_name
POSTGRES_USER=your_database_user
POSTGRES_PASSWORD=your_database_password
DATABASE_URL=postgresql://your_database_user:your_database_password@postgres:5432/your_database_name
```

### Running the Application

Build and run the Docker containers:

```bash
docker-compose up -d --build
```

### Stopping the Application

```bash
docker-compose down
```

### Issues and Improvements

- CORS Issue: There is an ongoing issue with CORS in the Dockerized environment. Currently, 127.0.0.1 is used as a workaround for API requests. This needs to be resolved for production. [See issue #1](https://github.com/tsiorimg/template-fullstask/issues/1)

## License
This project is licensed under the MIT License - see the LICENSE.md file for details.

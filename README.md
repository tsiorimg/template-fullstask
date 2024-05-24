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
Create two environment files: .env.development and .env.production in the root directory.

`.env.development`

```bash
POSTGRES_DB=your_dev_database_name
POSTGRES_USER=your_dev_database_user
POSTGRES_PASSWORD=your_dev_database_password
DATABASE_URL=postgresql://your_dev_database_user:your_dev_database_password@postgres:5432/your_dev_database_name
ENV_CONFIG=development
NODE_OPTIONS=--openssl-legacy-provider
REACT_APP_API_URL=http://127.0.0.1:5000
```


`.env.production`

```bash
POSTGRES_DB=your_prod_database_name
POSTGRES_USER=your_prod_database_user
POSTGRES_PASSWORD=your_prod_database_password
DATABASE_URL=postgresql://your_prod_database_user:your_prod_database_password@postgres:5432/your_prod_database_name
ENV_CONFIG=production
NODE_OPTIONS=--openssl-legacy-provider
REACT_APP_API_URL=http://backend:5000
```

Additionally, create a .env file that specifies the current environment configuration.

`.env`

```bash
ENV_CONFIG=development  # or production
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

### Switching Environments

To switch between development and production environments, modify the ENV_CONFIG value in the .env file.

### Issues and Improvements

- CORS Issue: There is an ongoing issue with CORS in the Dockerized environment. Currently, 127.0.0.1 is used as a workaround for API requests. This needs to be resolved for production. [See issue #1](https://github.com/tsiorimg/template-fullstask/issues/1)

## License
This project is licensed under the MIT License - see the LICENSE.md file for details.

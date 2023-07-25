```
version: '3.8'

services:
  postgres:
    image: postgres:14
    container_name: postgres-container
    restart: always
    environment:
      POSTGRES_USER: your_username
      POSTGRES_PASSWORD: your_password
      POSTGRES_DB: your_database_name
    volumes:
      - ./data:/var/lib/postgresql/data
    ports:
      - "5432:5432"
```

## Docker Compose Configuration for PostgreSQL

This `docker-compose.yml` file is used to create and configure a Docker container running PostgreSQL version 14. The file defines a service named `postgres` that uses the official PostgreSQL version 14 Docker image (`postgres:14`) from Docker Hub as the base image.

### Version

```yaml
version: '3.8'

This line specifies the version of the Docker Compose syntax being used. In this case, it's version 3.8. Different versions support different features and syntax, so make sure you are using a version that's compatible with your Docker and Docker Compose installations.
Services

yaml

services:
  postgres:
    image: postgres:14

The services section defines the services that make up your application. In this case, we have a service named postgres, which uses the official PostgreSQL version 14 Docker image (postgres:14) from Docker Hub as the base image.
Container Name

yaml

    container_name: postgres-container

The container_name specifies a custom name for the container. In this case, the container will be named "postgres-container."
Restart Policy

yaml

    restart: always

The restart option specifies the restart policy for the container. Here, we set it to "always," meaning that Docker will automatically restart the container if it stops or crashes.
Environment Variables

yaml

    environment:
      POSTGRES_USER: your_username
      POSTGRES_PASSWORD: your_password
      POSTGRES_DB: your_database_name

The environment section allows you to set environment variables inside the container. Here, we are setting three environment variables for the PostgreSQL container: POSTGRES_USER, POSTGRES_PASSWORD, and POSTGRES_DB. Replace your_username, your_password, and your_database_name with the desired credentials and database name.
Volumes

yaml

    volumes:
      - ./data:/var/lib/postgresql/data

The volumes section specifies a data volume that will be mounted into the container. In this case, it maps the ./data directory on the host (your current directory) to the /var/lib/postgresql/data directory inside the container. This allows the data to be persisted even if the container is stopped or removed.
Ports

yaml

    ports:
      - "5432:5432"

The ports section maps port 5432 of the container to port 5432 on the host. Port 5432 is the default port that PostgreSQL listens on, so this allows you to access the PostgreSQL database from your local machine.

With this updated docker-compose.yml file, you can now run the PostgreSQL container using the following command:
docker-compose up -d


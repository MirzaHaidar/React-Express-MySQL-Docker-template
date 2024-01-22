# Compose Sample Application

## Use with Docker Development Environments

Explore this sample using the Dev Environments feature of Docker Desktop version 4.12 or later.

[![Open in Docker Dev Environments](../open_in_new.svg)](https://open.docker.com/dashboard/dev-envs?url=https://github.com/docker/awesome-compose/tree/master/react-express-mysql)

## React Application with NodeJS Backend and MySQL Database

**Project Structure:**
```plaintext
.
├── backend
│   ├── Dockerfile
│   ...
├── db
│   └── password.txt
├── compose.yaml
├── frontend
│   ├── ...
│   └── Dockerfile
└── README.md
```
###compose.yaml
```
services:
  backend:
    build: backend
    ports:
      - 80:80
      - 9229:9229
      - 9230:9230
    ...
  db:
    # Use mariadb image supporting both amd64 & arm64 architecture
    image: mariadb:10.6.4-focal
    # If you prefer MySQL, uncomment the following line
    #image: mysql:8.0.27
    ...
  frontend:
    build: frontend
    ports:
      - 3000:3000
    ...
```

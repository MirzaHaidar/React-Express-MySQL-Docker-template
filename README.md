Compose Sample Application

Use with Docker Development Environments:
You can leverage the Dev Environments feature of Docker Desktop version 4.12 or later to explore this sample application.

React Application with NodeJS Backend and MySQL Database
Project Structure:
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

compose.yaml:
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

The compose file defines an application with three services: frontend, backend, and db. When deploying, Docker Compose maps port 3000 of the frontend service container to port 3000 of the host.

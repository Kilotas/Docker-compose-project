# Docker Compose Project with MongoDB, Collector, and Flask App

This project uses Docker Compose to manage three connected services: mymongo (MongoDB), collector (custom service from ./checker), and flaskapp (Flask web app from ./plot).

## Features

- MongoDB database with authentication
- Custom collector service
- Flask web application
- Easy local development with Docker Compose

## Requirements

- Docker
- Docker Compose

## Project Structure
```
.
├── docker-compose.yml
├── checker/
│   └── (Dockerfile and code for collector)
└── plot/
    └── (Dockerfile and code for flaskapp)
```

## Quick Start

1. Clone the repository or download the files:

   git clone https://github.com/Kilotas/Docker-compose-project.git
   cd train_compose

2. Build and start all services:

   docker-compose up --build -d

This will:
- Pull the official MongoDB image
- Build collector and flaskapp images from local folders
- Start all containers in the background

## Service Details

### mymongo
- Official mongo image
- Environment variables:
  - MONGO_INITDB_ROOT_USERNAME: root
  - MONGO_INITDB_ROOT_PASSWORD: example
- Port mapping: 27017 on host ➜ 27017 in container
- Connect locally with:
  mongodb://root:example@localhost:27017

### collector
- Built from ./checker
- Depends on mymongo
- Starts after MongoDB is ready

### flaskapp
- Built from ./plot
- Depends on mymongo
- Port mapping: 5000 on host ➜ 5000 in container
- Accessible at http://localhost:5000

## Useful Commands

- Start services:
  docker-compose up -d

- Stop services:
  docker-compose down

- View logs:
  docker-compose logs -f

- Rebuild after changes:
  docker-compose up --build -d

## License

Feel free to use and modify this project.

## Author
Omarov Alen
https://github.com/Kilotas



# Docker Project

This repository contains my solutions for the Docker project in the `holbertonschool-softy-pinko-docker` repository.  
Through these tasks, I practiced the fundamentals of Docker, containerization, Docker Compose, reverse proxy setup, and horizontal scaling using Nginx and multiple services.

## Learning Objectives

Through this project, the following Docker and deployment concepts are practiced:

- Creating Docker images with Dockerfiles
- Running containers from custom images
- Installing dependencies inside Docker images
- Serving a Python Flask API in a container
- Serving static front-end files with Nginx
- Connecting front-end and back-end services
- Using Docker Compose to orchestrate multiple containers
- Configuring a reverse proxy with Nginx
- Routing traffic between services with proxy rules
- Scaling services horizontally with Docker Compose
- Understanding simple Round-Robin load balancing

## Requirements

- Each task is organized in its own directory
- Dockerfiles are created according to the project instructions
- Python dependencies are installed inside Docker images where needed
- Nginx is used to serve static files and proxy requests
- Docker Compose is used for multi-service orchestration
- Service names are used for internal container communication
- The project is structured to support reverse proxying and horizontal scaling

## What I Learned

By completing this project, I learned how to:

- build a Docker image from a basic `Dockerfile`
- use Ubuntu as a base image and install packages with `apt-get`
- create and run a Flask back-end service inside a container
- expose services on specific ports
- organize a project into separate front-end and back-end directories
- use Nginx to serve static front-end content
- configure Nginx with custom server blocks
- connect a front-end to a back-end API using JavaScript and AJAX
- enable CORS in Flask to allow communication between containers
- define and manage multiple services with `docker-compose.yml`
- configure an Nginx proxy server to forward `/` and `/api` requests
- hide internal services behind a single proxy entry point
- scale the back-end service horizontally using Docker Compose
- understand how Docker service names allow internal networking between containers
- observe how Nginx distributes requests across multiple API servers using Round-Robin load balancing

## Tasks Overview

| Task | Title | Main Concepts Covered |
|------|-------|------------------------|
| task0 | Create Your First Docker Image | Dockerfile basics, Ubuntu image, package update/upgrade, running a simple container |
| task1 | Back-end | Flask API, Python installation, pip, working directory, copying files into image |
| task2 | Front-end | Nginx static server, serving front-end files, Nginx config, project reorganization |
| task3 | Connecting the Front-end and Back-end | AJAX requests, dynamic content, Flask-CORS, communication between services |
| task4 | Making it Simpler with Docker Compose | Multi-service orchestration, docker-compose, service definitions, ports, dependencies |
| task5 | Proxy Server | Reverse proxy, Nginx proxy rules, internal routing, hiding direct service access |
| task6 | Scale Horizontally | Docker Compose scaling, multiple API containers, Round-Robin load balancing |

## Detailed Task Summary

| Task | Description | Files |
|------|-------------|-------|
| task0 | Created a basic Docker image based on `ubuntu:latest`, updated and upgraded APT packages, and configured the container to print `Hello, World!` when run. | `task0/Dockerfile` |
| task1 | Built a Flask back-end container by installing `python3`, `python3-pip`, and `flask`, then copied `api.py` into the image and served `/api/hello` on port `5252`. | `task1/Dockerfile`, `task1/api.py` |
| task2 | Reorganized the project into `back-end` and `front-end`, cloned the static front-end files, and configured Nginx to serve the front-end on port `9000`. | `task2/back-end/Dockerfile`, `task2/back-end/api.py`, `task2/front-end/Dockerfile`, `task2/front-end/softy-pinko-front-end.conf` |
| task3 | Connected the front-end to the back-end using AJAX, added a dynamic content heading to the page, and enabled CORS in Flask using `flask-cors`. | `task3/back-end/Dockerfile`, `task3/back-end/api.py`, `task3/front-end/softy-pinko-front-end/index.html` |
| task4 | Created a `docker-compose.yml` file to define and run the front-end and back-end services together with simpler multi-container management. | `task4/docker-compose.yml`, `task4/back-end/*`, `task4/front-end/*` |
| task5 | Added a proxy server with Nginx, routed `/` to the front-end and `/api` to the back-end, updated the front-end API call to go through the proxy, and restricted external access to the proxy only. | `task5/proxy/Dockerfile`, `task5/proxy/proxy.conf`, `task5/docker-compose.yml`, `task5/front-end/softy-pinko-front-end/index.html` |
| task6 | Scaled the back-end horizontally by creating a file containing the exact Docker Compose command used to start two API servers behind the proxy. | `task6/2-api-servers.txt` |

## Notes

- Each task follows the structure and requirements specified in the project instructions.
- The project gradually evolves from a single Docker image into a multi-service architecture.
- Nginx is used in two different roles: as a static file server and as a reverse proxy.
- Docker Compose simplifies the management of multiple related containers.
- The final tasks demonstrate how scaling and load balancing can be introduced with minimal changes to the overall project structure.
- The project focuses on practical Docker usage, service communication, and deployment architecture, not only basic container commands.

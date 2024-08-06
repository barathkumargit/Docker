# Docker Cheat Sheet

Welcome to the Docker Cheat Sheet! This guide covers basic to advanced Docker commands and concepts, helping you get started and master Docker.

---

## 1. Basic Docker Concepts and Terms

- **Docker Image:** A lightweight, stand-alone, executable package that includes everything needed to run a piece of software.
- **Docker Container:** A runtime instance of a Docker image.
- **Docker Hub:** A cloud-based registry service where Docker users and partners create, test, store, and distribute container images.
- **Dockerfile:** A text document containing all the commands a user could call on the command line to assemble an image.
- **Docker Compose:** A tool for defining and running multi-container Docker applications.

---

## 2. Basic Docker Commands

- `docker --version`: Display Docker version.
- `docker info`: Display system-wide information.
- `docker run image`: Run a Docker container from an image.
- `docker ps`: List running Docker containers.
- `docker ps -a`: List all Docker containers.
- `docker stop container_id`: Stop a running container.
- `docker rm container_id`: Remove a Docker container.
- `docker images`: List Docker images.
- `docker rmi image_id`: Remove a Docker image.
- `docker pull image`: Pull an image from a Docker registry.
- `docker push image`: Push an image to a Docker registry.
- `docker exec -it container_id command`: Execute a command in a running container.
- `docker logs container_id`: Fetch the logs of a container.
- `docker start container_id`: Start a stopped container.
- `docker stop container_id`: Stop a running container.
- `docker build`: Build an image from a Dockerfile.
- `docker pull image`: Pull an image or a repository from a registry.
- `docker push image`: Push an image or a repository to a registry.
- `docker export container_id`: Export a container’s filesystem as a tar archive.
- `docker exec`: Run a command in a run-time container.
- `docker search`: Search the Docker Hub for images.
- `docker attach container_id`: Attach to a running container.
- `docker commit container_id image`: Create a new image from a container’s changes.

---

## 3. Intermediate Docker Commands

- `docker run -d image`: Run a Docker container in detached mode.
- `docker run -p host_port:container_port image`: Map a port from the host to a container.
- `docker run -v host_volume:container_volume image`: Mount a volume from the host to a container.
- `docker run -e VAR=VALUE image`: Set environment variables in a container.
- `docker inspect container_id/image_id`: Return low-level information on Docker objects.
- `docker build -t tag .`: Build a Docker image with a tag from a Dockerfile in the current directory.
- `docker tag image new_tag`: Tag an image with a new tag.

---

## 4. Dockerfile Commands

- `FROM image`: Set the base image.
- `RUN command`: Run a command.
- `CMD command`: Set a default command to run when the container starts.
- `ENV VAR=VALUE`: Set environment variables.
- `ADD source destination`: Copy files from source to the container's filesystem at the destination.
- `COPY source destination`: Copy new files or directories from source and add them to the filesystem of the container at the destination.
- `ENTRYPOINT command`: Configure a container to run as an executable.
- `LABEL key=value`: Add metadata to an image.
- `EXPOSE port`: Inform Docker that the container listens on the specified network ports at runtime.
- `VOLUME`: Create a mount point with the specified name and mark it as holding externally mounted volumes from native host or other containers.
- `USER user`: Set the user name (or UID) and optionally the user group (or GID) to use when running the image and for any subsequent instructions.
- `WORKDIR path`: Set the working directory for any RUN, CMD, ENTRYPOINT, COPY, and ADD instructions that follow.
- `ARG`: Define a variable users can pass at build-time to the builder with the docker build command.
- `ONBUILD`: Add a trigger instruction when the image is used as the base for another build.

---

## 5. Docker Compose Commands

- `docker-compose up`: Create and start containers.
- `docker-compose down`: Stop and remove containers, networks, images, and volumes.
- `docker-compose build`: Build or rebuild services.
- `docker-compose logs`: View output from containers.
- `docker-compose restart`: Restart services.
- `docker-compose pause`: Pause services.
- `docker-compose unpause`: Unpause services.
- `docker-compose start`: Start existing containers for a service.
- `docker-compose stop`: Stop running containers without removing them.
- `docker-compose config`: Validate and view the compose file.

---

## 6. Docker Networking

- `docker network ls`: List networks.
- `docker network create network`: Create a network.
- `docker network rm network`: Remove a network.
- `docker network inspect network`: Display detailed information on one or more networks.

### Network Drivers

- **Bridge:** Docker's default networking driver.
- **Host:** Removes network isolation between the container and the Docker host.
- **Overlay:** Connects multiple Docker daemons together and enables swarm services to communicate with each other.
- **Macvlan:** Assigns a MAC address to a container, making it appear as a physical device on your network.

---

## 7. Docker Volumes

- `docker volume ls`: List volumes.
- `docker volume create volume`: Create a volume.
- `docker volume rm volume`: Remove a volume.
- `docker volume inspect volume`: Display detailed information on one or more volumes.

---

## 8. Docker Object Commands

- `docker image`: Manage images.
- `docker container`: Manage containers.
- `docker network`: Manage networks.
- `docker volume`: Manage volumes.
- `docker secret`: Manage Docker secrets.
- `docker plugin`: Manage plugins.

---

## 9. Docker Advanced Commands

- `docker history image`: Show the history of an image.
- `docker save image > file`: Save an image to a tar archive.
- `docker load < file`: Load an image from a tar archive.
- `docker commit container_id image`: Create a new image from a container’s changes.

---

## 10. Docker System Commands

- `docker info`: Display system-wide information.
- `docker version`: Show Docker version information.
- `docker system df`: Show Docker disk usage.
- `docker system events`: Get real-time events from the server.
- `docker system prune`: Remove unused data.

---

## 11. Docker Swarm Commands

- `docker swarm init`: Initialize a swarm.
- `docker swarm join`: Join a node to a swarm.
- `docker node ls`: List nodes in a swarm.
- `docker service create image`: Create a service.
- `docker service ls`: List services in a swarm.
- `docker service rm service`: Remove a service.
- `docker swarm`: Manage Swarm.
- `docker node`: Manage Swarm nodes.
- `docker stack`: Manage Docker stacks.
- `docker service`: Manage services.

### Container Orchestration with Docker Swarm

- **Services:** Define tasks to execute on the manager or worker nodes.
- **Tasks:** A single runnable instance of a service.
- **Worker Nodes:** Execute tasks dispatched from manager nodes.
- **Manager Nodes:** Execute Docker commands and authorize other nodes to join the swarm.
- **Raft Consensus Algorithm:** Used by manager nodes to agree on task scheduling and status updates.
- **Service Scaling:** Scale services up or down for optimal resource utilization.

---

## 12. Docker Security

- `docker secret create secret file`: Create a secret from a file.
- `docker secret ls`: List secrets.
- `docker secret rm secret`: Remove a secret.
- **Docker Security Scanning:** Security feature for Docker repositories.
- **Docker Content Trust:** Use digital signatures for data sent to and received from remote Docker registries.
- **Docker Secrets:** Manage sensitive data such as passwords, SSH private keys, and SSL certificates.

---

## 13. Docker Troubleshooting and Monitoring

- `docker stats`: Display a live stream of container resource usage statistics.
- `docker system df`: Display Docker disk usage.
- `docker inspect`: Return low-level information on Docker objects.
- `docker events`: Get real-time events from the server.
- `docker logs`: Fetch the logs of a container.
- `docker healthcheck`: Check the health of a running container.

---

## 14. Docker Registries and Repositories

- **Docker Hub:** Docker's public registry instance.
- **Docker Trusted Registry (DTR):** Commercially supported storage for Docker images.
- **Docker Content Trust (DCT):** Use digital signatures for data sent to and received from remote Docker registries.

---

## 15. Docker and CI/CD

- **Docker in Jenkins:** Jenkins provides built-in Docker integration for CI/CD workflows.
- **Docker in Travis CI:** Travis CI provides Docker integration for CI/CD workflows.
- **Docker in GitLab CI:** GitLab CI has native Docker support for CI/CD workflows.
- **Docker in CircleCI:** CircleCI offers Docker support to build and push Docker images.
- **Docker in Azure DevOps:** Azure DevOps can build, push, or run Docker images, or run a Docker command.

---

## 16. Docker and the Cloud

- **Docker on AWS:** Services like Amazon Elastic Container Service (ECS) and AWS Fargate for running Docker containers.
- **Docker on Azure:** Azure Kubernetes Service (AKS) for running Docker containers.
- **Docker on Google Cloud:** Google Kubernetes Engine (GKE) for running Docker containers.

---



## 17. Docker Best Practices

- **Container Immutability:** Never update a running container; always create a new one.
- **Single Process per Container:** Each container should address a single concern.
- **Minimize Layer Counts in Dockerfiles:** Fewer commands that create layers result in smaller images.
- **Leverage Build Cache:** Docker caches the results of the first build of a Dockerfile, allowing subsequent builds to be fast.
- **Use .dockerignore:** Prevent sending unnecessary files to the daemon when building images.
- **Use Specific Tags for Production Images:** Ensure application consistency by using specific image versions.
- **Always Use the Latest Version of Docker:** New versions include security improvements, bug fixes, and new features.

---

## 18. Docker and Microservices

- **Service Discovery:** Docker Swarm Mode has a built-in DNS server for resolving service names to IP addresses.
- **Service Scaling:** Scale services up or down in Docker Swarm Mode.
- **Load Balancing:** Docker's built-in load balancer distributes network connections to all instances of a replicated service.
- **Secure Communication:** Docker Swarm Mode's routing mesh provides secure communication between services.

---

## 19. Docker Plugins

- **Storage Plugins:** Provide storage capabilities to Docker containers.
- **Network Plugins:** Provide networking capabilities to Docker containers.
- **Authorization Plugins:** Restrict access to Docker APIs.

---

## 20. Docker API

- **Docker REST API:** Used by applications to interact with the Docker daemon.
- **Docker SDK:** SDKs for Go and Python built on top of the Docker REST API.
- **Docker Engine API:** Used by Docker clients to communicate with the Docker daemon.

---

## 21. Docker Editions

- **Docker Community Edition (CE):** Ideal for individual developers and small teams experimenting with container-based apps.
- **Docker Enterprise Edition (EE):** Designed for enterprise development and IT teams building, shipping, and running business-critical applications at scale.

---

## 22. Docker Architecture

- **Docker Engine:** A client-server application with a server, a REST API, and a command-line interface (CLI).
- **Docker Daemon:** Manages Docker objects such as images, containers, networks, and volumes.
- **Docker Client:** The primary way users interact with Docker. Commands sent by the client are executed by the Docker daemon.
- **Docker Images:** Ordered collections of root filesystem changes and execution parameters for use within a container runtime.
- **Docker Containers:** Runnable instances of images. Managed via Docker API or CLI.
- **Docker Services:** Allow scaling containers across multiple Docker daemons, forming a swarm with multiple managers and workers.

---

Created by: **Barath kumar**

Feel free to contribute and improve this cheat sheet by creating pull requests or opening issues.

---

Happy Dockering!

---

*Note: The commands and concepts listed here are essential for working with Docker. For comprehensive usage and additional options, refer to the [Docker documentation](https://docs.docker.com/).*

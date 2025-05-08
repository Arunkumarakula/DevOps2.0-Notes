## Monolithic Architecture

A monolithic application is built as a single unified unit where all components such as the frontend, backend, and database—run together as one service.

**Advantages:**

- Simple to develop and test initially.
- Easier debugging and logging.

**Disadvantages:**

- A small change requires redeploying the whole application.
- Hard to adopt new technologies without rewriting large parts.

## Microservices Architecture

A microservices architecture breaks the application into smaller, independent services, each handling a specific function and communicating via APIs.

**Advantages:**

- Easier to scale and deploy individual services.
- More flexibility in using different technologies.

**Disadvantages:**

- More complex to design and manage.
- Requires DevOps practices for CI/CD, monitoring, etc.

## Virtualization vs Containerization

Virtualization and containerization are both methods of running multiple applications on a single physical server, but they differ in how they isolate and share resources.

### 1. Virtualization

Virtualization uses a hypervisor to create virtual machines, each with its own operating system.

* **Hypervisor**: A hypervisor is software that manages the virtual machines and allocates resources like CPU, memory, and storage.

**Advantages:**

- Full isolation and security.
- Supports multiple OS types on one physical machine (e.g., Linux and Windows).

### 2. Containerization

Containerization packages an application and its dependencies into a container, which shares the host operating system's kernel.

* **Docker**: Docker is a popular containerization platform.

**Key Docker Components:**

1.  **Docker Client**: The Docker client is the primary way that many Docker users interact with Docker. When you use the `docker` command, the client sends these commands to a Docker daemon (`dockerd`) which carries them out. The Docker command line interface (CLI) uses the Docker Engine API.

2.  **Docker Daemon**: Docker Daemon is the background service that manages Docker containers. It listens for Docker API requests and handles tasks such as building, running, and distributing containers.
    -   Interacts with Docker objects like images, containers, networks, and volumes.

3.  **Docker Host**: A Docker host is the physical or virtual machine that runs the Docker daemon (`dockerd`) and manages Docker containers.
    -   It provides the environment necessary to build, run, and manage containers, including the operating system, networking, and storage.

4.  **Docker Registry**: A Docker Registry is a centralized system for storing and distributing Docker images. It allows you to push and pull container images.

5.  **Docker Image**: A Docker image is a read-only template that contains the code, libraries, and dependencies needed to create and run a Docker container.

6.  **Docker Container**: A Docker container is a lightweight and isolated environment that is used to run an application. It packages an application including dependencies, libraries, and settings.

## Base Image

A base image is like a foundation for creating a Docker container. It's a pre-built image that includes an operating system, and we can build our own app on top of it, like adding code, dependencies, and libraries.
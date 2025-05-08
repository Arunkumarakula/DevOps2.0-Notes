*Monolithic Architecture: monolithic application is built as a single unified unit where all components such as the frontend, backend, and database run together as one service.

**Advantages**:
- Simple to develop and test initially.
- Easier debugging and logging.

**Disadvantages**:
- A small change requires redeploying the whole application.
- Hard to adopt new technologies without rewriting large parts.


* Microservices Architecture: A microservices architecture breaks the application into smaller, independent services, each handling a
                                specific function and Communicate via APIs.

**Advantages**:
- Easier to scale and deploy individual services.

- More flexibility in using different technologies.

**Disadvantages**:
- More complex to design and manage.

- Requires DevOps practices for CI/CD, monitoring, etc.


* Virtualization vs containerization: Virtualization and containerization are both methods of running multiple applications on a single
                                      physical server, but they differ in how they isolate and share resources.

1. **Virtualization**:  Virtualization uses a hypervisor to create virtual machines each with its own operating system.

  * **Hypervisor**: A hypervisor is software,that manages the virtual machines and allocates resources like CPU, memory, and storage.

**Advantages**:
- Full isolation and security.
- Supports multiple OS types on one physical machine (e.g., Linux and Windows).

**Disadvantages**:
- High overhead (RAM, CPU).
- Slower performance.
- Larger image size (in GBs).

  * **Containerization**: Containerization is a method of running applications in isolated, lightweight environments called containers,that share the host operating system.

  - Uses tools like Docker, Podman, or Kubernetes.

**Advantages**:
- Faster startup and shutdown.
- Lightweight (smaller image sizes).
- Easier to scale and deploy.
- Ideal for microservices.

**Disadvantages**:
- Less isolation than VMs (depends on kernel security).
- All containers must run on the same OS type as the host.

* Docker : Docker is a tool that allows the package an application with all its dependencies (like code, libraries, tools, settings) into
          lightweight container so it can run any Environments(Linux, Mac, windows).

**Advantages**:
 - Docker is portable, you can your application on any environment.
 - Docker is lightweight, uses less memory and storage than a traditional virtual machines.
 - Apps can run independently in containers.
 - Integrates well with automation pipelines.
 - Each Docker container runs in isolation, preventing conflicts between different applications.
 - Docker reduce infrastructure cost by optimizing resource utilization, allowing for running multiple workloads on same hardware and
   enabling faster deployments.


* Docker Architecture :

When a user enters the command `docker run <image-name>`, the Docker client communicates with the Docker daemon. The daemon first checks if the image is available locally. If it is, the daemon runs the image; if not, it pulls the image from the Docker registry before running it.

1. **Docker Client**: Docker Client is the command-line interface(CLI) or graphical interface that allows users to interact with the Docker
                 system. Accepts commands like `docker run`, `docker build`, and `docker pull`, and communicates with the Docker daemon via the
                 Docker Engine API.

2. **Docker Daemon**: Docker Daemon is the background service that manages Docker containers.Listens for Docker API requests and handles tasks
                 such as building, running, and distributing containers.
                 - Interacts with Docker objects like images, containers, networks, and volumes.

3. **Docker Host**: A Docker host is the physical or virtual machine that runs the Docker daemon(`dockerd`) and manages Docker containers.
                 - It provides the environment necessary to build, run, and manage containers, including the operating system, networking,
                  storage.

4. **Docker Registry**: A Docker Registry is a centralized system for storing and distributing Docker images. It allows you to push and pull
                    container images.

5. **Docker Image**: Docker image is a read only template that contains the code, Libraries and dependencies needed to create and run a
                  docker container.

6. **Docker Container**: A Docker container is a lightweight and isolated environment that is used to run an application, it packages an
                     application including dependencies, libraries, and settings.


* Base Image : A base image like a foundation for creating a docker container. It's  pre-built image that includes an operating system and
              we can build our own app on top of it like add code, Dependencies and libraries.
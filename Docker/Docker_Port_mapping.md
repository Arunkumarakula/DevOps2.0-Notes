# Port mapping

Port mapping in Docker is the process of assigning a port on the host machine to inside a container application, to access the application from outside of docker.

- By default, the container’s internal port is hidden inside Docker.

## Why Port Mapping

- Containers are isolated Each Docker container runs its own network environment.  
- Without port mapping, container apps cannot be accessed from outside Docker.  
- This allows external access (like from browsers) to the container app.

## How does the traffic flow from outside to inside the container via port mapping

**External request:**  
You access the host machine’s port, for example, http://localhost:8080.

**Host machine:**  
Your host machine listens on port 8080.

**Docker port mapping:**  
Docker forwards any traffic coming to host port 8080 to the container’s internal port, for example, port 80.

**Inside the container:**  
The application inside the container listens on port 80 and responds.

**Response sent back:**  
The response travels back the same way from the container’s port 80 → host port 8080 → your browser or external system.

## In Docker, there are two main types of port mapping:

### 1. Port Forwarding (-P)  
- Docker automatically assigns a random port on your host machine to the container’s exposed port.  
- You use the -P (capital P) option.  
- Port Forwarding is also known as Dynamic port forwarding.

**Example:**  
```bash
docker run -P nginx
````
* After running the container, use this command to hecck the random port is assigned or not.
```bash
docker port my-nginx
```

* If Nginx exposes port 80, Docker might map it to something like 32768 on the host.
* Random port (check via docker port).

✅ **Use When:**

* You don't care which host port is used.
* You're testing or running multiple containers without port conflicts.

### 2. Port Assigning (-p)

* You manually specify which host port should connect to which container port (will assign a custom port).
* Use the -p (small p) option.

**Example:**

```bash
docker run -p 8080:80 nginx
```

* This maps host port 8080 → container port 80.

✅ **Use When:**

* You want predictable, fixed ports (e.g., in production).

---

## LAB :

### Run an Nginx container mapping host port 8080 to container port 80

```bash
docker run -d -p 8080:80 --name my-nginx nginx
```

* `-d` runs the container in detached mode (in the background).
* `-p 8080:80` maps host port 8080 to container port 80.
* `nginx` is the official image from Docker Hub.

### Run Nginx container without port mapping

```bash
docker run -d --name my-nginx nginx
```

* No `-p` option means no ports are exposed to the host.
* You cannot access the Nginx server via localhost or the host IP.


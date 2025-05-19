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
docker port nginx
```
* Now we can see that the port like Example :
```bash
80/tcp -> 0.0.0.0:49153
```
➡️ This means:
* The container's port 80 is mapped to host port 49153.
* You can access the app using: http://localhost:49153

### Alternative: Use docker ps
```bash
docker ps
```
Look in the "PORTS" column. It will show something like:
```bash
0.0.0.0:49153->80/tcp
```

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
* Now we can the port using
```bash
docker port nginx
```
(or)
```bash
docker ps
```
Output :
```bash
80/tcp -> 0.0.0.0:8080
````
* This maps host port 8080 → container port 80.

✅ **Use When:**

* You want predictable, fixed ports (e.g., in production).

---

## LAB :

### create a custom Apache HTTP Server (httpd) image, assign a port, and deploy a colorful HTML page :
#### 🔧 Step-by-Step Guide :

##### step 1: Create Your Project Structure
```bash
mkdir Basic-Docker-Project
cd Basic-Docker-Project
```
```bash
vi index.html
```
- In the index.html file we can paste a basic html code, you can refer this code.
```bash
<!DOCTYPE html>
<html>
<head>
    <title>Colorful Apache Page</title>
    <style>
        body {
            background: linear-gradient(to right, #ff758c, #ff7eb3);
            color: white;
            font-family: Arial, sans-serif;
            text-align: center;
            padding-top: 100px;
        }
        h1 {
            font-size: 3rem;
            text-shadow: 2px 2px #000;
        }
        p {
            font-size: 1.2rem;
        }
    </style>
</head>
<body>
    <h1>Keep Learning Keep Growing</h1>
    <p>Happy Learning</p>
</body>
</html>
```
##### step2: Run Apache container with your HTML mounted and port mapped
```bash
docker run -d -p 8080:80 -v $(pwd):/usr/local/apache2/htdocs/ --name my-httpd-container httpd
```
- -d → run container detached (in background)
- -p 8080:80 → map your machine’s port 8080 to the container’s port 80 (Apache’s default)
- -v $(pwd):/usr/local/apache2/htdocs/ → mount your current folder (my-httpd-site) as the web root in the container
- httpd → official Apache HTTP Server image.

#### Step 3: Open your browser

```bash
docker run -d -p 8080:80 --name mypractice httpd
```
Check the port using :
```bash
docker ps (or) docker port httpd
```

* `-d` runs the container in detached mode (in the background).
* `-p 8080:80` maps host port 8080 to container port 80.
* `httpd` is the official image from Docker Hub.

### Run httpd container without port mapping
```bash
http://localhost:8080
```
---
#### Step-By-Step process:

![Image](https://github.com/user-attachments/assets/a930c8fd-9c16-4832-801b-2ed887d4d189)

- Index.html file which conatins html-code
![Image](https://github.com/user-attachments/assets/7aabe234-11ab-4fd8-bc38-909fb80abf48)

- After Running a container we can access the application using Ip-address, we can this output.
![Image](https://github.com/user-attachments/assets/a930c8fd-9c16-4832-801b-2ed887d4d189)


# Dockerfile

A **Dockerfile** is a text file that contains a set of instructions used to automate the creation of a Docker image.

* Each instruction in a Dockerfile creates a layer in the image.
* Each instruction tells Docker what to do like: Start from a base image, Install software, Copy files.
* Docker reads the Dockerfile line by line to build the image.

**Note:** You don’t share the Dockerfile across containers, but you use it to build a Docker image, and that image can be shared and used to run multiple containers.

---

## 📜 Dockerfile Instructions :

### 1. FROM

The FROM command in a Dockerfile sets the base image to build your Docker image.

* The FROM instruction is the first and most important command in a Dockerfile.
* The FROM command sets the base image for the Docker image - which we are going to build.
* It tells Docker: Start building this image using another existing image as a base.

**Syntax:**

```
FROM <image-name>:<tag>
```

**Example:**

```
FROM ubuntu:20.04
```

* You Can Use Official images like: ubuntu, alpine, node, python, nginx.

---

### 2. RUN

The RUN instruction is used to execute commands while building the Docker image.

* It runs a command inside the image during the build process.
* Commonly used to install software, update packages.

**Example:**

```
RUN apt-get update && apt-get install -y nginx
```

---

### 3. COPY

The COPY instruction copies files or folders from your local machine into the Docker image.

**Syntax:**

```
COPY <source> <destination>
```

**Example:**

```
COPY . /app
```

---

### 4. ADD

The ADD instruction copies files or directories from your local system into the Docker image like COPY, but it also has some extra features.

* Can also download files from a URL.
* Automatically extracts compressed files (like .tar, .gz)

**Example:**

```
 ADD https://example.com/big.tar.gz /var/www/html/
```

---

### 5. CMD

CMD in a Dockerfile specifies the default command that runs when a container starts

* This command is executed when you run the container. Only one CMD is allowed; if you specify multiple, only the last one is used.

**Example:**

```
CMD ["python", "app.py"]
```

* Runs the Python script named app.py when the container starts.

---

### 6. ENTRYPOINT

---

### 7. WORKDIR

WORKDIR sets the working directory inside the container.

* If the directory doesn’t exist, Docker will create it.

**Example:**

```
WORKDIR /usr/src/app
```

---

### 8. EXPOSE

EXPOSE tells Docker which network ports the container will listen on at runtime.

**Example:**

```
EXPOSE 80
```

---

### 9. VOLUME

Creates a mount point for volumes to persist data.

* Specifies that the directory should be stored outside the container filesystem, useful for persistent storage.

**Example:**

```
VOLUME /data
```

---

### 10. ENV

Sets environment variables inside the container.

* Defines environment variables which can be accessed by applications running in the container.

**Example:**

```
ENV NODE_ENV=production
```



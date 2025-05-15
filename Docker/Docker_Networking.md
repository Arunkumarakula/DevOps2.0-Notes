# *Docker Network* 

Docker networking is how Docker containers communicate with each other, with the host machine, and with the outside world (internet or other networks).  
→ When you create containers, Docker automatically connects them to a default network unless you specify otherwise.  
→ You can also create custom networks to control how containers talk to each other.

## ➤ Why is Docker Networking: 
→ Enables communication between containers (e.g., web server container talking to a database container).  
→ Defines how and which container ports are published to the outside world.  
→ Provides isolation and security between containers.

## ➤ Types of Docker Networks : Docker has 4 main types of networks by default.

### 1. **bridge (default) network**  
Bridge network is Docker’s default private network where containers on the same host can communicate with each other using IP addresses.  
→ When you start a container without specifying a network, it connects to this default bridge network.  
→ Requires port mapping to access containers externally.

**why**:  
→ To isolate container traffic from the host and other networks.  
→ To allow containers on the same host to communicate securely.

### 2. **host network**  
The container shares the host’s networking namespace. No network isolation, the container uses the host’s IP address and ports directly.  
→ Ports do not need to be published explicitly.

**why**:  
→ When a container needs direct access to the host’s network interfaces.  
→ For applications that require low latency.

### 3. **none network**  
The container has no network  
→ Container is completely isolated from any network.  
→ No communication with other containers or the outside world.

**why**:  
→ Useful for running containers without network access.

### 4. **overlay network**  
Enables communication between containers running on different Docker hosts.  
→ Used mainly in Docker Swarm or Kubernetes clusters.

**why**:  
→ For multi-host container deployments, such as in orchestration platforms or clusters.

> **Note**: You cannot remove Docker’s default networks (bridge, host, and none) because they are built-in and essential for Docker to function properly.

---

# *Commands*

## **Bridge network** :

➤ When you run a container without specifying a network, Docker connects it to the default bridge network.  
**command**:  
```bash
docker run -d --name mycontainer nginx
````

➤ Custom bridge network with a specific name
**command**:

```bash
docker network create --driver bridge <your-network-name>
# eg:
docker network create --driver bridge my-bridge-net
```

> Verify the Network using `docker network ls` command or
> `docker network inspect my-bridge-net` this shows details like connected containers, subnet, gateway, etc.

➤ To disconnect a container from a bridge network
**command**:

```bash
docker network disconnect <network-name> <container-name>
# eg:
docker network disconnect my-bridge-net web1
```

➤ Command to remove a custom network
**command**:

```bash
docker network rm <network-name>
# eg:
docker network rm my-bridge-net
```

---

## **Host Network** :

→ You cannot create a new host network in Docker because the host network is a special built-in network
→ We can use the existing host network when running containers.

➤ Command to run a container with host network:

```bash
docker run --name my-host-container --network host nginx
```

➤ Disconnect container from Host Network
→ You cannot disconnect a container from the host network once it is running with it because the host network mode is a special built-in mode.
→ If we want to disconnect, stop and remove the container.

**commands**:

```bash
docker stop my-container  
docker rm my-container
```

→ Run it again with a different network, like bridge or a custom one.
**command**:

```bash
docker run --name my-container --network bridge nginx
```

---

## **none network** :

➤ How to run a container with none network.
**command**:

```bash
docker run --name isolated-container --network none alpine
```

➤ You cannot remove the default none network in Docker.

```

Let me know if you'd like this saved to a file or further customized!
```

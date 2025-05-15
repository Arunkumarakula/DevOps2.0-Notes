* **Docker Network:**

Docker networking facilitates communication between Docker containers, the host machine, and external networks.
→ Docker automatically connects containers to a default network unless specified.
→ Custom networks can be created for controlled inter-container communication.

➤ **Why is Docker Networking:**
→ Enables **communication between containers**.
→ Defines **port publishing** to the outside world.
→ Provides **isolation and security** between containers.

➤ **Types of Docker Networks:** Docker has 4 main default network types.

    1. **bridge (default) network**: Docker’s default private network for communication between containers on the same host using IP addresses.
        → Default connection for containers without specified networks.
        → Requires **port mapping** for external access.

        **why**:
        → To **isolate container traffic** from the host and other networks.
        → To allow **secure communication** between containers on the same host.

    2. **host network**: Container shares the host’s networking namespace. **No network isolation**, uses the host’s IP address and ports directly.
        → **No explicit port publishing needed**.

        **why**:
        → For containers needing **direct access** to the host’s network interfaces.
        → For applications requiring **low latency**.

    3. **none network**: Container has **no network**.
        → Completely **isolated** from any network.
        → **No communication** with other containers or the outside world.

        **why**:
        → Useful for running containers **without network access**.

    4. **overlay network**: Enables communication between containers running on **different Docker hosts**.
        → Primarily used in **Docker Swarm or Kubernetes clusters**.

        **why**:
        → For **multi-host container deployments**, such as in orchestration platforms or clusters.

**Note**: Default networks (**bridge, host, and none**) **cannot be removed**.

* **Commands:**

**Bridge network:**
➤ Running a container on the default bridge network:
    `docker run -d --name mycontainer nginx`

➤ Creating a **custom bridge network**:
    `docker network create --driver bridge <your-network-name>`
    `eg : docker network create --driver bridge my-bridge-net`

    Verify with: `docker network ls` or `docker network inspect my-bridge-net`

➤ **Disconnecting** a container from a bridge network:
    `docker network disconnect <network-name> <container-name>`
    `eg : docker network disconnect my-bridge-net web1`

➤ **Removing** a custom network:
    `docker network rm <network-name>`
    `eg : docker network rm my-bridge-net`

**Host Network:**

    → **Cannot create a new host network**. It's a built-in network.
    → Use the existing host network when running containers.

➤ Running a container with **host network**:
    `docker run --name my-host-container --network host nginx`

➤ **Disconnecting** container from Host Network:
    → **Cannot disconnect** while running.
    → **Stop and remove** the container to change the network.
    `docker stop my-container`
    `docker rm my-container`
    → Run again with a different network:
    `docker run --name my-container --network bridge nginx`

**none network:**

➤ Running a container with **none network**:
    `docker run --name isolated-container --network none alpine`

➤ **Cannot remove** the default none network.
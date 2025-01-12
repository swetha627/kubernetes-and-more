
# Basic and Docker Commands

## Basic Commands

### User Management
- **Create a user with a home directory and bash shell:**
  ```bash
  sudo useradd -m -s /bin/bash <username>
  ```
  - `-m` flag creates a home directory for the user.

- **Delete a user:**
  ```bash
  sudo userdel <username>
  ```

### Shell and System Information
- **Print current shell:**
  ```bash
  echo $SHELL
  ```
- **Print hostname:**
  ```bash
  hostname
  ```
- **Print operating system:**
  ```bash
  uname -s
  ```
- **Print system architecture:**
  ```bash
  uname -m
  ```

### Networking Commands
- **Show network configuration:**
  ```bash
  ifconfig
  ```
- **List all ports being used:**
  ```bash
  netstat -a
  ```
- **List all listening TCP/UDP ports (numerical form):**
  ```bash
  netstat -tuln
  ```
- **List IPs of a domain:**
  ```bash
  nslookup
  ```

### File Search
- **Find a file:**
  ```bash
  find / -name <filename>
  ```
  - `/` searches through everything from the root directory.

### Environment Variables
- **Set an environment variable:**
  ```bash
  export ENVNAME=VALUE
  ```

### Memory and Processes
- **Show free memory (in MB):**
  ```bash
  free -m
  ```
- **Interactive process viewer:**
  ```bash
  htop
  ```

## Docker Commands

### General Docker Information
- **Check Docker version:**
  ```bash
  docker version
  ```
- **Get detailed Docker information:**
  ```bash
  docker info
  ```

### Images
- **List Docker images:**
  ```bash
  docker images
  ```
- **Remove a Docker image:**
  ```bash
  docker rmi <image>
  ```
- **Tag a Docker image:**
  ```bash
  docker tag <source-image> <target-image>
  ```
- **Build a Docker image:**
  ```bash
  docker build -t <image-name> .
  ```
- **Push a Docker image to a repository:**
  ```bash
  docker push <image-name>
  ```

### Containers
- **Run a container:**
  ```bash
  docker run <image-name>
  ```
- **Run a container with a custom name:**
  ```bash
  docker run --name myapp <image-name>
  ```
- **Run a container with an environment variable:**
  ```bash
  docker run -e ENV_NAME=VALUE <image-name>
  ```
- **Run a container using an environment file:**
  ```bash
  docker run --envfile env.list <image-name>
  ```
- **Run a container in detached mode:**
  ```bash
  docker run -d <image-name>
  ```
  - Detached mode: You won’t see logs on the screen but can use `docker logs` or `docker exec` to check them.
- **Run a container in interactive mode (default):**
  ```bash
  docker run -it <image-name>
  ```

### Container Management
- **Stop a container:**
  ```bash
  docker stop <container-id>
  ```
- **Start a container:**
  ```bash
  docker start <container-id>
  ```
- **Remove a container:**
  ```bash
  docker rm <container-id>
  ```

### Inspecting and Accessing Containers
- **Access a running container:**
  ```bash
  docker exec -it <container-id> -- /bin/bash
  ```
- **View container logs:**
  ```bash
  docker logs <container-id>
  ```
- **Inspect container details:**
  ```bash
  docker inspect <container-id>
  ```

### Listing Containers
- **List running containers:**
  ```bash
  docker ps
  ```
- **List all containers (including stopped):**
  ```bash
  docker ps -a
  ```

### Networking
- **List Docker networks:**
  ```bash
  docker network ls
  ```
  - Types of networks: Bridge, Overlay, Host, None (different scopes of access).
- **Create a Docker network:**
  ```bash
  docker network create <network-name>
  ```
- **Connect a container to a network:**
  ```bash
  docker network connect <network-name> <container-name>
  ```

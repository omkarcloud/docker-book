---
sidebar_position: 20
---

# Container and Image
## Understanding Images
At the heart of Docker's architecture lies the concept of images. An image is a lightweight, standalone, and component that contains everything necessary to run an application, including the code, runtime, system tools, system libraries, and configurations.

Think of images as blueprints or templates from which containers are created. They are designed to be immutable, meaning they cannot be changed once created. Any modifications to an image result in the creation of a new image. This immutability ensures consistency and reproducibility in the software development and deployment processes.


## Images and Containers Analogy
To better grasp the relationship between images and containers, let's consider an analogy. 

Consider Images as blueprints and containers as objects. An image serves as a blueprint that defines the environment and configuration needed to run an application within a container. It encapsulates all the necessary dependencies and instructions.

Similarly, just as multiple objects can be created from a single blueprint, multiple containers can be instantiated from a single image.


## DockerHub
Similar to how we have github to store Code Repositories. Docker Inc, created DockerHub to store Images.

DockerHub is a widely used cloud-based registry where developers can discover, share, and distribute Docker images. It acts as a central repository for both official and community-built images.

DockerHub provides a vast collection of pre-built images, including popular software stacks, operating systems, and frameworks. With DockerHub, you can easily search for images, pull them to your local system, and use them as a base for your containers.

It also promotes collaboration and allows developers to share their own custom images with others.

> Please note that, besides Docker, there are other image repositories available, such as GCR (Google Container Registry), which serve as repository for container images.

## Container Tutorial 

In this section, we will provide a detailed tutorial on creating and managing containers using Docker. 

We will cover different aspects of container management, including creating a container, stopping a container, restarting a container, deleting a container, bashing into a container, and mapping ports in a container.

### **Running a Container**

To start a container, you can use the command **`docker run <image-name>`**. This will create and launch a new container using the specified image.

For example, if you want to run a container with the Alpine image, you can use the following command:

```
docker run alpine:3.14
```

Every Docker image has a tag, similar to semantic versions in npm packages.

> The Alpine image is a lightweight Linux distribution known for its small size, typically ranging from 5MB to 10MB. It is commonly used in Docker containers due to its efficiency.


### **Viewing Running Containers**

To see the list of running containers, you can use the command **`docker ps -a`**. This will display details about all the running containers, including their container ID, image name, the command used to start them, creation time, and status.

Here is the syntax to view the running containers:

### **Stopping a Container**

Each container has a unique ID, which you can find by running **`docker ps -a`** command. To stop a container, use the following command:

```
docker stop <container-id>
```

### **Restarting a Container**

To restart an existing container, use the following command:

```
docker restart <container-id>
```

### **Deleting a Container**

To delete an existing container, use the following command:

```
docker rm <container-id>
```

### **Accessing a Container's Shell**

Sometimes you may need to access a container's shell. You can achieve this using the **`docker exec`** command:

```
docker exec -it <container-id> sh
```

Here, the **`-it`** option runs the command in interactive and tty mode, and **`sh`** specifies the shell to be used.

### **Mapping Ports in a Container**

To map ports in a container, you can use the **`-p`** flag. For example, if you are running a Node.js application and want to map the host port `3000` to the container's port `3000`, you would use the following command:

```
docker run -p 3000:3000 <image-name>
```

This command maps the host port `3000` to the container's port `3000`.


> A helpful tip to remember the mapping order is to consider that "host" contains "docker" Therefore, when mapping ports, the host port comes first, followed by the Docker container's port.


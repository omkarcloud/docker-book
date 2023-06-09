---
sidebar_position: 10
---

# Docker

## What is Docker?

In the early days, running a new application meant acquiring a whole new server since one server could only run a single application.

However, everything changed when VMware, Inc. introduced the virtual machine (VM) - a game-changing gift to the world. With VMs, multiple applications could be run on a single server, revolutionizing the way companies utilized their infrastructure.

However, there was still a catch. Each VM required its own dedicated operating system (OS), resulting in the consumption of valuable CPU and RAM resources that could have been utilized by the applications themselves.

This limitation prompted tech giants like Google to explore an alternative solution: Containers. Similar to VMs, containers allowed for running multiple applications, but they didn't require a full-fledged OS. As a result, containers freed up significant amounts of system resources such as CPU and RAM.

However, there was a hurdle to using containers - it required the expertise of Linux Kernel Engineers, making it inaccessible to the masses.

Then, along came a company called dotCloud Inc, founded by Solomon Hykes, a French-American innovator. They introduced Docker, a groundbreaking technology that made containers easy to use.

Docker's user-friendly approach simplified the management and deployment of containers, breaking down barriers and making containers accessible to everyone.

This democratization of containers opened up new possibilities for developers and businesses alike, empowering them to leverage the benefits of containerization without the need for specialized expertise.

Thanks to Docker's ease of use, the world witnessed a shift towards widespread adoption of containers, transforming the landscape of application development and deployment.

Docker's impact on the industry has been profound, empowering the masses and unleashing the full potential of containerization.

<!-- TODO: Needs work to make it interesting -->
## Why we need Docker?

The need for Docker arises when faced with the challenge of setting up an end-to-end stack involving multiple technologies.

Consider a scenario where you have to configure a stack consisting of a Node.js-based web server, databases like MongoDB or CouchDB, a messaging system like Redis, and an orchestration tool such as Ansible. Developing an application with such diverse components presents various issues.

Firstly, ensuring compatibility between the components and the underlying operating system becomes crucial. It can be difficult to find an OS compatible with all the required services, as certain versions may not align with the chosen OS. This compatibility matrix issue, often referred to as the "matrix from hell," poses significant obstacles.

Secondly, compatibility concerns between the services, libraries, and OS dependencies must be addressed. Different services may require specific versions of dependent libraries, creating conflicts. As the application's architecture evolves, upgrades or changes to components and databases necessitate repeating the process of verifying compatibility with the underlying infrastructure.

Moreover, setting up new development environments for each new developer becomes a challenging task. Extensive instructions and numerous commands must be followed to ensure the correct operating system and component versions are used. Additionally, the presence of different development, test, and production environments using various operating systems creates inconsistencies and uncertainty regarding application performance across these environments.

To overcome these challenges, Docker provides a solution. By running each component in a separate container with its own libraries and dependencies, Docker allows isolation within the same VM and OS. Docker configuration only needs to be built once, enabling developers to initiate development with a simple "docker run" command.

Regardless of the underlying OS, as long as Docker is installed, developers can easily set up their environments, alleviating compatibility concerns and streamlining the development, building, and shipping processes.


## People behind Docker
Docker, is created by real breathing humans. As the author, it is important for me to acknowledge their contributions and ensure they receive the credit they deserve. Here are key People who played an important role in giving us Docker.

**Solomon Hykes**

Solomon Hykes is founder of dotCloud Inc which later became Docker. He initially released Docker as an open-source project in 2013.He served as the CTO and Chief Product Officer of Docker, Inc. (previously known as dotCloud, Inc.) until 2018.

**Ben Golub**

Ben Golub served as the CEO of Docker, Inc. from 2013 to 2017. He played a significant role in Docker's early success, helping to secure funding and scale the company. Golub focused on growing Docker's community and establishing partnerships with various organizations to promote the adoption of containerization.



## How to install Docker 

There are two methods you can utilize to use Docker. I will provide you with an approach that is suitable even for devices with limited specifications, such as 1GB RAM and an i3 processor.

1. Install Docker on your operating system:
You can install Docker on your PC similar to how you install other software. To follow this method, search "install Docker Linux/Mac/Windows" on Google. This will provide you with step-by-step instructions tailored to your specific operating system.

2. Make Project on Gitpod:
Another option is to use Gitpod, a cloud-based Integrated Development Environment (IDE) that offers developers pre-configured development environments accessible through a web browser. 

These environments come equipped with Docker, Docker Compose, Python, and Node.js already installed. 

Gitpod offers high-performance cloud machines equipped with powerful hardware and fast internet connectivity, reaching hundreds of megabytes per second.

:::info  

In General, Gitpod is actually a very good place to write code if you come from rural places in India or Africa which does not have Good Internet Speed or you have a low end device.

:::

To get started, create a project on gitpod.io, and Gitpod will automatically provision a machine with Docker pre-installed and ready to use.


## Next Steps

Now that you have a basic understanding of Docker, let's progress further and learn about Containers something that is very Central to Docker.
---
sidebar_position: 30
---

# Dockerization

## Understanding Dockerization

Now, we will understand what is Dockerization.

Dockerization is the process of packaging an application and its dependencies into a image which can be used to create Containers.

For example, when you have created your React application. Then to run it in a container. You need to Dockerize the React application before running it in Container. 

The General Process of Dockerization is as follows: 

- **Create a Dockerfile**: A Dockerfile is a text file that contains instructions for building a Docker image. It specifies the base image, application dependencies, environment variables, and other configurations needed for the container.

- **Build the Docker Image**: Use the Dockerfile to build a Docker image by running the docker build command. This process involves pulling the base image, installing dependencies, and configuring the container.


### Setting Up Dockerfile

Let's walk through an example of Dockerizing a React application.

To Dockerize your React application, follow these steps:

1. Create a Dockerfile by running the following command:
```
touch Dockerfile
```

2. Open the Dockerfile and add the following line:
```
FROM node:16-alpine
```
This line specifies the base image as the official Node.js Alpine Linux image. Alpine Linux is chosen for its small size.

3. Set the working directory in the Dockerfile:
```
WORKDIR /app
```
The `WORKDIR` instruction sets the working directory to `/app`. If the directory doesn't exist, it will be created.

4. Copy the `package.json` and `package-lock.json` files to the working directory, and install the application's dependencies:
```
COPY package.json package-lock.json .
RUN npm run install
```
These lines ensure that your application's dependencies are installed properly during the Docker image build process.

5. Copy the entire application code to the working directory:
```
COPY . .
```
This step copies all the files and folders from your current directory to the Docker image's `/app` directory.

6. Build the React app inside the Docker image:
```
RUN npm run build
```
This line builds the React app using the defined scripts in the `package.json` file.

7. Expose the port that the application will run on:
```
EXPOSE 3000
```
The `EXPOSE` instruction informs Docker that the application within the container will listen on port 3000.

8. Specify the command to start the application:
```
CMD npm run start
```
This line defines the command to be executed when the container is launched, which starts the application.

The complete Dockerfile should look like this:

```
FROM node:16-alpine
WORKDIR /app
COPY package.json package-lock.json .
RUN npm run install
COPY . .
RUN npm run build
EXPOSE 3000
CMD npm run start
```

### Building the Docker Image

Now that the Dockerfile is complete, you can build the Docker image using the following command:
```
docker build -t react-app .
```
This command builds the Docker image using the instructions specified in the Dockerfile. The `-t` flag assigns a tag (name) to the image, in this case, "react-app".

If the build succeeds, you will see relevant messages in the command's output.

You can use the `docker images` command to view basic information about the created image.

### Running the Docker Image in a Container

To run your Docker image inside a container, use the following command:
```
docker run -p 3000:3000 react-app
```
This command starts a container based on the "react-app" image and binds port 3000 in the container to port 3000 on the host machine.

Once the container is running, you can access your React application through http://localhost:3000.


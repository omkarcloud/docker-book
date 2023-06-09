---
sidebar_position: 40
---

# Volume

## What are Volumes
Men may come and men may go but the Knowledge that is passed to the next generation continues to live.

SimilarLY containers may be created and containers may be deleted, but sometimes we need to persist the data within the container.

For instance, suppose our backend is storing user data in a SQLite file. We want to ensure that the SQLite file persists even if the container is deleted.

To achieve this, we use volumes. Volumes allow us to persist data on the host machine associated with the container. Even if the container is removed, the data remains persisted on the host. Volumes work in a bi-directional manner: any file created in the host will be copied to the container, and any file created in the container will be copied to the host.

## Example

Let's illustrate this with an example. We will create an Alpine container and persist all the data stored in the "app-data" folder. To accomplish this, run the following command:
```
docker run -v /host/path:/container/path alpine
```
You remember the analogy that hosts has docker. So the part before ":" refers to the host path and path after ":", refers to the path in container.

Now, let's test whether the data is being persisted. First, we'll create a file in the host and verify that it gets copied into the container. Then, we'll create a file in the container and see that it gets copied to the host.

## Creating a File in the Host
To create a file in the host, navigate to the "/app-data" folder and create a file there.

Next, let's access the container's shell to check if the file has been copied into the container. Run the following commands:

```
docker exec -it <container_id> sh
cd /container/path
ls
```
You will see that the file has been successfully created in the container.

## Creating a File in the Container
Now, let's create a file within the container by accessing its shell.

```
docker exec -it <container_id> sh
echo "Some content" > /container/path/newfile.txt
```
After running the above commands, you will notice that a new file has been created in your host machine's specified path.

By using volumes, we can persist data between the host and the container, ensuring that important files or data remain accessible even if the container is removed.
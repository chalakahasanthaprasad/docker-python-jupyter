### Pull the Python Docker Image

To get started, pull the official Python Docker image from Docker Hub. This example uses the `python:3.8-slim` image, which is a smaller, optimized version of Python 3.8.

```bash
docker pull python:3.8-slim
```

This command downloads the Python 3.8-slim image to your local machine.

### List All Local Docker Images

Once the image is pulled, you can list all Docker images available on your local system using the following command:

```bash
docker image ls
```

This command displays a list of all Docker images you have downloaded, including the `python:3.8-slim` image.

### Run the Python Docker Image

To run the Python image locally, use the following command:

```bash
docker run -it python:3.8-slim
```

This command starts a container from the `python:3.8-slim` image and opens an interactive Python shell. You can now execute Python commands directly within the container.

## 🚀 Docker Commands for Python and JupyterLab

### Pull the Python Image
![Pushing Docker Image](images/Screenshot_1-Install%20Python%20Image.png)

To get the Python 3.8 slim image from Docker Hub:
```bash
docker pull python:3.8-slim
```

### List All Local Docker Images
![Pushing Docker Image](images/Screenshot_2-Type%20Linux%20cmd%20Inside%20Python%20Container.png)

To see all the Docker images that are available locally:
```bash
docker image ls
```

### Run the Python Image Locally
To run the Python image interactively:
```bash
docker run -it python:3.8-slim
```

### Run the Python Image in Detached Mode
To run the Python image in the background:
```bash
docker run -t -d python:3.8-slim
```

### Assign a Specific Name to the Container
If you want to give your container a specific name:
```bash
docker run -t -d --name=<your_container_name> python:3.8-slim
```

**Example:**
![Pushing Docker Image](images/Screenshot%20_3-Create%20new%20Container%20base%20on%20python3.8%20and%20install%20Jupyter%20Lab.png)

```bash
docker run -t -d --name=pyjupyter python:3.8-slim
```

### Create a Copy of the Container
To create a new container with the same base image but without copying modifications like installed packages (e.g., JupyterLab installed inside the container):
1. **Original Container**: Python base image (with JupyterLab installed).
2. **New Container**: A fresh Python image, without the JupyterLab installation.

Now, we have two containers:
- `python:3.8-slim`
- `pyjupyter` (if JupyterLab was installed in it)

### Access the Bash Shell of a Running Container
To open the terminal (bash) inside a running container, use either the container ID or name:
```bash
docker exec -it <container_id> bash
docker exec -it <container_name> bash
```

**Examples:**
```bash
docker exec -it d7605a2704ae bash
docker exec -it pyjupyter bash
```

### Check Installed Python Packages
Inside the container, to list all installed Python packages:
```bash
pip list
```

### Install JupyterLab Inside the Container
To install JupyterLab inside the running Python container:
```bash
pip install jupyterlab
```

### Exit the Container Console
To exit the container's bash shell:
```bash
Ctrl + D
```

### Save the Container State as a New Image
![Pushing Docker Image](images/Screenshot_5-Save%20the%20current%20state%20of%20a%20container%20as%20a%20new%20image.png)

To save the current state of a container as a new image:
```bash
docker commit pyjupyter dsimage
```

### List Docker Images
To list all Docker images on your local machine:
```bash
docker image ls
```

### List Running Containers
To list all running Docker containers:
```bash
docker ps
```

### Stop and Remove a Container
To stop a running container:
```bash
docker stop pyjupyter
```

To remove a stopped container:
```bash
docker rm pyjupyter
```

### Run a Container with a Deleted Name
To run a new container with the same name as a previously deleted container:
```bash
docker run --rm -t -d --name=<deleted_container_name> <image_name>
```

**Example:**
```bash
docker run --rm -t -d --name=pyjupyter dsimage
```

### Available Ports to Map: Local Machine
![Pushing Docker Image](images/Screenshot_6-Find%20Available%20Ports.png)

To run a cmd or install this CurrPorts [Download](https://www.nirsoft.net/utils/cports.html/) :
```bash
netstat -aon
```

### Port Mapping: Local Machine to Container
![Pushing Docker Image](images/Screenshot_7-Port%20Mapping.png)

To run a container and map a port on your local machine to a port in the container (Local Machine port=8585: Container Port=8484):
```bash
docker run --rm -t -d --name=pyjupyter -p 8585:8484 dsimage
```

### Accessing the Container
![Pushing Docker Image](images/Screenshot_8-Jupyter%20Map%20to%20Local%20Machin.png)

To access the bash shell inside the `pyjupyter` container:
```bash
docker exec -it pyjupyter bash
```

### Start JupyterLab Inside the Container
To start JupyterLab inside the container:
```bash
jupyter lab --ip='0.0.0.0' --port=8484 --no-browser --allow-root
```

### Access JupyterLab from Your Browser
![Pushing Docker Image](images/Screenshot_9-Go%20to%20the%20Browser.png)

Open your browser and go to:
```
http://localhost:8585
```

Token:
![Pushing Docker Image](images/Screenshot_10-Where%20my%20token.png)
<br>
Jupyter:
![Pushing Docker Image](images/Screenshot_11-enter%20any%20password%20and%20enter%20To%20Jupyter.png)
<br>
Docker Desktop:
![Pushing Docker Image](images/Screenshot_12-Our%20base%20has%20been%20changed%20to%20our%20custome%20image.png)
<br>
### Enjoy the code! 😎
---

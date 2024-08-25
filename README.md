# Docker Python Jupyter

This repository provides a Dockerized setup for Python and JupyterLab, making it easier to manage Python environments and dependencies for machine learning projects.

## Why Docker?

Installing Python and its dependencies locally on a machine can often lead to various problems, especially when working with multiple projects requiring different Python versions. Here are some common issues faced when managing Python environments without Docker:

- **Version Conflicts**: When a new Python version (e.g., 3.9) is installed along with its specific packages, older versions (e.g., 3.8) may not function properly due to incompatible dependencies.
- **Dependency Management**: Virtual environments (`venv`) are a standard solution, but they can still lead to issues such as:
  - **Environment Activation**: Forgetting to activate the correct virtual environment can result in using the wrong Python interpreter or package versions.
  - **Environment Corruption**: Over time, environments can become bloated with unnecessary packages or suffer from version conflicts that are hard to debug.
  - **Reproducibility**: Sharing environments with others can be challenging, as different machines might have different setups or system-specific dependencies.

## Benefits of Using Docker

Docker containers solve these problems by providing a consistent environment across all machines:

- **Isolated Environment**: Each Docker container runs independently of the host system, ensuring that the installed Python version and packages are isolated and won't interfere with other projects or system Python installations.
- **Portability**: Docker containers can run on any machine that has Docker installed, providing a consistent environment regardless of the underlying operating system.
- **Simplicity**: Once a Docker image is created, it can be reused multiple times without reinstalling Python or JupyterLab.

## Project Setup

To get started with this project, follow the steps below:

### Prerequisites

- Install Docker on your machine. Follow the [official Docker installation guide](https://docs.docker.com/get-docker/) for instructions specific to your operating system.

### Building the Docker Image

1. Clone this repository:

   ```bash
   git clone https://github.com/chalakahasanthaprasad/docker-python-jupyter.git
   cd docker-python-jupyter
   ```

2. Build the Docker image:

   ```bash
   docker build -t python-jupyter .
   ```

### Running JupyterLab

After building the image, you can run JupyterLab inside a Docker container:

```bash
docker run -p 8888:8888 python-jupyter
```

This command will start a JupyterLab server accessible at `http://localhost:8888` on your local machine.

### Using the Container

The Docker container is configured to run JupyterLab with the specified Python version and all necessary packages. This setup ensures that your development environment is consistent and portable across different systems.

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## Conclusion

Using Docker for your Python and JupyterLab setup is a great way to avoid the common pitfalls of managing Python environments locally. With Docker, you can easily switch between different Python versions and dependencies, maintain a clean and isolated environment, and ensure that your machine learning projects are reproducible and portable.

Feel free to contribute to this repository by submitting issues or pull requests!

---

This README now includes the license information, clearly outlining that the project is under the MIT License.

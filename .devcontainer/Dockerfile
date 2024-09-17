# Use the official Python 3.10 image as the base
FROM mcr.microsoft.com/devcontainers/python:3.10

# Set environment variables to avoid interactive prompts during package installation
ENV DEBIAN_FRONTEND=noninteractive

# Install necessary system dependencies for ML and scientific computing
RUN apt-get update && apt-get install -y \
    git \
    wget \
    build-essential \
    libgl1-mesa-glx \
    libhdf5-dev \
    && apt-get clean

# Set up working directory
WORKDIR /workspace

# Install JupyterLab and configure it to run properly in Codespaces
RUN pip install jupyterlab

# Expose port 8888 for JupyterLab
EXPOSE 8888

# Set the default command to launch JupyterLab on Codespace start
CMD ["jupyter", "lab", "--ip=0.0.0.0", "--no-browser", "--allow-root"]

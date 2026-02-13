# Use official Python 3.11 image with development tools
FROM mcr.microsoft.com/devcontainers/python:3.11-bookworm

# Set environment variables
ENV DEBIAN_FRONTEND=noninteractive
ENV PYTHONUNBUFFERED=1

# Install system dependencies for Python packages and Azure services
RUN apt-get update && apt-get install -y \
    build-essential \
    git \
    curl \
    wget \
    ca-certificates \
    libssl-dev \
    libffi-dev \
    python3-dev \
    libpq-dev \
    # Image processing libraries
    libjpeg-dev \
    libpng-dev \
    libtiff-dev \
    libfreetype6-dev \
    liblcms2-dev \
    libwebp-dev \
    libopenjp2-7-dev \
    zlib1g-dev \
    # Additional utilities
    vim \
    nano \
    && rm -rf /var/lib/apt/lists/*

# Install Jupyter and common Python tools
RUN pip install --no-cache-dir \
    jupyter \
    jupyterlab \
    ipykernel \
    ipywidgets \
    notebook

# Create a non-root user (vscode) - already created in base image
# Set up Jupyter configuration
USER vscode
RUN mkdir -p /home/vscode/.jupyter && \
    echo "c.ServerApp.ip = '0.0.0.0'" >> /home/vscode/.jupyter/jupyter_notebook_config.py && \
    echo "c.ServerApp.allow_root = False" >> /home/vscode/.jupyter/jupyter_notebook_config.py && \
    echo "c.ServerApp.open_browser = False" >> /home/vscode/.jupyter/jupyter_notebook_config.py

# Switch back to root for any final setup
USER root

# Set the default shell to bash
ENV SHELL=/bin/bash

# Set working directory
WORKDIR /workspaces/mslearn-ai-vision

# Default command
CMD ["/bin/bash"]

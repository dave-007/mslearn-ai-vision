# Devcontainer Setup for Azure AI Vision Labs

This repository includes a preconfigured development container (devcontainer) that provides a complete Python environment for working with Azure AI Vision services and Jupyter notebooks.

## 🎯 What's Included

The devcontainer provides:
- **Python 3.11** with all necessary packages pre-installed
- **Jupyter Notebook & JupyterLab** for interactive development
- **Azure AI SDKs**: Vision, Custom Vision, Face API, OpenAI
- **VS Code Extensions**: Python, Jupyter, Azure Tools
- **Azure CLI** for resource management
- **Image processing libraries**: PIL, OpenCV, matplotlib
- All dependencies from the lab exercises

## 🚀 Getting Started with GitHub Codespaces

GitHub Codespaces provides a cloud-based development environment that works directly in your browser.

### Steps:

1. **Open in Codespaces**
   - Navigate to the repository on GitHub
   - Click the green **"Code"** button
   - Select the **"Codespaces"** tab
   - Click **"Create codespace on main"** (or your branch)

2. **Wait for Setup**
   - The container will automatically build (first time takes 2-5 minutes)
   - Dependencies are automatically installed via `postCreateCommand`
   - You'll see a VS Code interface in your browser

3. **Start Working**
   - Navigate to `Labfiles/` directory
   - Open any `.ipynb` notebook file
   - Configure your Azure credentials in `.env` files
   - Run the notebook cells

4. **Using Jupyter**
   ```bash
   # Start Jupyter Lab (if needed)
   jupyter lab --ip=0.0.0.0 --port=8888 --no-browser
   ```
   - VS Code will prompt you to open the forwarded port
   - Or use the Jupyter extension built into VS Code

### Codespaces Tips:

- **Port Forwarding**: Port 8888 is automatically forwarded for Jupyter
- **Secrets**: Add Azure credentials as Codespaces secrets for automatic loading
- **Cost**: Free tier includes 60 hours/month; stop codespaces when not in use
- **Persistence**: Files are saved automatically; containers persist between sessions

## 🐳 Getting Started with Local Docker Containers

For local development using VS Code and Docker Desktop.

### Prerequisites:

1. **Install Docker Desktop**
   - Windows: [Docker Desktop for Windows](https://docs.docker.com/desktop/install/windows-install/)
   - Mac: [Docker Desktop for Mac](https://docs.docker.com/desktop/install/mac-install/)
   - Linux: [Docker Engine](https://docs.docker.com/engine/install/)

2. **Install Visual Studio Code**
   - Download from [code.visualstudio.com](https://code.visualstudio.com/)

3. **Install Dev Containers Extension**
   - Open VS Code
   - Go to Extensions (Ctrl+Shift+X / Cmd+Shift+X)
   - Search for "Dev Containers" (ms-vscode-remote.remote-containers)
   - Click Install

### Steps:

1. **Clone the Repository**
   ```bash
   git clone https://github.com/MicrosoftLearning/mslearn-ai-vision.git
   cd mslearn-ai-vision
   ```

2. **Open in Container**
   - Open the folder in VS Code: `code .`
   - VS Code will detect the `.devcontainer` folder
   - Click **"Reopen in Container"** in the notification
   - Or press `F1`, type "Dev Containers: Reopen in Container"

3. **Wait for Build**
   - First build takes 3-7 minutes (downloads base image and installs packages)
   - Subsequent starts are much faster (under 30 seconds)
   - Watch the build progress in the terminal

4. **Start Working**
   - All files are mounted from your local filesystem
   - Open notebooks in `Labfiles/` directories
   - Edit code with full IntelliSense and debugging
   - Run Jupyter directly in VS Code or via terminal

5. **Using Jupyter**
   ```bash
   # Start Jupyter Lab
   jupyter lab --ip=0.0.0.0 --port=8888 --no-browser
   ```
   - Access at http://localhost:8888
   - Or use VS Code's built-in Jupyter support (recommended)

### Local Development Tips:

- **Performance**: Docker Desktop works best with allocated resources (Settings → Resources)
  - Recommended: 4+ GB RAM, 2+ CPU cores
- **File Changes**: Files are synced in real-time between host and container
- **Persistence**: Installed packages persist in the Docker volume
- **Rebuilding**: If you modify `.devcontainer` files:
  - Press `F1` → "Dev Containers: Rebuild Container"

## ⚙️ Configuration

### Azure Credentials

Each lab directory contains a `.env` file template. Configure your credentials:

```bash
# Example: Labfiles/analyze-images/python/image-analysis/.env
AI_SERVICE_ENDPOINT=https://your-resource.cognitiveservices.azure.com/
AI_SERVICE_KEY=your-key-here
```

### Environment Variables in Codespaces

For GitHub Codespaces, you can set secrets at the repository or organization level:
1. Go to Settings → Secrets and variables → Codespaces
2. Add secrets like `AI_SERVICE_ENDPOINT`, `AI_SERVICE_KEY`
3. They'll be automatically available in your codespace

## 🔧 Customization

### Adding Python Packages

Edit `.devcontainer/requirements.txt` and rebuild:
```bash
# Add your package
echo "your-package==1.0.0" >> .devcontainer/requirements.txt

# Rebuild container (VS Code)
# F1 → "Dev Containers: Rebuild Container"
```

### Modifying the Container

Edit `.devcontainer/Dockerfile` to install system packages:
```dockerfile
RUN apt-get update && apt-get install -y \
    your-system-package \
    && rm -rf /var/lib/apt/lists/*
```

### VS Code Extensions

Add extensions to `.devcontainer/devcontainer.json`:
```json
"extensions": [
    "ms-python.python",
    "your-extension-id"
]
```

## 📝 Common Commands

```bash
# Verify Python version
python --version

# Check installed packages
pip list

# Update a package
pip install --upgrade package-name

# Start Jupyter Notebook
jupyter notebook

# Start JupyterLab
jupyter lab

# Run a Python script
python script.py

# Azure CLI commands
az --version
az login
```

## 🐛 Troubleshooting

### Issue: Container won't build
**Solution**: 
- Check Docker Desktop is running
- Ensure you have internet connectivity
- Try: "Dev Containers: Rebuild Container Without Cache"

### Issue: Port 8888 already in use
**Solution**:
```bash
# Kill existing Jupyter processes
pkill -f jupyter

# Or use a different port
jupyter lab --port=8889
```

### Issue: Import errors in notebooks
**Solution**:
```bash
# Reinstall requirements
pip install --force-reinstall -r .devcontainer/requirements.txt

# Or install specific package
pip install azure-ai-vision-imageanalysis==1.0.0
```

### Issue: Azure authentication fails
**Solution**:
- Verify `.env` file exists and has correct values
- Check your Azure subscription is active
- Ensure the Azure resource is in the same region
- Try using Azure CLI: `az login`

### Issue: Jupyter kernel dies
**Solution**:
- Increase Docker Desktop memory allocation (Settings → Resources)
- Restart the kernel: Kernel → Restart
- Check for infinite loops or memory leaks in code

## 📚 Additional Resources

- [VS Code Dev Containers Documentation](https://code.visualstudio.com/docs/devcontainers/containers)
- [GitHub Codespaces Documentation](https://docs.github.com/en/codespaces)
- [Azure AI Vision Documentation](https://learn.microsoft.com/azure/ai-services/computer-vision/)
- [Jupyter Documentation](https://jupyter.org/documentation)

## 🤝 Contributing

If you find issues with the devcontainer configuration or have suggestions:
1. Open an issue on GitHub
2. Submit a pull request with improvements
3. Share your configuration tweaks with the community

## 📜 License

This devcontainer configuration is part of the mslearn-ai-vision repository and follows the same MIT License.

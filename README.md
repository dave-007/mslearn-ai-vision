# Develop Computer Vision Solutions in Azure

The exercises in this repo are designed to provide you with a hands-on learning experience in which you'll explore common tasks that developers perform when creating computer vision solutions on Microsoft Azure.

> **Note**: To complete the exercises, you'll need an Azure subscription in which you have sufficient permissions and quota to provision the necessary Azure resources and generative AI models. If you don't already have one, you can sign up for an [Azure account](https://azure.microsoft.com/free). There's a free trial option for new users that includes credits for the first 30 days.

[View the exercises in the GitHub Pages site for this repo](https://go.microsoft.com/fwlink/?linkid=2318640)

> **Note**: While you can complete these exercises on their own, they're designed to complement modules on [Microsoft Learn](https://learn.microsoft.com/training/paths/create-computer-vision-solutions-azure-ai/); in which you'll find a deeper dive into some of the underlying concepts on which these exercises are based.

## 📓 Jupyter Notebook Labs

All labs are now available as **interactive Jupyter notebooks** with comprehensive explanations, code examples, and visualizations. Each lab includes both a **basic** and an **advanced** notebook for progressive learning.

### Getting Started with Notebooks

#### 🐳 Quick Start with Devcontainer (Recommended)

The easiest way to get started is using our pre-configured development container that includes all dependencies:

**Option 1: GitHub Codespaces** (Cloud-based, no local setup required)
1. Click the **Code** button → **Codespaces** tab → **Create codespace**
2. Wait for the container to build (2-5 minutes first time)
3. Start working with notebooks immediately!

**Option 2: Local Docker Container** (Local development with VS Code)
1. Install [Docker Desktop](https://www.docker.com/products/docker-desktop) and [VS Code](https://code.visualstudio.com/)
2. Install the [Dev Containers extension](https://marketplace.visualstudio.com/items?itemName=ms-vscode-remote.remote-containers)
3. Clone this repository and open in VS Code
4. Click "Reopen in Container" when prompted

📖 **[Full Devcontainer Documentation](.devcontainer/README.md)** - Detailed setup instructions and troubleshooting

#### 💻 Manual Setup (Alternative)

If you prefer to set up your environment manually:

#### Prerequisites
- Python 3.8 or later
- Jupyter Notebook or JupyterLab
- Azure subscription with appropriate AI services

#### Quick Setup

1. **Clone the repository**
   ```bash
   git clone https://github.com/MicrosoftLearning/mslearn-ai-vision
   cd mslearn-ai-vision
   ```

2. **Install dependencies**
   ```bash
   pip install jupyter python-dotenv azure-ai-vision-imageanalysis matplotlib pillow azure-cognitiveservices-vision-customvision azure-cognitiveservices-vision-face openai requests
   ```

3. **Configure credentials**
   - Navigate to the lab directory (e.g., `Labfiles/analyze-images/python/image-analysis/`)
   - Edit the `.env` file with your Azure credentials
   - Or set credentials directly in the notebook cells

4. **Launch Jupyter**
   ```bash
   jupyter notebook
   ```

5. **Open a notebook** and start learning!

### 📚 Available Labs

#### Lab 01: Image Analysis with Azure AI Vision
- **Basic**: `Labfiles/analyze-images/01-analyze-images.ipynb`
  - Image captions and tags
  - Object detection
  - People detection
  - Visualizations with bounding boxes
- **Advanced**: `Labfiles/analyze-images/01-analyze-images-advanced.ipynb`
  - Smart cropping for thumbnails
  - Dense captioning
  - Background removal
  - Content moderation
  - Batch processing

#### Lab 02: Optical Character Recognition (OCR)
- **Basic**: `Labfiles/ocr/02-ocr.ipynb`
  - Text extraction from images
  - Line and word detection
  - Bounding polygon visualization
- **Advanced**: `Labfiles/ocr/02-ocr-advanced.ipynb`
  - Handwritten text recognition
  - Multi-language support
  - Document layout analysis
  - Table extraction
  - Form processing

#### Lab 03: Face Service
- **Basic**: `Labfiles/face/03-face-service.ipynb`
  - Face detection
  - Facial attributes (age, emotion, accessories)
  - Emotion analysis
- **Advanced**: `Labfiles/face/03-face-service-advanced.ipynb`
  - Face verification
  - Similar face finding
  - Face grouping
  - Facial landmarks
  - Best practices and ethics

#### Lab 04: Custom Vision - Image Classification
- **Basic**: `Labfiles/image-classification/04-image-classification.ipynb`
  - Training custom classifiers
  - Uploading and tagging images
  - Model evaluation
- **Advanced**: `Labfiles/image-classification/04-image-classification-advanced.ipynb`
  - Transfer learning
  - Data augmentation
  - Multi-label classification
  - Model export for edge deployment

#### Lab 05: Custom Vision - Object Detection
- **Basic**: `Labfiles/object-detection/05-object-detection.ipynb`
  - Training object detectors
  - Bounding box annotations
  - Confidence thresholds
- **Advanced**: `Labfiles/object-detection/05-object-detection-advanced.ipynb`
  - IoU metrics
  - Non-maximum suppression
  - Real-time detection
  - Performance optimization

#### Lab 06: Video Indexer
- **Basic**: `Labfiles/video-indexer/06-video-indexer.ipynb`
  - Video upload and indexing
  - Insight extraction
  - Transcript processing
  - Timeline analysis
- **Advanced**: `Labfiles/video-indexer/06-video-indexer-advanced.ipynb`
  - Custom models
  - Content moderation
  - Speaker identification
  - Batch processing

#### Lab 08: Generative AI with Vision (GPT-4 Vision)
- **Basic**: `Labfiles/gen-ai-vision/08-gen-ai-vision.ipynb`
  - Image understanding with GPT-4
  - Visual question answering
  - Multi-turn conversations
- **Advanced**: `Labfiles/gen-ai-vision/08-gen-ai-vision-advanced.ipynb`
  - Complex image reasoning
  - Image comparison
  - Few-shot learning
  - Batch analysis

#### Lab 09: DALL-E Image Generation
- **Basic**: `Labfiles/dalle-client/09-dalle.ipynb`
  - Text-to-image generation
  - Prompt engineering basics
  - Interactive image creation
- **Advanced**: `Labfiles/dalle-client/09-dalle-advanced.ipynb`
  - Advanced prompt patterns
  - Style transfer
  - A/B testing
  - Creative workflows

### 💡 Tips for Learning

- **Start with basic notebooks** to understand core concepts
- **Progress to advanced notebooks** to explore sophisticated features
- **Experiment with your own images** and prompts
- **Read the markdown cells carefully** for context and explanations
- **Run cells sequentially** to avoid dependency issues
- **Check the Azure documentation** links provided in notebooks

### 🔧 Troubleshooting

**Issue**: Module not found errors
- **Solution**: Install required packages using pip install

**Issue**: Authentication errors
- **Solution**: Verify your Azure credentials in `.env` files

**Issue**: Jupyter kernel crashes
- **Solution**: Restart the kernel and ensure sufficient system memory

**Issue**: Rate limiting errors
- **Solution**: Add delays between API calls or use batch processing

### 📖 Additional Resources

- [Azure AI Vision Documentation](https://learn.microsoft.com/azure/ai-services/computer-vision/)
- [Azure Custom Vision Documentation](https://learn.microsoft.com/azure/ai-services/custom-vision-service/)
- [Azure Face API Documentation](https://learn.microsoft.com/azure/ai-services/computer-vision/overview-identity)
- [Azure Video Indexer Documentation](https://learn.microsoft.com/azure/azure-video-indexer/)
- [Azure OpenAI Service Documentation](https://learn.microsoft.com/azure/ai-services/openai/)

### 🤝 Contributing

We welcome contributions! If you find issues or have suggestions for improvements, please open an issue or submit a pull request.

### 📜 License

This project is licensed under the MIT License - see the LICENSE file for details.


# Azure AI Vision - Jupyter Notebook Lab Guide

## 🎯 Overview

This repository contains comprehensive Jupyter notebook labs for learning Azure AI Vision services. Each lab is designed to be interactive, educational, and practical, with clear explanations and runnable code examples.

## 📋 Table of Contents

- [Getting Started](#getting-started)
- [Lab Structure](#lab-structure)
- [Detailed Lab Descriptions](#detailed-lab-descriptions)
- [Best Practices](#best-practices)
- [Troubleshooting](#troubleshooting)

## 🚀 Getting Started

### Prerequisites

Before starting, ensure you have:

1. **Python 3.8+** installed
2. **Jupyter Notebook or JupyterLab**
3. **Azure Subscription** with:
   - Azure AI Vision resource (Labs 01-03)
   - Azure Custom Vision resource (Labs 04-05)
   - Azure Video Indexer account (Lab 06)
   - Azure OpenAI resource (Labs 08-09)

### Installation

```bash
# 1. Clone the repository
git clone https://github.com/MicrosoftLearning/mslearn-ai-vision
cd mslearn-ai-vision

# 2. Create a virtual environment (recommended)
python -m venv labenv
source labenv/bin/activate  # On Windows: labenv\Scripts\activate

# 3. Install required packages
pip install jupyter python-dotenv
pip install azure-ai-vision-imageanalysis==1.0.0
pip install azure-cognitiveservices-vision-customvision
pip install azure-cognitiveservices-vision-face
pip install openai matplotlib pillow requests

# 4. Launch Jupyter
jupyter notebook
```

### Azure Resource Setup

#### For Labs 01-03 (Azure AI Vision)
1. Go to [Azure Portal](https://portal.azure.com)
2. Create a **Computer Vision** resource
3. Note the **Endpoint** and **Key** from the resource

#### For Labs 04-05 (Custom Vision)
1. Go to [Custom Vision Portal](https://customvision.ai)
2. Create a project
3. Note the **Training Key**, **Prediction Key**, and **Endpoint**

#### For Lab 06 (Video Indexer)
1. Go to [Video Indexer Portal](https://videoindexer.ai)
2. Sign in with your Azure account
3. Get your **Account ID** and **API Key**

#### For Labs 08-09 (Azure OpenAI)
1. Create an **Azure OpenAI** resource
2. Deploy GPT-4 Vision (Lab 08) and DALL-E (Lab 09) models
3. Note the **Endpoint**, **API Key**, and **Deployment Names**

## 📚 Lab Structure

Each lab follows a consistent structure:

```
Labfiles/
├── lab-name/
│   ├── XX-lab-name.ipynb                    # Basic lab notebook
│   ├── XX-lab-name-advanced.ipynb           # Advanced topics
│   └── python/
│       └── script-name/
│           ├── .env                         # Configuration file
│           ├── requirements.txt             # Dependencies
│           ├── images/                      # Sample images
│           └── script-name.py              # Original Python script (reference)
```

### Notebook Components

Each notebook includes:

1. **Overview Section**: Learning objectives and prerequisites
2. **Setup Cells**: Package installation and imports
3. **Configuration**: Azure credential setup
4. **Core Exercises**: Step-by-step guided activities
5. **Visualizations**: Charts and annotated images
6. **Practice Exercises**: Hands-on challenges
7. **Summary**: Key takeaways and next steps
8. **Resources**: Links to documentation and guides

## 📖 Detailed Lab Descriptions

### Lab 01: Image Analysis with Azure AI Vision

#### Basic Notebook (`01-analyze-images.ipynb`)
**Time**: ~30 minutes | **Difficulty**: Beginner

**What You'll Learn:**
- Authenticate with Azure AI Vision service
- Generate AI-powered image captions
- Extract descriptive tags from images
- Detect objects with bounding boxes
- Identify people in images
- Visualize detection results

**Key APIs:**
- `ImageAnalysisClient.analyze()`
- `VisualFeatures.CAPTION`
- `VisualFeatures.TAGS`
- `VisualFeatures.OBJECTS`
- `VisualFeatures.PEOPLE`

**Sample Images Included:**
- `street.jpg` - Urban scene with people and objects
- `person.jpg` - Portrait photo
- `building.jpg` - Architecture image

#### Advanced Notebook (`01-analyze-images-advanced.ipynb`)
**Time**: ~45 minutes | **Difficulty**: Intermediate

**Advanced Topics:**
- Smart cropping for thumbnail generation
- Dense captioning (region-specific descriptions)
- Background removal and foreground matting
- Content moderation (adult/racy/gory detection)
- Multi-feature comprehensive analysis
- Batch processing multiple images

**Use Cases:**
- E-commerce product thumbnails
- Content moderation pipelines
- Accessibility features with detailed descriptions
- Automated image cataloging

---

### Lab 02: Optical Character Recognition (OCR)

#### Basic Notebook (`02-ocr.ipynb`)
**Time**: ~25 minutes | **Difficulty**: Beginner

**What You'll Learn:**
- Extract text from images using Read API
- Process text blocks, lines, and words
- Visualize text detection with bounding polygons
- Handle confidence scores
- Extract structured text data

**Key Concepts:**
- **Blocks**: Logical groupings of text
- **Lines**: Horizontal text sequences
- **Words**: Individual text elements
- **Bounding Polygons**: 4-point coordinates defining text location

**Sample Images:**
- `Lincoln.jpg` - Gettysburg Address document

#### Advanced Notebook (`02-ocr-advanced.ipynb`)
**Time**: ~60 minutes | **Difficulty**: Advanced

**Advanced Topics:**
- Handwritten text recognition
- Multi-language text detection (100+ languages)
- Document layout analysis
- Table extraction with structure preservation
- Invoice and receipt processing
- Batch document processing with parallel execution
- Text post-processing and error correction
- Integration with Azure Form Recognizer

**Use Cases:**
- Document digitization
- Invoice processing automation
- Handwritten form extraction
- Multi-language document translation

---

### Lab 03: Face Service

#### Basic Notebook (`03-face-service.ipynb`)
**Time**: ~35 minutes | **Difficulty**: Beginner

**What You'll Learn:**
- Detect faces in images
- Analyze facial attributes:
  - Demographics (age, gender)
  - Emotions (8 types with confidence)
  - Physical features (hair, glasses, facial hair)
  - Accessories and head pose
- Visualize face detection results
- Create emotion analysis charts

**Sample Images:**
- `face1.jpg`, `face2.jpg` - Individual portraits
- `faces.jpg` - Multiple faces

**Important Note**: 
Face recognition for specific individuals requires [Limited Access approval](https://aka.ms/cog-services-limited-access) from Microsoft.

#### Advanced Notebook (`03-face-service-advanced.ipynb`)
**Time**: ~50 minutes | **Difficulty**: Intermediate

**Advanced Topics:**
- Face verification (1:1 matching)
- Similar face finding (1:N matching)
- Face grouping and clustering
- 27-point facial landmarks
- Recognition quality assessment
- Detection model comparison
- Privacy and ethical considerations

**Use Cases:**
- Identity verification
- Photo organization
- Emotion analytics for UX research
- Accessibility features

---

### Lab 04: Custom Vision - Image Classification

#### Basic Notebook (`04-image-classification.ipynb`)
**Time**: ~45 minutes | **Difficulty**: Intermediate

**What You'll Learn:**
- Create Custom Vision classification projects
- Upload and tag training images
- Train custom image classifiers
- Make predictions with confidence scores
- Evaluate model performance
- Improve models with additional data

**Dataset:**
- 45 training images across 3 classes:
  - Apples (15 images)
  - Bananas (15 images)
  - Oranges (15 images)

**Training Process:**
1. Create project
2. Upload tagged images
3. Train model
4. Evaluate performance
5. Test predictions
6. Iterate and improve

#### Advanced Notebook (`04-image-classification-advanced.ipynb`)
**Time**: ~75 minutes | **Difficulty**: Advanced

**Advanced Topics:**
- Transfer learning and domain selection
- Data augmentation techniques:
  - Rotation, flipping, brightness, contrast
- Advanced evaluation metrics:
  - F1 scores, confusion matrices, ROC curves
- Multi-label vs multi-class classification
- Batch prediction for efficiency
- Model export for edge deployment (ONNX, TensorFlow)
- Production deployment patterns

**Use Cases:**
- Product categorization
- Quality control inspection
- Wildlife species identification
- Medical image classification

---

### Lab 05: Custom Vision - Object Detection

#### Basic Notebook (`05-object-detection.ipynb`)
**Time**: ~50 minutes | **Difficulty**: Intermediate

**What You'll Learn:**
- Create object detection projects
- Annotate images with bounding boxes
- Train custom object detectors
- Detect objects with confidence thresholds
- Visualize detections with annotations
- Evaluate detection performance

**Key Concepts:**
- **Bounding Boxes**: Rectangular regions around objects
- **Normalized Coordinates**: 0-1 coordinate system
- **Confidence Threshold**: Minimum confidence for detections
- **Tags**: Object class labels

#### Advanced Notebook (`05-object-detection-advanced.ipynb`)
**Time**: ~90 minutes | **Difficulty**: Advanced

**Advanced Topics:**
- IoU (Intersection over Union) calculations
- Non-Maximum Suppression (NMS)
- Performance benchmarking
- Multi-object scene analysis
- Real-time detection considerations
- Production-ready detector implementation
- Memory and latency optimization

**Use Cases:**
- Retail shelf monitoring
- Manufacturing defect detection
- Traffic monitoring
- Sports analytics

---

### Lab 06: Video Indexer

#### Basic Notebook (`06-video-indexer.ipynb`)
**Time**: ~40 minutes | **Difficulty**: Intermediate

**What You'll Learn:**
- Upload and index videos
- Extract comprehensive insights:
  - Faces, keywords, topics, sentiments
- Process video transcripts
- Analyze timelines
- Detect objects and scenes
- Search within video content
- Generate summaries and highlights

**Sample Video:**
- `responsible_ai.mp4` - Microsoft's Responsible AI video

**Key Features:**
- Automated video indexing
- Timestamped transcripts
- Visual and audio insights
- Content searchability

#### Advanced Notebook (`06-video-indexer-advanced.ipynb`)
**Time**: ~70 minutes | **Difficulty**: Advanced

**Advanced Topics:**
- Custom brand detection models
- Custom people models (requires approval)
- Content moderation and compliance
- Speaker diarization
- Scene and shot detection
- Keyframe extraction
- Batch video processing
- Azure service integration (Storage, Logic Apps, Functions)

**Use Cases:**
- Media content management
- Educational video analysis
- Compliance monitoring
- Video accessibility (automatic captions)

---

### Lab 08: Generative AI with Vision (GPT-4 Vision)

#### Basic Notebook (`08-gen-ai-vision.ipynb`)
**Time**: ~35 minutes | **Difficulty**: Intermediate

**What You'll Learn:**
- Authenticate with Azure OpenAI
- Analyze images with GPT-4 Vision
- Ask questions about image content
- Implement multi-turn conversations with image context
- Extract detailed information from visual data
- Use system prompts for specialized tasks

**Example Scenarios:**
- Grocery item identification
- Product description generation
- Image accessibility descriptions
- Visual quality assessment

#### Advanced Notebook (`08-gen-ai-vision-advanced.ipynb`)
**Time**: ~60 minutes | **Difficulty**: Advanced

**Advanced Topics:**
- Complex image reasoning and inference
- Side-by-side image comparison
- Few-shot learning with visual examples
- Chain-of-thought reasoning for vision
- Custom captioning styles
- Content moderation with vision
- Batch image analysis
- Prompt engineering best practices

**Use Cases:**
- Automated product cataloging
- Visual quality control
- Educational content generation
- Medical image interpretation (preliminary)

---

### Lab 09: DALL-E Image Generation

#### Basic Notebook (`09-dalle.ipynb`)
**Time**: ~30 minutes | **Difficulty**: Beginner

**What You'll Learn:**
- Generate images from text descriptions
- Use effective prompts for desired results
- Save and display generated images
- Iterate on prompts for refinement
- Explore artistic styles and techniques
- Control image parameters (size, quality)

**Prompt Categories:**
- Realistic scenes
- Artistic styles (watercolor, oil painting)
- Abstract concepts
- Product mockups
- Character designs

#### Advanced Notebook (`09-dalle-advanced.ipynb`)
**Time**: ~55 minutes | **Difficulty**: Intermediate

**Advanced Topics:**
- Advanced prompt engineering patterns:
  - Style modifiers, lighting, composition
- Image variation generation
- A/B testing different prompts
- Quality optimization techniques
- Prompt templates for consistency
- Content policy and safety filters
- Creative workflows for professionals
- Batch generation strategies

**Use Cases:**
- Marketing material creation
- Concept art generation
- Rapid prototyping
- Social media content
- Educational illustrations

---

## 💡 Best Practices

### Working with Notebooks

1. **Run Cells Sequentially**: Always run cells in order from top to bottom
2. **Read Markdown Cells**: Don't skip the explanatory text
3. **Experiment**: Modify code and try different parameters
4. **Save Regularly**: Use Ctrl+S to save your work
5. **Restart Kernel**: If things seem broken, restart the kernel and run all cells

### Azure Best Practices

1. **Use Free Tiers**: Start with F0 (free) pricing tiers when learning
2. **Monitor Usage**: Check your Azure consumption regularly
3. **Delete Resources**: Remove resources you're not using
4. **Secure Credentials**: Never commit `.env` files with real credentials
5. **Use Resource Groups**: Organize related resources together

### Learning Tips

1. **Start with Basic**: Complete basic notebooks before advanced ones
2. **Take Notes**: Add your own markdown cells with observations
3. **Try Own Data**: Test with your own images and scenarios
4. **Read Documentation**: Follow links to official Azure docs
5. **Join Community**: Engage with Azure AI communities for help

## 🔧 Troubleshooting

### Common Issues and Solutions

#### Issue: "ModuleNotFoundError: No module named 'azure'"
**Solution:**
```bash
pip install azure-ai-vision-imageanalysis azure-cognitiveservices-vision-customvision azure-cognitiveservices-vision-face
```

#### Issue: "Unauthorized" or "InvalidKey" errors
**Solution:**
- Verify your Azure credentials in `.env` files
- Check that your API key hasn't expired
- Ensure you're using the correct endpoint

#### Issue: "Rate limit exceeded"
**Solution:**
- Add delays between API calls: `time.sleep(1)`
- Use batch operations when possible
- Upgrade to a paid tier for higher limits

#### Issue: Jupyter kernel crashes or hangs
**Solution:**
- Restart the kernel: Kernel → Restart
- Check system memory usage
- Close other applications
- Try processing smaller batches of data

#### Issue: Images not displaying
**Solution:**
- Verify image paths are correct (use relative paths)
- Check that `%matplotlib inline` is executed
- Ensure PIL and matplotlib are properly installed

#### Issue: "Model not found" errors (Custom Vision)
**Solution:**
- Verify you've trained the model
- Check the iteration/model ID
- Ensure the model is published

#### Issue: "Quota exceeded" errors
**Solution:**
- Wait for quota to reset (usually hourly/daily)
- Reduce request frequency
- Upgrade to higher service tier

## 📞 Getting Help

### Resources

- **Azure Documentation**: [https://learn.microsoft.com/azure/ai-services/](https://learn.microsoft.com/azure/ai-services/)
- **Microsoft Q&A**: [https://learn.microsoft.com/answers/](https://learn.microsoft.com/answers/)
- **Stack Overflow**: Tag questions with `azure-cognitive-services`
- **GitHub Issues**: Report problems in this repository

### Support Channels

1. **Documentation**: Check official Azure AI Services docs
2. **Community Forums**: Microsoft Q&A and Stack Overflow
3. **GitHub Issues**: For problems with these notebooks
4. **Azure Support**: For account and service issues

## 🎓 Learning Path

### Recommended Order

1. **Beginner Track** (Weeks 1-2):
   - Lab 01 Basic (Image Analysis)
   - Lab 02 Basic (OCR)
   - Lab 09 Basic (DALL-E)

2. **Intermediate Track** (Weeks 3-4):
   - Lab 03 Basic (Face Service)
   - Lab 08 Basic (GPT-4 Vision)
   - Lab 04 Basic (Image Classification)

3. **Advanced Track** (Weeks 5-6):
   - Lab 05 Basic (Object Detection)
   - Lab 06 Basic (Video Indexer)
   - All Advanced notebooks

4. **Expert Track** (Weeks 7-8):
   - Build your own projects
   - Combine multiple services
   - Deploy to production
   - Contribute improvements

## 🏆 Completion Checklist

Track your progress:

- [ ] Lab 01: Image Analysis (Basic)
- [ ] Lab 01: Image Analysis (Advanced)
- [ ] Lab 02: OCR (Basic)
- [ ] Lab 02: OCR (Advanced)
- [ ] Lab 03: Face Service (Basic)
- [ ] Lab 03: Face Service (Advanced)
- [ ] Lab 04: Image Classification (Basic)
- [ ] Lab 04: Image Classification (Advanced)
- [ ] Lab 05: Object Detection (Basic)
- [ ] Lab 05: Object Detection (Advanced)
- [ ] Lab 06: Video Indexer (Basic)
- [ ] Lab 06: Video Indexer (Advanced)
- [ ] Lab 08: GPT-4 Vision (Basic)
- [ ] Lab 08: GPT-4 Vision (Advanced)
- [ ] Lab 09: DALL-E (Basic)
- [ ] Lab 09: DALL-E (Advanced)

## 📜 License

This project is licensed under the MIT License.

## 🤝 Contributing

We welcome contributions! If you find issues or have suggestions:

1. Fork the repository
2. Create a feature branch
3. Make your changes
4. Submit a pull request

---

**Happy Learning!** 🎉

For questions or feedback, please open an issue in this repository.

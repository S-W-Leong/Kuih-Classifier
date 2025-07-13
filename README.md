# 🍰 Kuih Muih Classifier

A Streamlit web application that classifies Traditional Malay kuih muih using an ensemble of MobileNetV3 and Vision Transformer models.

## 🎯 Features

- **🖼️ Image Upload**: Support for JPG, PNG image formats
- **🧠 Ensemble AI**: Combines predictions from MobileNetV3 and Vision Transformer
- **📊 Visualization**: Interactive probability charts using Matplotlib
- **🎨 Beautiful UI**: Modern, responsive design with custom styling
- **⚡ Fast Inference**: Optimized model loading with caching
- **🛡️ Error Handling**: Graceful fallbacks for missing model files

## 📋 Supported Kuih Types

1. **Kek Lapis** - Layered cake
2. **Kuih Kaswi Pandan** - Pandan-flavored rice cake
3. **Kuih Ketayap** - Coconut pancake roll
4. **Kuih Lapis** - Steamed layered cake
5. **Kuih Seri Muka** - Two-layered pandan cake
6. **Kuih Talam** - Steamed coconut cake
7. **Kuih Ubi Kayu** - Cassava cake
8. **Onde-Onde** - Glutinous rice balls

## 🚀 Quick Start

### Prerequisites

- Python 3.8 or higher
- pip package manager

### Installation

1. **Clone or download the project files**

2. **Install dependencies**:
   ```bash
   pip install -r requirements.txt
   ```

3. **Ensure model files are present**:
   - `mobilenetv3.pth` - MobileNetV3 weights
   - `vit.pth` - Vision Transformer weights
   - `labels.txt` - Class labels file

### Running the Application

1. **Start the Streamlit app**:
   ```bash
   streamlit run app.py
   ```

2. **Open your browser** and navigate to the URL shown in the terminal (usually `http://localhost:8501`)

3. **Upload an image** of a Traditional Malay kuih and click "Classify Image"

## 🏗️ Project Structure

```
Kuih_Classifier_App/
├── app.py              # Main Streamlit application
├── model_utils.py      # Model loading and inference utilities
├── mobilenetv3.pth     # MobileNetV3 model weights
├── vit.pth            # Vision Transformer model weights
├── labels.txt         # Class labels
├── requirements.txt   # Python dependencies
└── README.md         # This file
```

## 🔧 Technical Details

### Model Architecture

- **MobileNetV3**: Lightweight CNN optimized for mobile devices
- **Vision Transformer**: Attention-based transformer architecture
- **Ensemble Method**: Average of softmax outputs from both models

### Image Processing

- **Resize**: 224x224 pixels
- **Normalization**: Mean=0.5, Std=0.5
- **Format**: RGB tensor with batch dimension

### Performance Features

- **Model Caching**: Uses `@st.cache_resource` for faster subsequent loads
- **GPU Support**: Automatically detects and uses CUDA if available
- **Error Handling**: Graceful fallbacks for missing model files

## 🎨 UI Features

- **Responsive Design**: Works on desktop and mobile devices
- **Custom Styling**: Beautiful color scheme and typography
- **Interactive Charts**: Matplotlib-based probability visualization
- **Real-time Feedback**: Loading spinners and status indicators
- **Helpful Tips**: User guidance for better classification results

## 🛠️ Customization

### Adding New Models

1. Create a new model class in `model_utils.py`
2. Add the model to the `load_models()` function
3. Update the ensemble prediction logic

### Modifying Class Names

Edit the `labels.txt` file or modify the `load_class_names()` function in `model_utils.py`.

### Changing Image Processing

Modify the `preprocess_image()` function in `model_utils.py` to adjust:
- Image size
- Normalization parameters
- Additional transformations

## 🔍 Troubleshooting

### Common Issues

1. **Model files not found**:
   - Ensure `mobilenetv3.pth` and `vit.pth` are in the project directory
   - The app will use dummy models as fallback

2. **CUDA out of memory**:
   - The app automatically falls back to CPU if GPU memory is insufficient

3. **Import errors**:
   - Make sure all dependencies are installed: `pip install -r requirements.txt`

4. **Image upload issues**:
   - Supported formats: JPG, JPEG, PNG
   - Try resizing large images before uploading

### Performance Tips

- **First run**: Model loading may take 30-60 seconds
- **Subsequent runs**: Models are cached for faster startup
- **GPU usage**: Ensure CUDA is available for faster inference

## 📝 License

This project is for educational and research purposes. Please ensure you have the necessary permissions for any model weights used.

## 🤝 Contributors:

VisionTransformer: Low Ze Xuan, Terrence Chan Jun Seng
MobileNetV3: Francis Tan Jing Xuan

---

**Enjoy classifying Traditional Malay kuih muih! 🍰** 

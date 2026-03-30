# Brain Tumor Detection Project

## Problem
Brain tumors are one of the most critical and life-threatening forms of cancer, requiring timely and accurate detection for effective treatment. This project focuses on the detection of brain tumors using a Convolutional Neural Network (CNN) architecture programmed in Python. The primary objective is to develop a simple yet efficient CNN model capable of classifying brain MRI images into tumor and non-tumor categories.

=> The model leverages the powerful image processing capabilities of CNNs to automatically learn and extract relevant features from the input images, minimizing the need for manual feature extraction. The dataset used for training and validation comprises a diverse set of brain MRI images, pre-processed to enhance image quality and ensure consistency.

=> The CNN architecture is designed with multiple convolutional layers(with 16,32,1 filters respectively ,kernal size=3x3,padding = 1)fully connected layers to achieve high accuracy and robustness.

=> A deep learning-based system for detecting brain tumors in MRI images using Convolutional Neural Networks (CNNs). This project provides multiple implementations of tumor segmentation models and a user-friendly GUI for medical image analysis.

## Features

=> **Brain Tumor Segmentation**: Uses CNN models to identify and segment tumors in MRI scans
=> **X-Ray Abnormality Detection**: Classifies X-ray images as normal or abnormal
=> **Graphical User Interface**: Easy-to-use Tkinter-based interface for image upload and analysis
=> **Visualization**: Displays original images, predicted masks, and segmentation results
=> **Multiple Model Architectures**: Includes different CNN architectures for comparison

## Project Structure

```
Brain-Tumor-Project/
=> 1/                          # MRI images with tumors (training data)
=> 2/                          # MRI images without tumors (training data)
=>src/
│   |=> Mri.py                  # Command-line MRI tumor detection
│   |=>Medical_diagnosis.py    # GUI application with MRI and X-ray analysis
│   |=>Medical_diagnosis1.py   # Alternative GUI with U-Net architecture
│   |=> Medical diagnosis2.py   # Another GUI variant


## Requirements

- Python 3.7+
- PyTorch
- NumPy
- Matplotlib
- Pillow (PIL)
- Tkinter (usually included with Python)
- EasyGUI
- Requests (for loading images from URLs)

## Installation

1. **Clone the repository:**
   ```bash
   git clone https://github.com/ch-ushasree/brain-tumordetection.git
   cd brain-tumorproject
   ```

2. **Install dependencies:**
   ```bash
   pip install torch torchvision numpy matplotlib pillow easygui requests
   ```

## Usage

### Training the Models

=> The current implementation initializes models with random weights. For production use, you would need to train the models on the provided dataset.

=> The models in the current code are not pre-trained. You need to implement training logic or use pre-trained weights.

### Running the Applications

=> GUI Application 
Run the main GUI application for interactive analysis:

```bash
python src/Medical_diagnosis.py
```

This opens a window where you can:
1. Click "Upload Image" to select an MRI or X-ray image
2. Click "Check for Brain Tumor" for MRI analysis
3. Click "Check X-ray for Abnormalities" for X-ray analysis

=> Command-Line MRI Analysis
For direct MRI analysis without GUI:

```bash
python src/Mri.py
```

This will open a file dialog to select an MRI image and display the analysis results.

=> Alternative Versions
- `Medical_diagnosis1.py`: Uses a U-Net-like architecture
- `Medical diagnosis2.py`: Another variant with different features

=> Model Architecture

The project includes several CNN architectures:

### Basic CNN (Mri.py, Medical_diagnosis.py)
- 6 convolutional layers with batch normalization
- ReLU activation functions
- Sigmoid output for binary segmentation

### U-Net Style (Medical_diagnosis1.py)
- Encoder-decoder architecture
- Multiple convolutional blocks
- Suitable for precise segmentation tasks

### Classification CNN (X-Ray Analysis)
- Convolutional layers followed by fully connected layers
- Max pooling for downsampling
- Softmax output for binary classification

## Dataset

The project includes sample MRI datasets:
- **Folder 1**: Images with brain tumors (Y-prefixed files)
- **Folder 2**: Images without brain tumors (no-prefixed files)

Which uncludes a sample dataset. For real medical applications, use properly annotated medical imaging datasets from reliable sources.

## How It Works

1. **Image Preprocessing**: Images are loaded and converted to grayscale numpy arrays
2. **Model Inference**: The CNN processes the image to generate a segmentation mask
3. **Thresholding**: Pixels above 0.5 threshold are considered tumor regions
4. **Visualization**: Results are displayed with original image, mask, and overlay

## Limitations

- Models are not pre-trained and require training on medical datasets
- Current implementation uses random weights
- Performance depends on training data quality and quantity
- Not intended for clinical diagnosis without proper validation

## Contributing

1. Fork the repository
2. Create a feature branch
3. Make your changes
4. Add proper documentation
5. Submit a pull request


## conclusion

This software is for research and educational purposes only. It should not be used for actual medical diagnosis or treatment decisions. Always consult qualified medical professionals for health-related matters.

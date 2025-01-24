# Image Colorization with Transformers and GANs
![image](https://github.com/user-attachments/assets/70165102-f5ea-4091-865f-fa5e321c3525)

## Overview

This project implements a novel image colorization method using Transformer architectures and Generative Adversarial Networks (GANs). The primary objective is to achieve visually appealing and realistic image colorization by addressing challenges like color bleeding, desaturation, and poor detail capture. Key innovations include the integration of a color encoder and a color transformer within the generator architecture. These components enhance the contextual relevance and visual quality of the results.

### Key Features:
- **Transformer-based Architecture**: Captures long-range dependencies and global features.
- **GAN Framework**: Improves visual fidelity of the colorized images.
- **Color Encoder and Transformer**: Enhance the integration of grayscale and color features for better results.

## Architecture
![image](https://github.com/user-attachments/assets/dbf4ffc3-2dd5-4c96-8d0e-5877fc624c32)

The proposed architecture is an encoder-decoder framework with the following components:
1. **Color Encoder**: Generates color features from a random normal distribution.
2. **Color Transformer**: Fuses global and local features for better contextual understanding.
3. **Generator**: Integrates the color encoder and transformer for precise colorization.
4. **Discriminator (Patch-GAN)**: Evaluates the quality of local patches in the colorized images.

The generator operates in the CIELAB color space, where:
- The luminance channel (L) is used as input.
- Chrominance channels (ab) are predicted.

## Getting Started
### 1. Clone the repository:
```bash
git clone https://github.com/elza02/Grey-scale-image-colorization.git
cd Grey-scale-image-colorization
```
### 2. Setting up the Environment:
To replicate the results, a Python virtual environment is recommended.

```bash
# Create a virtual environment
python3 -m venv venv

# Activate the virtual environment
source venv/bin/activate  # For Linux/macOS
# OR
venv\Scripts\activate     # For Windows

# Install dependencies
pip install -r requirements.txt
```
- Open the notebook file in the Jupyter interface, follow the instructions, and execute the cells to process the dataset, train the model, and evaluate results.
## Dataset
The dataset used for training and evaluation is **PASCAL VOC**. It contains over **17,000** images of varying complexity.

Dataset Link: [PASCAL VOC Dataset](http://host.robots.ox.ac.uk/pascal/VOC/)
Images were resized to **256×256** pixels and converted to the **CIELAB color space**.

## Training Pipeline
The training pipeline includes:

1. **Data preprocessing**: Conversion to LAB color space and normalization.
2. **Model training**: Optimization of the generator and discriminator using perceptual, adversarial, and color losses.

## References
This project is based on insights and methodologies from:

- **Hamza Shafiq** and **Bumshik Lee** (2024). "Transforming Color: Novel Image Colorization Method".
DOI: 10.1109/ACCESS.2023.3335225


# Colour-Based Steganography using Chi-Square Analysis

## Overview

This project implements a novel colour-based steganography technique for hiding secret messages within digital images. The method uses a key color and tolerance to select specific pixels for embedding data, ensuring the hidden information is visually indistinguishable. Additionally, it employs Chi-Square analysis to detect the presence of steganographic content in images, providing a statistical measure of detectability.

### Example: Embedding Historical Text

One example demonstrates embedding a detailed biography of J. Robert Oppenheimer into an image using a key color of `(89, 89, 89)` and a tolerance of `1.7320508075688772`. The encoded image appears visually identical to the original, but contains the hidden message.

| Original Image | Visualization of Embedded Data |
|---------------|-------------------------------|
| ![Original](Examples/oppenheimer%20copy.jpg) | ![Visualization](Examples/oppenheimer%20copy_visualization.png) |

## Features

- **Secure Embedding**: Hide text messages in images using color-based pixel selection
- **Chi-Square Detection**: Analyze images for potential hidden data using statistical tests
- **Visualization Tools**: Generate visual representations of embedded data
- **LSB Distribution Analysis**: Examine least significant bit distributions for forensic analysis
- **Jupyter Notebook Implementation**: Interactive Python notebooks for easy experimentation

## Installation

1. Clone the repository:
   ```bash
   git clone https://github.com/yourusername/Colour-Based-Steganography-using-Chi-Square-Analysis.git
   cd Colour-Based-Steganography-using-Chi-Square-Analysis
   ```

2. Install required dependencies:
   ```bash
   pip install -r requirements.txt
   ```

   Or manually install:
   ```bash
   pip install numpy scipy pillow matplotlib jupyter
   ```

## Usage

### Encoding a Message

Run the `chisquare.ipynb` notebook to embed a message:

1. Open `chisquare.ipynb` in Jupyter
2. Provide your secret message, key color, and tolerance
3. Execute the cells to generate the encoded image

### Decoding a Message

Use the decoding functions in the notebook to extract hidden messages from images.

### Detection

Apply Chi-Square analysis to suspect images to determine if they contain hidden data.

## How It Works

### Steganography Technique

1. **Pixel Selection**: Pixels are selected based on their color proximity to a specified key color within a given tolerance
2. **Data Embedding**: Secret bits are embedded in the least significant bits (LSBs) of the selected pixels
3. **Boundary Management**: The algorithm ensures embedding doesn't exceed image boundaries

### Chi-Square Detection

The detection method analyzes the distribution of LSBs in selected pixels:
- A uniform distribution (50% 0s and 1s) indicates natural randomness
- Deviations from uniformity suggest potential steganographic manipulation
- Lower Chi-Square statistics indicate higher detectability risk

## Examples

For more examples, including additional encoded messages, LSB distribution analysis, and step-by-step details, see [examples.md](examples.md).

## Project Structure

- `chisquare.ipynb`: Main implementation notebook
- `crypto.ipynb`: Additional cryptographic utilities
- `Examples/`: Sample images and outputs
- `examples.md`: Detailed example documentation

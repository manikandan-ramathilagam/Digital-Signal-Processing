# Digital-Signal-Processing
Edge Detection and Feature extraction

# Edge Detection and Feature Extraction

This repository contains the implementation and evaluation of various classical and advanced edge detection and feature extraction techniques. The project transitions from simple first-order derivative operators to the sophisticated, multi-stage Canny pipeline, analyzing their spectral responses and robustness to noise.

This work was completed as part of the **DSP Lab Course WS 2025/26** at Friedrich-Alexander-Universität Erlangen-Nürnberg (FAU).

## 🚀 Features & Implemented Algorithms

- **Gradient-Based Operators:** Implementation of first-order derivative operators including **Roberts**, **Prewitt**, and **Sobel** filters using discrete convolution kernels.
- **Laplacian of Gaussian (LoG):** A second-order derivative method optimized for finding zero-crossings, incorporating a Gaussian smoothing step to handle noise sensitivity.
- **Canny Edge Detection Pipeline:** A full multi-stage pipeline implementing:
  1. Noise reduction via Gaussian filtering
  2. Gradient magnitude and orientation analysis
  3. Non-Maximum Suppression (NMS) for single-pixel edge thinning
  4. Double thresholding (Strong, Weak, and Suppressed pixels)
  5. Hysteresis tracking to preserve structurally connected edges
- **Spectral Analysis:** 2D Fourier transforms applied to kernels and images (with zero-padding) visualized via 3D surface plots to evaluate frequency responses.
- **Noise Robustness Evaluation:** Testing performance against deterministic cosine noise and additive Gaussian noise.

## 🛠️ Tech Stack & Libraries

The project is fully realized within a **Python Jupyter Notebook** for clean code traceability and visualization.

- **Core Computation:** NumPy, SciPy
- **Image Processing:** SKImage (Scikit-Image)
- **Visualization:** Matplotlib

## 📊 Evaluation Summary

The algorithms were benchmarked on both synthetic checkerboard images (for controlled edge orientation analysis) and natural images from the **BSDS500** dataset:

- **Gradient Operators:** Act as directional high-pass filters. Roberts produces the thinnest edges, while Sobel offers slightly smoother contours than Prewitt.
- **Laplacian Operator:** Highly sensitive to noise, producing fragmented edges due to unstable zero-crossings when noise is present.
- **Marr-Hildreth (LoG):** Improves noise robustness through prior smoothing but achieves worse results on noise-free synthetic patterns.
- **Canny Detector:** Consistently yields the highest-quality results, producing thin, continuous boundaries and successfully filtering out noise-induced artifacts in real-world scenarios.

## 📂 Repository Structure

├── main.pdf              # Final project report
├── Project.ipynb         # Main Jupyter Notebook containing the implementation
└── README.md             # Project documentation

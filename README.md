Intelligent-plant-Leaf-disease-detection
# Intelligent Plant Leaf Disease Detection: A Hybrid DIP Approach
An automated agritech pipeline that combines Digital Image Processing (DIP) and lightweight machine learning to isolate, quantify, and classify plant leaf diseases from digital images. By shifting analysis from standard RGB space to device-independent color spaces, this project ensures robust detection under varying field lighting conditions.
 Features
Illumination Invariant Preprocessing: Uses CLAHE and Bilateral Filtering to remove background noise while preserving sharp lesion boundaries.
 * Dual-Engine Segmentation: Offers both targeted HSV/Lab Color Masking and unsupervised K-Means Clustering to partition background, healthy tissue, and diseased spots.
 * Automated Metrics Calculation: Real-time computation of the exact surface area percentage infected by the disease.
 * Texture Feature Extraction: Computes Gray-Level Co-occurrence Matrix (GLCM) features (Contrast, Homogeneity, Energy, and Entropy) for classification.
 * Interactive Web Dashboard: A built-in Streamlit interface allowing users to upload a leaf photo and view the image processing pipeline step-by-step.
## The Pipeline Workflow
The project processes raw leaf images through a structured matrix manipulation pipeline:
 1. Preprocessing: Raw Image -> Bilateral Filter (Noise Removal) -> CLAHE (Contrast Enhancement)
 2. Segmentation: RGB to HSV/Lab Conversion -> K-Means Clustering -> Binary Disease Mask
 3. Feature Analysis: Connected Components -> GLCM Texture Extraction -> Infection Percentage Calculation
Infection % = (Disease Cluster Pixels / Total Leaf Pixels) * 100
## Repository Structure
plant-disease-detection/
│
├── data/
│   └── sample_leaves/          # Demo images (Healthy, Rust, Spot, etc.)
│
├── src/
│   ├── **init**.py
│   ├── preprocessing.py        # Image resizing, filtering, and enhancement
│   ├── segmentation.py         # HSV Masking & K-Means Engine
│   ├── feature_extractor.py    # GLCM features and area calculation
│   └── classifier.py           # Disease category prediction logic
│
├── app.py                      # Streamlit UI Application
├── requirements.txt            # Project dependencies
├── notebook_demo.ipynb         # Step-by-step visual walkthrough
└── README.md                   # Project documentation
## Installation and Setup
### 1. Clone the Repository
~~~bash
git clone https://github.com/abhishekkrishna12-cloud/plant-disease-detection.git
cd plant-disease-detection
### 2. Install Dependencies
Make sure you have Python installed, then run:
pip install -r requirements.txt
### 3. Run the Web Application
streamlit run app.py
## Core Tech Stack
 * OpenCV (opencv-python): Primary matrix manipulations, color space conversions, and morphology.
 * Scikit-Image (scikit-image): GLCM texture feature extraction.
 * NumPy: High-speed pixel array math.
 * Streamlit: Frontend UI wrapper for quick interactive testing.
## License
This project is licensed under the MIT License - see the LICENSE file for details.

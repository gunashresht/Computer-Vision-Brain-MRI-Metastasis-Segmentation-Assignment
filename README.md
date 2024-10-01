# Computer-Vision-Brain-MRI-Metastasis-Segmentation-Assignment

Brain MRI Metastasis Segmentation
Project Overview
This project implements a deep learning model for segmenting brain metastases from MRI images. The model is based on the U-Net architecture, which is widely used for biomedical image segmentation tasks. This repository includes data preprocessing steps, model training, evaluation, and a FastAPI application for inference.

Table of Contents
Installation
Dataset
Data Preprocessing
Model Implementation
Training
Evaluation
Inference Web Application
Usage
Results
License
Acknowledgements
Installation
To run this project, you'll need to install the required libraries. You can use the following command:

bash
Copy code
pip install opencv-python albumentations torch torchvision fastapi uvicorn matplotlib
Dataset
The dataset used for this project consists of brain MRI images and corresponding segmentation masks. The dataset can be downloaded from this link.

Dataset Structure
The dataset should be organized as follows:

kotlin
Copy code
data/
    ├── images/
    │   ├── image1.png
    │   ├── image2.png
    │   └── ...
    └── masks/
        ├── mask1.png
        ├── mask2.png
        └── ...
Data Preprocessing
Data preprocessing steps include:

Contrast Limited Adaptive Histogram Equalization (CLAHE): Enhances contrast in MRI images.
Normalization: Scales pixel values to the range [0, 1].
Augmentation: Includes random flips, rotations, and brightness adjustments to enhance model generalization.
The preprocessing is handled in the preprocessing.py file.

Model Implementation
The segmentation model is implemented using the U-Net architecture. The U-Net model consists of an encoder-decoder structure with skip connections. The model is defined in the model.py file.

Training
The model is trained using the following parameters:

Loss Function: Binary Cross-Entropy Loss (BCE)
Optimizer: Adam
Number of Epochs: 20
Batch Size: 8
Training scripts can be found in train.py.

Evaluation
Model evaluation is performed using metrics such as the DICE coefficient. The evaluation script is located in evaluate.py.

Inference Web Application
A FastAPI application is provided for inference, allowing users to upload MRI images and receive segmentation masks.

How to Run the Web Application
Navigate to the directory where main.py is located.
Run the FastAPI application using the command:
bash
Copy code
uvicorn main:app --reload
Access the API documentation at http://127.0.0.1:8000/docs to test the /predict/ endpoint.
Usage
To use the model for segmentation:

Upload an MRI image via the web application.
The API will return the predicted segmentation mask as a JSON response.
Results
The model achieves promising results in segmenting brain metastases, as illustrated by the validation metrics and visualizations included in the evaluation section.

License
This project is licensed under the MIT License.

Acknowledgements
U-Net architecture paper: Ronneberger et al., 2015. "U-Net: Convolutional Networks for Biomedical Image Segmentation."
Albumentations for data augmentation techniques.

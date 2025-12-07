# Retina Vessel Segmentation using U Net

This project focuses on segmenting retinal blood vessels from fundus images using a U Net based deep learning model. The goal is to build a simple, clear, and reproducible pipeline that loads the dataset, pairs images with their masks, trains a U Net, evaluates the model, and visualizes the predicted segmentation maps. The notebook includes complete data preprocessing, model architecture, training loop, loss calculation, visualization of results, and basic performance checks. This is a self driven side project created to improve understanding of image segmentation, medical imaging workflows, and deep learning experiment design. Everything is kept straightforward so the project can be extended later for other datasets or accelerated hardware platforms.

<img width="1920" height="1011" alt="image" src="https://github.com/user-attachments/assets/a0f2f359-43f4-45b4-9dca-6f4ebe1b8dfa" />

## Features

- Complete preprocessing of fundus images and corresponding vessel masks
- Automatic pairing of images and labels using file basename
- U Net architecture implemented in PyTorch
- Training and validation loops with loss tracking
- Visualization of predictions and ground truth masks
- Lightweight and easy to run on GPU or CPU
- Notebook focused workflow for learning and experiments

## Dataset

The project uses retinal fundus images along with manually annotated vessel masks. Files are paired by matching the same basename.

https://www.kaggle.com/datasets/abdallahwagih/retina-blood-vessel 

## Results: 

<img width="1442" height="755" alt="image" src="https://github.com/user-attachments/assets/f9c182ce-ce2c-4716-aa35-db265c97f45c" />


<img width="1599" height="995" alt="image" src="https://github.com/user-attachments/assets/e612d292-2a03-461b-bc37-aa755c629e97" />


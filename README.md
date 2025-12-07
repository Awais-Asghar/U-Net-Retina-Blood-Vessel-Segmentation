# Retina Vessel Segmentation using U-Net

Project goal is to automatically segment blood vessels from retinal images using a convolutional encoder decoder architecture. Accurate vessel segmentation helps in early diagnosis of diseases such as diabetic retinopathy, glaucoma, hypertension, and cardiovascular disorders. This project focuses on segmenting retinal blood vessels from fundus images using a U Net based deep learning model. The goal is to build a simple, clear, and reproducible pipeline that loads the dataset, pairs images with their masks, trains a U Net, evaluates the model, and visualizes the predicted segmentation maps. The notebook includes complete data preprocessing, model architecture, training loop, loss calculation, visualization of results, and basic performance checks. This is a self driven side project created to improve understanding of image segmentation, medical imaging workflows, and deep learning experiment design. Everything is kept straightforward so the project can be extended later for other datasets or accelerated hardware platforms.

<img width="1920" height="1011" alt="image" src="https://github.com/user-attachments/assets/a0f2f359-43f4-45b4-9dca-6f4ebe1b8dfa" />

## Features

- Complete preprocessing of fundus images and corresponding vessel masks
- Automatic pairing of images and labels using file basename
- U Net architecture implemented in PyTorch
- Training and validation loops with loss tracking
- Visualization of predictions and ground truth masks
- Lightweight and easy to run on GPU or CPU
- Notebook focused workflow for learning and experiments

## Workflow Overview

1. Load image and mask paths
2. Pair images and masks by matching filenames
3. Preprocess both (resize, normalize, convert to tensor)
4. Create PyTorch Dataset and DataLoader
5. Build U Net model
6. Train the model for fixed epochs
7. Track training and validation loss
8. Generate sample predictions
9. Visualize predicted mask vs ground truth
10. Save results

## Why U Net

* Works well for pixel level segmentation
* Performs well on small medical datasets
* Preserves spatial details using skip connections
* Handles thin structures like blood vessels
* Efficient and easy to train

## Model Information

Architecture: **U Net**
Key components:

* Encoder: series of convolutions that reduce spatial size
* Decoder: upsampling layers that recover resolution
* Skip connections: pass encoder features to decoder for detail recovery
* Output: binary mask of vessel and non vessel pixels

Activation used for mask: **Sigmoid**
Loss function (typical): **Binary Cross Entropy**
Possible improvements: Dice loss or BCE + Dice hybrid

## Dataset

The project uses retinal fundus images along with manually annotated vessel masks. Files are paired by matching the same basename.

https://www.kaggle.com/datasets/abdallahwagih/retina-blood-vessel 

Details:

* Contains 40 high resolution fundus images
* Includes manually annotated vessel masks
* Standard train–test split provided
* Image and mask filenames match by basename
* Mask represents pixel level blood vessel boundaries

Folder format expected:

```
images/
    image_01.png
    image_02.png
masks/
    image_01.png
    image_02.png
```

## Visualizations Included

Notebook contains:

* Random sample image and mask preview
* Predicted vessel maps
* Training loss curve
* Side by side comparisons

## Results Summary

* The U Net model successfully identifies major and minor retinal vessels
* Thin vessel structures are captured but can improve with augmentation
* Output masks align well with ground truth when trained properly
* Performance depends strongly on preprocessing and loss function

<img width="1442" height="755" alt="image" src="https://github.com/user-attachments/assets/f9c182ce-ce2c-4716-aa35-db265c97f45c" />


<img width="1599" height="995" alt="image" src="https://github.com/user-attachments/assets/e612d292-2a03-461b-bc37-aa755c629e97" />


## Limitations

* Dataset is small (only 40 images)
* Thin vessels are hard to detect
* No augmentation currently reduces generalization
* Model can overfit without validation monitoring

## Tools Used

* Python
* PyTorch
* NumPy
* Matplotlib
* Jupyter Notebook
* DRIVE dataset

## Future Improvements

* Use larger retinal datasets like STARE or CHASE DB1
* Optimize model for edge devices or real time use
* Replace base U-Net with Attention U Net or Residual U-Net

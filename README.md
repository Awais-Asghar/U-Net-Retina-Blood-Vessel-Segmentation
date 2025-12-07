# Retina Vessel Segmentation using U-Net

Project goal is to automatically segment blood vessels from retinal images using a convolutional encoder decoder architecture. Accurate vessel segmentation helps in early diagnosis of diseases such as diabetic retinopathy, glaucoma, hypertension, and cardiovascular disorders. This project focuses on segmenting retinal blood vessels from fundus images using a U Net based deep learning model. The goal is to build a simple, clear, and reproducible pipeline that loads the dataset, pairs images with their masks, trains a U Net, evaluates the model, and visualizes the predicted segmentation maps. The notebook includes complete data preprocessing, model architecture, training loop, loss calculation, visualization of results, and basic performance checks. This is a self driven side project created to improve understanding of image segmentation, medical imaging workflows, and deep learning experiment design. Everything is kept straightforward so the project can be extended later for other datasets or accelerated hardware platforms.

<img width="1878" height="1016" alt="Image" src="https://github.com/user-attachments/assets/25f6171f-1258-4b7d-832a-b2755e8ac271" />

<img width="1871" height="1007" alt="Image" src="https://github.com/user-attachments/assets/d085b1ee-f198-4141-8d18-c6fec5022e44" />

----

## Features

- Complete preprocessing of fundus images and corresponding vessel masks
- Automatic pairing of images and labels using file basename
- U Net architecture implemented in PyTorch
- Training and validation loops with loss tracking
- Visualization of predictions and ground truth masks
- Lightweight and easy to run on GPU or CPU
- Notebook focused workflow for learning and experiments

<img width="1869" height="1004" alt="Image" src="https://github.com/user-attachments/assets/709172e1-4ad9-4e3c-ac9a-ec76e8e5762c" />

---

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

<img width="1870" height="1008" alt="Image" src="https://github.com/user-attachments/assets/acae2e21-db6d-496c-9b2f-f11c5862e7c1" />

---

## Why U Net

* Works well for pixel level segmentation
* Performs well on small medical datasets
* Preserves spatial details using skip connections
* Handles thin structures like blood vessels
* Efficient and easy to train

<img width="1867" height="1014" alt="Image" src="https://github.com/user-attachments/assets/4ea7842d-8a02-4bfe-abcc-c05170ee75c0" />

---

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

## Visualizations Included

Notebook contains:

* Random sample image and mask preview
* Predicted vessel maps
* Training loss curve
* Side by side comparisons

<img width="1000" height="500" alt="Image" src="https://github.com/user-attachments/assets/f0d900d8-776b-4712-b93e-a29054c4a818" />


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

<img width="1865" height="993" alt="Image" src="https://github.com/user-attachments/assets/e846bee4-5c81-4017-a5b8-3d0af5c11ea4" />

---

## Results Summary

* The U Net model successfully identifies major and minor retinal vessels
* Thin vessel structures are captured but can improve with augmentation
* Output masks align well with ground truth when trained properly
* Performance depends strongly on preprocessing and loss function

<img width="1865" height="983" alt="Image" src="https://github.com/user-attachments/assets/8e26a615-502b-4c8d-88e1-12d405846e68" />


<img width="1442" height="755" alt="image" src="https://github.com/user-attachments/assets/f9c182ce-ce2c-4716-aa35-db265c97f45c" />


<img width="1599" height="995" alt="image" src="https://github.com/user-attachments/assets/e612d292-2a03-461b-bc37-aa755c629e97" />

<img width="1875" height="1015" alt="Image" src="https://github.com/user-attachments/assets/38b7a787-c970-4cf3-8170-86f417ec7c64" />

<img width="1859" height="1015" alt="Image" src="https://github.com/user-attachments/assets/96d66b8d-d90b-4c0f-adfe-d7ad1754e9e4" />

<img width="1857" height="1003" alt="Image" src="https://github.com/user-attachments/assets/2c5ad349-56f2-4095-91af-178ccd4f0f44" />

---

## Limitations

* Dataset is small (only 40 images)
* Thin vessels are hard to detect
* No augmentation currently reduces generalization
* Model can overfit without validation monitoring

<img width="1870" height="999" alt="Image" src="https://github.com/user-attachments/assets/a7e171dc-8e0d-4d47-835f-062ccfd1b9d4" />

---

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

<img width="1862" height="993" alt="Image" src="https://github.com/user-attachments/assets/3febcacf-2fb2-454c-b15b-7b6351b0cb8c" />

<img width="1872" height="777" alt="Image" src="https://github.com/user-attachments/assets/f8cc3202-70aa-4d66-8f45-8bd3e1874ea6" />

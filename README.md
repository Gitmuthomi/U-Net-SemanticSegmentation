# Forest Segmentation using U-Net Model
## Introduction
This project performs semantic segmentation on forest imagery using a U-Net model with a pre-trained ResNet50 encoder. The decoder is an upsampler that turns the features into a segmentation mask. The dataset contains images and corresponding masks indicating forested areas.

## Dependancies
The following libraries are required to run the project:
- `tensorflow >= 2.18.0`
- `numpy`
- `pandas`
- `matplotlib`
- `os`
- `kagglehub`

## Dataset
The dataset was obtained from [Kaggle](https://www.kaggle.com/datasets/quadeer15sh/augmented-forest-segmentation/data) which contained labelled images of forested areas in .jpg format and their corresponding masks. Below is the file structure of the dataset:

Forest Segmented/ # Root_content_path

├── Forest Segmented/ # Nested_content_path 

    │   ├── images/ # Raw images 

    │   ├── masks/ # Corresponding masks 

    |   ├── Test/ # test images and masks
            ├── images

            ├── masks

## How to Run the Model
1. **Preprocess the data**

The notebook uses `ImageDataGenerator` to auto-generate `train` and `val` splits from the raw `images/` and `masks/` folders and normalize the pixel values to the [0, 1] range. All images and masks are resized to 256×256 pixels for uniformity.

2. **Train the model**

Run the notebook cells in order to:
- Build the U-Net model with ResNet50 encoder backbone and upsample decoder.
- Train for 30 epoch with early stopping.
- Loss function: `Binary Cross-Entropy`.
- Optimizer: `Adam`.

3. **Evaluate the Model**

The script evaluates the trained model on the validation set and reports IoU, Mean Average Precion (mAP) and loss metrics.



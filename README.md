# Detection of retinal fundus vessels

## Project description

This project is about the automatic detection of blood vessels in retinal fundus images. The main objective is to develop an application that analyses a given input image and classifies pixels as blood vessels or background. The project uses both classical image processing techniques and advanced methods based on deep neural networks (UNet) to segment blood vessels.

## Features

- **Image pre-processing**:

  - **Green channel selection** - due to the highest blood vessel contrast in the green channel of the RGB image, it was selected for further analysis.
  - **Gamma correction** - increasing the contrast in darker areas of the image and decreasing in lighter areas to better highlight the blood vessels.
  - **Morphological Closure** - filling in holes and merging closely located objects and removing minor imperfections.

- **Image processing**:

  - **Creating a binary mask** - classifying pixels into those belonging to blood vessels and background, using filters such as the Frangi filter.

- **Final image processing**:

  - **Morphological dilation** - merging closely located objects, filling in holes and expanding objects.
  - **Morphological erosion** - reducing object size, removing noise and improving object separation.
  - **Edge removal** - eliminating unwanted elements from images, improving the quality of analysis.

- **UNet**:
  - **Data augmentation** - extending the training set by modifying existing images (allows for better model generalisation).
  - **Model training** - teaching the segmentation model on retinal fundus images to accurately detect blood vessels.
  - **Statistical analysis** - evaluating model performance through confusion matrices and calculating measures such as accuracy, sensitivity and specificity.

## Project structure

- `images/`: folder containing retinal images.
- `labels/`: folder containing the expert masks for the images.
- `basic_processing.ipynb`: notebook containing image preprocessing and implementation of simple vessel detection techniques.
- `unet.ipynb`: notebook containing UNet implementation, training and testing on retinal images.
- `README.md`.

## Data

The project uses images from the [STARE](https://cecas.clemson.edu/~ahoover/stare/probing/index.html) database, which contains images used for blood vessel analysis.

## Visualisation of results

The results of the algorithm are visualised through binary masks, where pixels belonging to blood vessels are highlighted. In addition, the results are compared with expert masks (ground truth), and the performance of the algorithm is evaluated based on selected metrics.


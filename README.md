# FewGAN
FewGAN : Face Editing eith Generative Adversarial Network with User's Sketch and Color

## Overview
Edit face images using a a deep neural network. Users can edit face images using intuitive inputs such as sketching and coloring, from which our network SC-FEGAN generates high quality synthetic images. We used SN-patchGAN discriminator and Unet-like generator with gated convolutional layers.

![Teaser Image](imgs/teaser.jpg)

## Dependencies
- tensorflow
- numpy
- Python3
- PyQt5
- opencv-python
- pyyaml

## Setup
First, download the model from [Google drive](https://drive.google.com/open?id=1VPsYuIK_DY3Gw07LEjUhg2LwbEDlFpq1).

Run these commands to start the program.
  ```
  mv /${HOME}/SC-FEGAN.ckpt.* /${HOME}/ckpt/
  python3 demo.py
  ```
  
Select the number of GPUs you want to use by editing `demo.yaml` file (multi-GPUs are not supported).
  ```
  GPU_NUM: 1 (the number you want to use)
  #GPU_NUM: (if you want to use only CPU, erase the number)
  ```

## How to Use
Edit face images using a simple GUI. Only erased regions of the image are filled in by the network.

Explanation of the buttons:

- `Open Image`: Open the image you want to edit.
- `Mask`: Draw a mask on the desired regions of the face on the left viewer.
- `Sketches`: Sketch the desired lines on the left viewer.
- `Color`: Draw colored lines. If you click this button the first time, you have to choose a color from the palette.
- `Palette`: Change color. After choosing a color, click the `Color` button to apply the change.
- `Save Img`: Save the results. It is saved as '*name.jpg*'.
- `Arrange`: Arrange the editing works.
- `Undo`: Undo previous editing work.
- `Complete`: Generate the image and show it on the right viewer.

  
We recommend using the following workflow:
  ```
  1. Draw the sketch plausibly referring to the original image.
  2. Draw the mask on the sketched region.
  3. Click the `Arrange` button.
  4. Draw the color on the masked region.
  5. Click `Complete'.
  ```  

## Example Results
### Face editing
![Face editing](imgs/face_edit.jpg)

### Edit earring
![Earring](imgs/earring.jpg)

### Face restoration
![restore1](imgs/restoration.jpg)

### Face restoration (with only sketch and color)
![restore2](imgs/restoration2.jpg)

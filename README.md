# POLY-GAN
Poly-GAN: Multi-Conditioned GAN for Fashion Synthesis
# Abstract

We present Poly-GAN, a novel conditional GAN architecture that is motivated
by Fashion Synthesis, an application where garments are automatically placed on
images of human models at an arbitrary pose. Poly-GAN allows conditioning on
multiple inputs and is suitable for many tasks, including image alignment, image
stitching and inpainting. Existing methods have a similar pipeline where three
different networks are used to first align garments with the human pose, then
perform stitching of the aligned garment and finally refine the results. Poly-GAN
is the first instance where a common architecture is used to perform all three tasks.
Our novel architecture enforces the conditions at all layers of the encoder and
utilizes skip connections from the coarse layers of the encoder to the respective
layers of the decoder. Poly-GAN is able to perform a spatial transformation of the
garment based on the RGB skeleton of the model at an arbitrary pose. Additionally,
Poly-GAN can perform image stitching, regardless of the garment orientation,
and inpainting on the garment mask when it contains irregular holes. Our system
achieves state-of-the-art quantitative results on Structural Similarity Index metric
and Inception Score metric using the DeepFashion dataset.


# Architecture of POLY-GAN
![Alt text](https://github.com/nile649/POLY-GAN/blob/master/images/Pipeline_Poly_Gan_final_3.png?raw=true "Flow Diagram")

![Alt text](https://github.com/nile649/POLY-GAN/blob/master/images/Poly_Gan_Inside(1)(2)(3)(1)(1).png?raw=true "Architecture")

# Libraries:
cat requirements.txt | xargs -n 1 pip install

# Dataset Preparation:
Download dataset from https://github.com/sergeywong/cp-vton.
We may provide dataset in future.
1. Pose estimator framework (LCR Net++, OpenPose).
2. Segmentation framework (Unet, Unet++).
3. Follow the steps in paper.


# Test:
Download pre-trained models and Data from https://drive.google.com/drive/folders/18eu3OrNh9TbmiED0sotbzGPtLCCecSeT?usp=sharing
It has pre-trained weights for Stage 1, Stage 2 and Stage 3.


In test.py, you need to provide location of the pre-trained weights of the stage you will be testing, Target and Reference Image name as well.

The dataset used is borrowed from the code CP-VTON
https://github.com/sergeywong/cp-vton

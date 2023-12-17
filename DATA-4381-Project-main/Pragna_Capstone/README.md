# Stroke Lession Segmentation
## Overview
This project is dedicated to developing a model designed to perform image segmentation on MRI scans specifically focused on ischemic strokes.

## Data
The annotated dataset comprises 400 multi-vendor MRI cases, offering high variability in stroke lesion size, quantity, and location. It is divided into a training dataset (n = 250) and a test dataset (n = 150).
This dataset underlies the ISLES 2022 challenge, found at https://www.isles-challenge.org/. The main aim is to identify algorithms for developing and benchmarking automatic and accurate segmentation methods for ischemic stroke.
* Files are given in .nii format (NifTi)

## Types of MRI
The MRIs this dataset gives us are:
* Diffusion Weighted imaging (DWI): captures how water molecules move in tissues, highlighting areas of restricted or free water movement
* ADC maps show how water moves in tissues and give characteristics based on the speed and direction of water diffusion
* Perfusion Weighted imaging (PWI): maps blood flow by using a contrast agent, assisting in assessing blood supply
* Fluid attenuated inversion Recovery (FLAIR): suppresses signals from cerebrospinal fluid, enhancing the visibility of brain lesions


## Preprocessing
* Image Rescaling: Resize the images to a consistent resolution if they vary in size.
* Normalization: Normalize pixel values to a standard range (e.g., [0, 1] or [-1, 1]). 
* Review and Cleaning: Check for any inconsistencies in the data. 
* Format Conversion: Ensure that the data is in a format that is compatible with the framework planned.

## Annotation Methods
The dataset given comes annotated, but in case another dataset is used and it is not annotated, medical annotations can be done by
* 3D Slicer: open-source platform for medical image analysis. It supports 2D and 3D image visualization, segmentation, registration, and more.
* AIM: Annotation and Image Markup is developed by the National Cancer Institute (NCI) for representing and sharing annotations on medical images.
* Annotator for DICOM is an open-source tool designed for annotating DICOM images.

## In Process
* Completion of preprocessing
* Model methods
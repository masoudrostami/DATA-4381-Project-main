# Capstone
Transfer Learning &amp; Generative AI w/ Pollen Dataset &amp; Lice

- This repository documents the process of using transfer learning to perform image classification on a Pollen dataset.

# Overview: 
- The challenge of this project is to utilize transfer learning & learn the features of Pollen grain images to accurately predict which category they belong to.
- In this repository, our approach is to use labeled/sorted data & perform categorical classification with 5 folders worth of 100-200 Pollen grain images. Using ImageNet weights & the Pollen training data, we used the ResNet101V2 architecture.  
-    ResNet101V2's performance suggests overfitting, clocking around a 99% accuracy and a 96% validation accuracy. Further plans involve Data augmentation, L1 regularization & using less complex models to solve overfitting.

# Data: 
- There are 5 folders of each category, for the families/species of pollen 
and lice.
- The total image count is 2273: 1034 for pollen and 1239 for 
lice. ​
-Pollen images are taken using Light-Field Microscopy while Lice images 
use both light and dark-field microscopy.       

- Pollen images are a consistent resolution of 300x300 px
  
- Pollen images are centered and retain most visual detail while the edges 
are blurry.

- Lice images on the other hand are not visually consistent & contain many 
imperfections like stains, debris, poor polarization. Photos also lack 
proper rotating, & the  subject can also be in the corner of the 
image instead of the center. 
 
# Pre Processing
- So far, most of the preprocessing has gone into image encoding as well 
as one hot label encoding for categorical classification purposes.
- Code exists to augment the data with the following effects:
* random flip/crop/center/rotate
* random brightness & contrast 
* Normalization
The choice behind these effects are to simulate the distortions and 
imperfections in the Lice dataset, so it does well outside of training.

this section will be updated when the Lice dataset is tested.

# Data visualization:
<img width="456" alt="Screen Shot 2023-12-15 at 10 22 31 PM" src="https://github.com/masoudrostami/DATA-4381-Project/assets/111654423/b87b50f1-bf80-4c11-8753-5558b4cfc5ac">
<img width="439" alt="Screen Shot 2023-12-15 at 10 22 20 PM" src="https://github.com/masoudrostami/DATA-4381-Project/assets/111654423/cbb09310-63df-4964-a622-be145a8313fc">



- The above Truth Labels indicate that ResNet101V2 has had no problems 
recognizing where the images originate from. With a batch size of 32, we 
are still curious to see how these change with more data.

# Training:

- The training was done using the TensorFlow dataset package as well as 
Keras' pretrained model API.   
- The Data was split 80% training, 20% validation 
- Training for each epoch took 70-90 seconds 
- Training loss vs. Epoch:
- ![Unknown](https://github.com/masoudrostami/DATA-4381-Project/assets/111654423/05266c7f-dbe0-45c9-ad6f-d7d7f11e5ec0)

* 1.8284 Training loss in 1st epoch
* .2293 Training loss in 10th epoch

- Training will continue so as to allow for augmentaation, L1 activation, 
& eventually expand training to the Lice dataset. We are also interested 
in comparing multiple model architectures for our dataset.

- The only difficulties so far were problems with overfitting, & applying 
augmentation.
- Overfitting was solved by changing the dropout rate from .5 to .2 & 
changing learning rate to 1e^-4

- As of Dec 12 2023, still in training phase. 


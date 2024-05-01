Part 2 of Assignment 2 for CS 587 - Adversarial Machine Learning course, taught by Alexandar Vakanski in Spring 2024 at the University of Idaho - Department of Computer Science.

The objective of this assignment is to create a substitute model for celebrity recognition, and transfer adversarial samples to a corresponding model hosted by Clarifai. This is a black-box attack, because we don’t have access to the model hosted by Clarifai.

We utilized a dataset comprising celebrity faces, extracted from a larger dataset known as LFW ( Labeled Faces in the Wild: https://vis-www.cs.umass.edu/lfw/ ). These images were sourced from the internet and annotated with individuals' names. Specifically for this assignment, our dataset encompassed 5,113 images featuring 62 different celebrities, with each image focusing solely on the cropped face of the individual from the original pictures.

We used the Vision Transformer (provided code named ViT_PyTorch) as a guidance for training the model. The code employs a Vision Transformer (ViT) with a Linformer backbone. We received the Test Accuracy of the model: 83.60 %.

We applied PGD attack to create non-targeted adversarial sample on various subsets of the test dataset.

(

import cleverhans 

from cleverhans.torch.attacks.projected_gradient_descent import projected_gradient_descent

)

Finally, we uploaded the adversarial samples to Clarifai's website to check if it is misclassified and tracked the minimum perturbation level for the image to be misclassified by the Clarifai’s model.

In the Report section, we have provided the original images and the ground-truth labels, the adversarial images, the predictions by the Clarifai’s model, and stated the applied level of perturbation. We also provide a brief discussion on the target model, and how diffcult it was to perform the attacks.

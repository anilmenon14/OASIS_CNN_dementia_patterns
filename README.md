## OASIS 1 and 2 MRI data for dementia analysis using Convolutional Neural Networks

#### This project was conducted in Jan and Feb 2023 as part of the Milestone II of Master's of Applied Data Science program at University of Michigan.

**Collaborators** : Anil Menon, Kenny Tang


**Objective** : Use convolutional neural networks to be able to gain insights relating to dementia using MRI data 

**Introduction and motivation behind project** :  

The challenge with onset of dementia is that it progresses slowly over time, which poses a challenge for care planning as it is hard to diagnose early. A patient suffering from chronic dementia has complex care planning needs. If dementia is diagnosed late, it could be very challenging for the affected individual, close family members, and healthcare institutions. Our team is motivated by the idea of having insight into early pattern identification for patients who are in pre or early stages of dementia through machine learning of brain Magnetic Resonance Imaging (here on, abbreviated as ‘MRI’) images using MRI imaging of patients who have been recently diagnosed with mild to moderate dementia.  
  
The supervised methods we are exploring is binary classification of demented and non-demented patients using Convolutional Neural Networks (abbreviated henceforth as ‘CNN’). Additionally, using the rich activation maps of weights generated in several layers in the process, we are using unsupervised methods to be able to derive meaning through clustering subjects into groups.  
  
In this project we attempted a novel approach of reviewing which of the planes of the MRI (Sagittal, Coronal or Transverse) has a better signal to help classify dementia for patients. This report will go through our findings in depth; however, a brief summary of our findings can be stated as below:  
- Processed MRI slices, that have been chosen by a radiologist as a summarized representation of the patients’ entire MRI, produces better accuracy and recall than stitching together different frames of the MRI and using it for training. Additionally, the former is several orders of magnitude efficient in terms of computational needs, however the latter is an alternative in the absence of processed images.
- The CNN model performs significantly better than the chosen baseline tree based (Random Forest) and probabilistic models (Naive Bayes) in metrics of accuracy and recall.
- In unsupervised learning, we could empirically prove that 2 clusters are the optimal number and could get insight on the distribution of ground truth labels through manifold representations of the data.


**Code reproducability and future work** :  

The code in `code` folder has been written in a way where it can build up the entire data pipeline required for the project from scratch and hence should be suitable lightweight code option for anyone who would like to continue work from a computing environment of their choice.

In this project, the work we felt could be carried on were the following:
- Since the ‘Processed’ technique led to the best results from this project, our team is curious to find out if there is a semi-supervised way to arrive at a processed 2-D view of an MRI, if a complete 3-D volume of that MRI is provided. This would essentially be a dimensionality reduction technique that continues to ensure that features that are signals for dementia continue to be in the processed image. Future work in this area would be beneficial both from a model improvement as well as computational efficiency standpoint.
- Continuous development of the CNN model can potentially lead to better feature representations for the unsupervised clustering models. Additionally, it would help to further explore other manifold learning methods such as UMAP in an attempt to learn more about the structure of the data and what other information our clusters hold.

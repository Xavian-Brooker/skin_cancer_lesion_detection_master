# Skin_cancer_lesion_detection_master
## Background ##
Skin Cancer is one of the most common type of cancer around the globe.  It is stated that one in every five american will develop skin cancer till the age of 70. 
When there is an abnormality in the skin cells than a tumor is formed. When this tumor is prevalent only uptill the *epidermis* than its called **Benign Tumor** but when it penetrates and enters the lower layer called *dermis* than it is called **Malignant Tumor** which can spread to other body parts. The most dangerous type of skin cancer is called **Melanoma** which is estimated to kill nearly 9,320 people in the USA.

## What is this project about? ##
This project explains how to classify skin cancer images into benign, intermediate or malignant so that if the cancer is detected early than its almost curable. *Note - You need not to rely on this algorithm as it might be wrong, so if it shows a positive result, kindly contact a nearby dermatologist for confirmation.*

## Data Collection ##
To train the classifier, the images were taken from [ISIS Archive](https://www.isic-archive.com/#!/topWithHeader/onlyHeaderTop/gallery). By setting the diagnostic attribute to **benign**, the filtered images were downloaded, then again by changing the attribute to **intermediate('s)** and finally to **malignant**. As the main dataset is humoungous, I chose to try this algortihm with just 500 images per class, you can choose to increase the dataset to further increase the accuracy. The image data was stored in this way -

`\train
  
  \benign
  
  \intermediate
  
  \malignant`
  
## Algorithm ##
To achieve better accuracy, Google's Inception was retrained by following the [tensorflow-for-poets](https://codelabs.developers.google.com/codelabs/tensorflow-for-poets/) & by using the script written in the `commands_to_retrain.txt` file. There are other options such as MobileNets model which is actually mentioned in the `tensorflow-for-poets` guide for lower latency & inference etc. 
You might also have to change the image_dir, bottlenecks_dir & output_graph, output_labels as per your directory. 
For training, epochs were set to default (4000 epochs) and so the flag `--how_many_training_steps` was not mentioned in the bash script. You can tweak the `--learning_rate` for variance in the performance.  

## What Next? ##
After the model has been retrained it outputs a `retrained_inception1.pb` file & a `retrained_graph.txt` file. You can either create a tensorflow program that imports this `savedModel` file and uses it for inference, or you can deploy the trained file into mobile devices by following the [tensorflow-for-poets-2](https://codelabs.developers.google.com/codelabs/tensorflow-for-poets/#8)guide.

## Contribution to the society ##
As every developer tries to use ML in the field of Medicine to fight terminating diseases such as Cancer is contributing something to the society. Cheers!

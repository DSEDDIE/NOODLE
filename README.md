# Lululemon Athletica
## Machine learning Multi-Image Classification
<img width="1107" alt="Unknown" src="https://user-images.githubusercontent.com/109767578/212406975-c552819f-c1c8-42ef-b6c3-612ce6a0d9b0.png">
Author: Edward Juarez

## Introduction
For this capstone project, I worked with a hypothetical client Chief Brand officer and the Lululemon marketing department. They're launching an aggressive global marketing campaign on all social media platforms promoting and attracting new customers that may feel intimidated to start practicing yoga in they’re studio or in general incentivising a reward system for any individual submitting photos of themselves with five specific yoga poses that Lululemon requires. This will also provide clarity to someone that has limited to no knowledge of yoga poses. They can also provide examples of how a pose is done from other peoples images creating a social network. They can also use this data as customer engagement. Providing accuracy, if they are doing the poses correctly or not. They are expecting an enormous feed back that would reqiure alot of time and employee efficiency.

## Business Objective
Our goal is to create a multi image classification model by using artificial intelligence algorithms, a multi-layer Convolutional Neural Network that can identify five different yoga poses these poses are `downward dog pose` ,`tree pose`, `plank pose`, `goddess pose` and the `warrior 2 pose`. The model output from this project can be used to identify yoga poses and gain reliable data.

## Data Understanding
The data used was from Kaggle,([you can find it here](https://www.kaggle.com/datasets/niharika41298/yoga-poses-dataset) )a yoga pose data set. That consist of 1550 images with Rgb color values with an alpha channel which specifies the opacity for a color. We analyze 1550 still images from 5 image classes to create a multi-image classification model that would help their marketing department correctly identify image classes. With our analysis and modeling.

<img width="1263" alt="Screen Shot 2023-01-13 at 3 17 07 PM" src="https://user-images.githubusercontent.com/109767578/212411662-255c6454-c525-40b8-934f-bf184c3e0513.png">

`Downward dog pose`  
`Tree pose`  
`Plank pose`  
`Goddess pose`  
`Warrior 2 pose`  

## Data Preparation
I started off by importing neccessary libraries. Then loaded and splitting the dataset into `training`, `test`, and `validation`, since the dataset was small in number I did a 80-20 split on the train dataset to use an alternative set of images for validation.
for the images I Rescale=1./255 to convert the pixels in range [0,255] to range [0,1]. This process is also called Normalizing the input. Scaling every images to the same range [0,1] will make images contributes more evenly to the total loss. I started to Explore the Dataset by by looking at `class_indices` then began to randomly apply `array_to_img`to visualize the images in the Dataset.

## Modeling
We start off with a baseline model that had one dense layer, I then made it a Convolutional network by adding convolutional layers , I try to do augmentation to get better results, for example augmentation can pull more information from a small dataset, but I still saw the model under fit. I then added more dense layers and convolutional layers, and also adjusted my Hyperparameters and filters. Ultimatley in a combination of all that that let us to a very overfit model and high complexity which we then needed to regularized using drop out layers in order to address the overfitting . I arrived at my final model giving us an `Accuracy Score`of 86 on validation data. The architecture of my final model
As you will see, we startered off with a convolution layer followed by a max pooling. I proceeded to do this several times adjusting the parameters at the same exact time and finally towards the end I then added drop out layers because I was seeing previous iterations of being over fit. Below I will provide the Final models' architecture.


<img width="750" alt="Final_mod_Architecture" src="https://user-images.githubusercontent.com/109767578/212430533-58dc963d-08c0-4155-8806-c5ea206b2a28.png">

This shows a comparison of the Baseline Model and Final Models' accuracy scores.

<img width="1109" alt="baseline final_chart" src="https://user-images.githubusercontent.com/109767578/212431008-41e40b8c-495a-48ef-a3f2-05b4879d2338.png">

## Evaluation
As a result here is our final model performance on unseen data we have an accuracy score of 91 this is an idea how it may generalize in the real world.As I said before we chose Accuracy as our metric to evaluate our model . Here is a confusion Matrix of our models classifications. The diagonals are our correct predictions as you can see we are doing very well. Our highest amount of error by falsely mis-identifying `goddess pose` with a `warrior 2 pose`. Note as I mention before these are some of the challenges that can arise due to these poses having the same formation when inverted. 

<img width="706" alt="Conf_MatrX" src="https://user-images.githubusercontent.com/109767578/212432106-9cb17f7f-7843-4a8e-8773-9ef54f28bb61.png">

## Conclusion
So what does this mean for Lululemon? At some level of accuracy they can identify some yoga poses.
So Lululemon can take the information relay back to the customer and informed their user if they are accuratley doing the pose. Lululemon also gains reliable data and can add new sales growth opportunities with this data at the same exact time it would allow us to gather up more images for future projects , such as ,segmentation leading to virtual Try on for clothing, accessories and other items improving user experience. Other uses could include face recognition which could enable current contactless payments with one's face as a proof.

## For More Information
Please review my full analysis in [my Jupyter Notebook](https://github.com/DSEDDIE/lulu_multi_image_proj/blob/main/Lululemon%20final%20notebook.ipynb) or my [presentation]().
 
For any additional questions, please contact 


 



 

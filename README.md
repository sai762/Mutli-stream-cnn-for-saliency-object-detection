# Mutli-stream-cnn-for-saliency-object-detection


Saliency detection is finding the visually significant and attention-grabbing objects present in an image. The present work is about finding saliency detection methods using Multi-Stream Convolution Neural Network. The main aim of this is to train a CNN model which captures the contextual information and multiscale features. Different metrics like f-measure, recall, precision and MAE are used to know how our model is performing with respect to other models. We also used cross dataset evaluation to know how our model is performing with unknown data to know the generalization capabilities. We compared our results with other well-known methods such as IT, MZ and SR which proves the efficacy of our work.




As saliency detection is not a new area of research, therefore numerous methods have been proposed to find saliency detection. The present work is based upon cross dataset training of Convolution Neural Network (CNN). Cross-dataset involves the training of model on one dataset and testing on another dataset. The process is used to know the performance of the model on unknown dataset. The model which performs as expected on cross dataset are said to be more robust. Moreover, the model uses parallel multi-stream CNN networks. 



Our model is built using CNN Architecture with two independent parallel streams, such that both the streams take the same raw input image. Each stream consists of a convolutional layer with ReLU activation that learns local features and patterns, which is followed by a Max pooling layer that reduces the size of the feature map produced previously. The Output of both the streams are fused(concatenated) together to produce concatenated feature map in order to combine the features learned from both the streams. An additional Convolutional layer with sigmoid activation is added to produce final saliency map, where each pixel corresponds to its saliency score in the image.



![image](https://github.com/sai762/Mutli-stream-cnn-for-saliency-object-detection/assets/99879627/c2c2ff7e-1b45-41b6-9ad9-e142f5c69704)





Preprocessing: Prior to feeding the images into the model, a preprocessing step is performed. The input images are resized to a fixed dimension to ensure uniformity across the dataset. 
Loss Function and Optimization: Since our model predicts saliency score of all the pixels of an image in the form of saliency map, it uses Binary Cross entropy as the training loss function in order to figure out the disparity between the predicted saliency map and its corresponding ground truth saliency map. The SGD optimizer is employed to update the model's weights iteratively, aiming to minimize the loss function and improve model performance.


Training on DUT-OMRON Dataset: The proposed model is trained on the DUT-OMRON dataset, containing images and corresponding ground truth saliency maps. The training process involves 2 steps: forward and backward propagation to update the parameters of the model iteratively which is also known as hyper parameter tuning that learns the features to predict accurate saliency maps.
Cross-Dataset Evaluation: After completing the training process, the model is tested on two distinct datasets: ECSSD and DUTS. Here cross dataset evaluation, (means Training and testing is performed on two different datasets) is used to assess the model's ability to generalize across diverse datasets with varying image content and annotations. 
Saliency Maps: Following the training and evaluation phases, the model generates two distinct saliency maps: Grayscale representation that depicts the saliency score of each pixel in 0(black) to 255(white) range and Binary Saliency Map that distinguishes most salient elements in 0 to 1 range. Based on the contrast exhibited by objects against their backgrounds, adjusting the threshold is crucial to generate Binary Saliency Map. Optimal threshold calibration falls in the range of 0.15 to 0.30.



![image](https://github.com/sai762/Mutli-stream-cnn-for-saliency-object-detection/assets/99879627/145bd694-eb63-4fed-acfd-fc10f23f9083)




Evaluation Metrics: Several metrics such as accuracy, loss, F-Measure, Mean Absolute Error (MAE) and Precision-Recall curves. Are used to assess the performance of our model, these metrics offer a thorough Evaluation of the model's ability to correctly predict saliency maps on various datasets. 
Comparative Analysis: The performance of the suggested method is evaluated based on recent state-of-art methods. This comparative analysis enables a clearer understanding of the advantages and disadvantages of the CNN-based strategy in comparison to other approaches currently in use.






![image](https://github.com/sai762/Mutli-stream-cnn-for-saliency-object-detection/assets/99879627/404cf3a6-a0e3-4a60-b2ec-044a71b40530)



![image](https://github.com/sai762/Mutli-stream-cnn-for-saliency-object-detection/assets/99879627/402ec548-88f8-45d4-9847-2fc6dc526d93)
Results of saliency detection of various models: a. Original Image b. IT c. MZ d. SR e. OUR

![image](https://github.com/sai762/Mutli-stream-cnn-for-saliency-object-detection/assets/99879627/3ed443cc-64ba-43e4-a0f7-931b20a5f9e9)
Comparison of precision, recall and F-measure employed for various methods 


![image](https://github.com/sai762/Mutli-stream-cnn-for-saliency-object-detection/assets/99879627/9209c0d4-0fb1-4b0e-8605-5b7a11fa1ccf)
Comparison of mean absolute error (MAE) employed for various methods 

# Mutli-stream-cnn-for-saliency-object-detection


Saliency detection is finding the visually significant and attention-grabbing objects present in an image. The present work is about finding saliency detection methods using Multi-Stream Convolution Neural Network. The main aim of this is to train a CNN model which captures the contextual information and multiscale features. Different metrics like f-measure, recall, precision and MAE are used to know how our model is performing with respect to other models. We also used cross dataset evaluation to know how our model is performing with unknown data to know the generalization capabilities. We compared our results with other well-known methods such as IT, MZ and SR which proves the efficacy of our work.




As saliency detection is not a new area of research, therefore numerous methods have been proposed to find saliency detection. The present work is based upon cross dataset training of Convolution Neural Network (CNN). Cross-dataset involves the training of model on one dataset and testing on another dataset. The process is used to know the performance of the model on unknown dataset. The model which performs as expected on cross dataset are said to be more robust. Moreover, the model uses parallel multi-stream CNN networks. 



Our model is built using CNN Architecture with two independent parallel streams, such that both the streams take the same raw input image. Each stream consists of a convolutional layer with ReLU activation that learns local features and patterns, which is followed by a Max pooling layer that reduces the size of the feature map produced previously. The Output of both the streams are fused(concatenated) together to produce concatenated feature map in order to combine the features learned from both the streams. An additional Convolutional layer with sigmoid activation is added to produce final saliency map, where each pixel corresponds to its saliency score in the image.



![image](https://github.com/sai762/Mutli-stream-cnn-for-saliency-object-detection/assets/99879627/c2c2ff7e-1b45-41b6-9ad9-e142f5c69704)

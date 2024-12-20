<p align="justify">

Our code implements a **convolutional neural network (CNN)** for image classification, utilizing the fuctions available in the **TensorFlow and Keras libraries** for model development, training, and evaluation. The use of these libraries was choosen due to their ease of use and popularity. 

The dataset used has **10 classes** and can be found at the following link - https://www.kaggle.com/datasets/karimabdulnabi/fruit-classification10-class

It worth noting that in this particular run, the train and validation set provided from the dataset where merged in order to provide more flexibility when it comes to subdividing the data into training, validation and test set.  

The dataset is loaded using TensorFlow’s image_dataset_from_directory function, which **automatically labels the images based on their folder structure**. The data is batched for efficiency, and a few sample images along with their labels are visualized to confirm correct loading.

The images are **preprocessed by normalizing their pixel values to a range between 0 and 1**, ensuring that all features are on a consistent scale. Labels are converted to **one-hot encoded vectors**, suitable for multi-class classification. The dataset is then split into training (70%), validation (20%), and testing (10%) subsets.

The CNN model is constructed using a **sequential approach**. It comprises convolutional layers for feature extraction, pooling layers to reduce spatial dimensions, and dropout layers to prevent overfitting by randomly deactivating neurons during training. A flattening layer converts 2D feature maps into a 1D vector, followed by dense layers for classification. The final output layer uses a softmax activation function to produce probabilities for each of the ten classes.

The model is compiled with the **Adam optimizer** for adaptive learning rates, categorical crossentropy as the loss function for multi-class classification, and accuracy as the evaluation metric. **Early stopping** is implemented to halt training if validation loss does not improve for 10 consecutive epochs, preventing unnecessary computation and overfitting.

Training is carried out on the training set, with validation data used to monitor performance during each epoch. The script visualizes the training and validation loss and **accuracy curves** to analyze the training process and detect potential **overfitting or underfitting**.

After training, the model is evaluated on the test set to compute the final test loss and accuracy. Predictions are generated for the test set, and a classification report is displayed to summarize precision, recall, and F1-scores for each class. A confusion matrix is visualized to provide insights into class-wise performance and potential misclassifications.

**Main Points Covered:** 

**-CNN**

**-TensorFlow and Keras Libraries**

**-Multiclass**

**-Normalization**

**-One-Hot Encoding**

**-Layer Structure**

**-Adam Optimizer**

**-Accuracy Curves**

**-Overfitting**

**Main Problem Faced: Overfitting due to...**

The main reason behind overfitting behaviour was due to a unsuitable choice of the batch size, we noticed a substantial improvement after incresing the batch from 80 to 200. 
In addition, the inital model was way too complex. As a consequence, we reduced number of layers and its size. Overfitting can be clearly observed as validation and testing loss curves diverge.

![image](https://github.com/user-attachments/assets/55dc1359-ee1c-4b7b-a744-9a5207fc0b3c)

**Final Results:**

![image](https://github.com/user-attachments/assets/0217b5a0-558f-407c-80fd-4a3a926efa75)

![image](https://github.com/user-attachments/assets/25b9ddc1-fdf4-41a1-8c27-72a50357a7bb)

![image](https://github.com/user-attachments/assets/5f5f9176-da64-41e1-8de7-fe56db9b3645)

The neural network demonstrates strong performance in the fruit classification task, with increasing training and validation accuracy and consistently decreasing loss curves. This indicates effective learning and good generalization. **The close alignment of training and validation metrics suggests minimal overfitting.** Additionally, the confusion matrix shows accurate predictions across all classes, with only  1 minor misclassification, confirming balanced and reliable model performance.

The whole code can be found at the following link - https://colab.research.google.com/drive/1V-eoDVVDDqmeveHjQuz0WtJiPrq1PaT5#scrollTo=6Bo2zeNkXz4K


 </p>





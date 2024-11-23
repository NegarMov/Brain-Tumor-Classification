<h1 align="center">Brain Tumor Classification</h1>

This project focuses on classifying brain tumors using a CNN model. The goal is to develop a fast and robust model capable of accurately identifying brain tumors from MRI images. For this purpose, ShuffleNet V2 (x0.5) is fine-tuned on the [Brain Tumor MRI Dataset](https://www.kaggle.com/datasets/masoudnickparvar/brain-tumor-mri-dataset) from Kaggle.

## Dataset
As mentioned before, the [Brain Tumor MRI Dataset](https://www.kaggle.com/datasets/masoudnickparvar/brain-tumor-mri-dataset) is utilized in this project. This dataset itself is a combination of the 'figshare', 'SARTAJ', and 'Br35H' datasets and contains brain MRI images in the following four categories:
  * Glioma Tumor
  * Meningioma Tumor
  * Pituitary Tumor
  * No Tumor

## Model Architecture
The architecture used for this project is ShuffleNet V2 (x0.5), followed by two fully connected layers. The first three blocks of the model are frozen, and the rest are trained. It is noteworthy that ShuffleNet is used due to its high efficiency, lightweight nature, and performance.

## Model Training
To enhance the model's performance and generalizability, a random horizontal flip and rotation (up to 5 degrees) are applied to augment the training data. Various regularization techniques, such as dropout and weight decay, are adopted to prevent overfitting. Additionally, classes are balanced by weighting the loss function, ensuring that the model performs well across all categories.

Moreover, 10-fold Cross-Validation is employed to assess the model's performance. Ultimately, the final model is chosen based on its performance on the validation set (minimum loss). This model is used to assess the final performance of the model on the test dataset.


## Performance Metrics
The model's performance is evaluated using accuracy metrics across different datasets:
  * Average Accuracy on Training Dataset: **98.77%**
  * Average Accuracy on Validation Dataset: **97.83%**
  * Accuracy on Test Dataset: **98.93%**

Also, the confusion matrix of the outputs of the model on the test dataset can be seen below:
<p align="center">
  <img src="https://github.com/NegarMov/Brain-Tumor-Classification/blob/main/confusion_matrix.png" alt="Confusion Matrix" width="500"/>
</p>

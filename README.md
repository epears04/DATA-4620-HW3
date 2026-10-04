# Homework 3: Facial Keypoints

## Instructions
1. **Inspect the data** Print out the shape, dtype, min, and max of the arrays and explain them in your report. Show some of the images and plot the keypoint locations on top of the images. Note: You can use np.nanmin() and np.nanmax() to compute the min and max while ignoring the missing values.
1. **Preprocess and split the data.** Preprocess the data by dividing the images by 255 and the keypoints by 96. Prepare a 90/10 train/test split.
1. **Prepare Dataset and DataLoader objects.** You can use ```TensorDataset``` as in HW1.
1. **Create a CNN.** The design of the CNN is up to you. You are welcome to use the “VGG-style” pattern shown in class (several blocks of conv-conv-pool, ending with flatten and finally a linear transformation or MLP). The input should be an image, and the output should be the 30 keypoint values.
1. **Train the model.** Train your CNN on the data. You will want to use the provided loss function ```masked_mae_loss``` to properly handle the NaN values. Make sure to use checkpointing to keep the model with best test error.
1. **Analyze the results.** Show some test images and predicted keypoints versus ground truth. Diagnose your initial results in terms of bias and variance, overfitting and underfitting. Be sure to report error metrics in pixel units (multiply by the keypoint labels and predictions by 96).
1. **Improve the model.** Now try at least two different modifications to improve your model. For example, you could add residual connections and/or batch normalization and try data augmentation (see [this page](https://albumentations.ai/docs/3-basic-usage/keypoint-augmentations/)). Keep in mind that any geometric augmentations (like crop, rotate, scale) need to act on both the images and the keypoints – Albumentations that has that functionality built-in.

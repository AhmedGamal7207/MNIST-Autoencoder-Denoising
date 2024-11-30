# MNIST Autoencoder Denoising

This project demonstrates the use of a Convolutional Neural Network (CNN) in an autoencoder architecture to remove Gaussian noise from images in the MNIST dataset. The model learns to map noisy images to their clean counterparts, helping to restore clarity in image-based applications. The autoencoder is trained on the noisy images and evaluated using both the noisy and original datasets.

## Features

- **MNIST Dataset**: Uses the popular MNIST dataset of handwritten digits.
- **Noise Addition**: Gaussian noise is added to images to simulate real-world imperfections.
- **Autoencoder Model**: Consists of an encoder-decoder network to reconstruct denoised images.
- **Model Evaluation**: The model’s performance is evaluated by comparing denoised images with the original images.

## How It Works

1. **Data Loading and Preprocessing**:  
   - The MNIST dataset is loaded and normalized for model compatibility.
   - Gaussian noise is added to the images to simulate noise.

2. **Autoencoder Model**:  
   - **Encoder**: Extracts features from the noisy images.
   - **Decoder**: Reconstructs the clean version of the images.
   - **Loss Function**: Binary cross-entropy is used to minimize the difference between the reconstructed and original images.

3. **Training**:  
   - The model is trained for 5 epochs with a batch size of 256.

4. **Testing and Visualization**:  
   - The model’s ability to denoise images is tested on a separate test set.
   - The results are visualized by comparing noisy, denoised, and original images.

## Model Architecture

The autoencoder model consists of the following layers:

- **Encoder**:
  - Conv2D layer with 32 filters, kernel size 3, ReLU activation, and padding='same'.
  - MaxPooling2D layer with pool size 2 and padding='same'.
  - Conv2D layer with 16 filters, kernel size 3, ReLU activation, and padding='same'.
  - MaxPooling2D layer with pool size 2 and padding='same'.
  
- **Decoder**:
  - Conv2D layer with 16 filters, kernel size 3, ReLU activation, and padding='same'.
  - UpSampling2D layer with size 2.
  - Conv2D layer with 32 filters, kernel size 3, ReLU activation, and padding='same'.
  - UpSampling2D layer with size 2.
  
- **Output Layer**:
  - Conv2D layer with 1 filter, kernel size 3, Sigmoid activation, and padding='same'.

## Results

After training, the model was tested on a separate test set. The results show that the model effectively removes noise, as visualized by comparing noisy images with denoised and original images. The model successfully learned to restore clarity, making digit recognition easier.

## Conclusion

The project demonstrates the use of autoencoders for image denoising. It highlights how CNN-based autoencoders can be trained to clean noisy images, improving clarity and restoring details. The trained model could be adapted for other image denoising tasks, proving useful in various computer vision applications.

# Dynamic-Apparel-Design-System-with-AI-and-Style-Transfer
# Neural Style Transfer

## Introduction
Neural Style Transfer (NST) is a deep learning technique that applies the artistic style of one image to another while preserving the original image's structure. This project implements NST using a **pretrained VGG19 model** to blend content and style images effectively.

## Dataset Information
The dataset consists of two main image inputs:
- **Content Image**: The base image that retains its structure.
- **Style Image**: The reference image whose artistic style is applied to the content image.

These images are loaded and preprocessed using a custom `ImageLoader` utility to ensure compatibility with the model.

## Preprocessing Steps
1. **Load Images**: The content and style images are read and resized to the required dimensions.
2. **Normalization**: Convert the image pixel values to a range suitable for the VGG19 model.
3. **Transformation**: Convert images to tensors and apply necessary transformations like scaling and cropping.
4. **Batching**: Ensure the images are in the correct format for model inference.

## Model Used
- **VGG19 Pretrained Model**: 
  - The feature extraction layers of VGG19 are used to compute the content and style representations of the images.
  - Content is extracted from **conv4**.
  - Style is extracted from **conv1, conv2, conv3, conv4, and conv5**.

## Workflow
1. **Import Required Libraries** (Torch, torchvision, PIL, Matplotlib, and custom modules).
2. **Load the Pretrained VGG19 Model** for feature extraction.
3. **Define Content and Style Layers**.
4. **Load and Display Input Images**.
5. **Compile and Train the Model** to minimize content and style losses.
6. **Generate and Display the Output Image**.

## Model Evaluation
- **Content Loss**: Measures the difference between the generated image and the original content image.
- **Style Loss**: Evaluates how well the generated image captures the texture and patterns of the style image.
- **Total Loss**: A weighted sum of content and style loss to balance the trade-off.
- **Comparison Metrics**: The generated image is visually compared with the original content and style images to assess quality.

## Results
- The model successfully transfers the style of the reference image to the content image.
- The generated image retains the structure of the content image while adopting the artistic features of the style image.
- The effectiveness of style transfer is influenced by hyperparameters such as content weight, style weight, and optimization steps.

## Conclusion
This project demonstrates how deep learning can be leveraged for artistic image generation using Neural Style Transfer. By utilizing a pretrained VGG19 model, we can achieve high-quality style transfer while preserving key structural details. Future improvements can include optimizing performance and experimenting with different loss functions for better stylization.


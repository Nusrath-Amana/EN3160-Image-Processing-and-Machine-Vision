# EN3160 - Image Processing and Machine Vision

## Overview

This repository contains the implementations for the assignments of the EN3160 course on Image Processing and Machine Vision. The assignments involve various tasks related to intensity transformations, filtering, image enhancement, object detection, and more. The following sections outline the details and steps involved in each assignment.

## Assignment 1: Intensity Transformations and Neighborhood Filtering

### Tasks:
1. **Intensity Transformation**:
   - Maps pixel values between 50 and 150 grayscale values to higher pixel values, resulting in a lighter processed image compared to the original.
   
2. **Accentuating White Matter & Gray Matter in the Brain Proton Density Image**:
   - **White matter**: Maps near white pixel values (187 to 255) to 255 (white).
   - **Gray matter**: Maps pixel values (140 to 187) to 255 (white).
   
3. **Gamma Correction**:
   - Applies a gamma correction with a value of 0.7 to enhance visibility in dark regions by widening the range of dark pixels.

4. **Increasing Vibrance**:
   - Enhances the mid-range color intensities in the image using a vibrance enhancement function (`a = 0.5`).

5. **Histogram Equalization**:
   - Equalizes the image histogram by calculating the cumulative distribution function (CDF) and mapping it to the range (0, 255).

6. **Histogram Equalization on Foreground**:
   - Applies histogram equalization only to the foreground of the image.

7. **Sobel Operator for Gradient Calculation**:
   - Computes gradients using the Sobel operator with `filter2D`, custom functions, and convolution methods.

8. **Image Zooming**:
   - Implements zooming using Nearest Neighbor and Bilinear Interpolation, with a comparison of the results and the sum of squared differences.

9. **Blurring Background**:
   - Applies blurring (averaging) to the background while keeping the foreground intact.

---

## Assignment 2: Image Detection and Feature Matching

### Task 1: Blob Detection Using Laplacian of Gaussian (LoG)
- **Objective**: Detect blobs of varying sizes in an image using LoG at different scales.
  - **Sigma Range**: (1, 30) with 10 sigma values.
  - **Threshold**: Filters weak blob responses.
  - **Max Response Calculation**: At radius \( r = \sqrt{2} \sigma \).
  - **Center of Largest Circle**: (359.0, 283.0) with radius 33.31.

### Task 2: RANSAC Algorithm for Line and Circle Detection
- **Steps**:
  1. Randomly select points (2 for line, 4 for circle).
  2. Fit a model to the subset and find the parameters.
  3. Find inliers by calculating the error (normal distance for line, radial error for circle).
  4. Iterate for 10,000 times to select the best model with the most inliers.
  - The line model is fitted first, followed by the circle model.

### Task 3: Image Warping Using Homography
- **Objective**: Perform homography between two images, wrapping and blending them together.
  - **Source Image**: Eiffel Tower.
  - **Destination Image**: A book with a black cover.
  - This technique can be used to make creative images by blending a source image onto a destination image.

### Task 4: Feature Matching with SIFT
- **Objective**: Detect keypoints and compute descriptors using the SIFT algorithm.
  - Use `knnMatch` with k = 2 for feature matching.
  - Apply ratio test (ratio = 0.75) to filter out good matches.
  - Use homography calculation between successive image pairs for accurate stitching.

---

## Dependencies

- Python 3.x
- OpenCV
- NumPy
- Matplotlib

---

## How to Run the Code

1. Clone this repository to your local machine:

   ```bash
   git clone https://github.com/Nusrath-Amana/EN3160-Image-Processing-and-Machine-Vision.git

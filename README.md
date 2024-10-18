# Image Region Labelling

## Scene Segmentation and Interpretation

**Instructor**: Olivier Laligant  
**Author**: Mayank Kumar GUPTA

### Objective

The objective of this project is to develop an image processing algorithm for region labeling in a binary image. The algorithm aims to accurately label regions within the binary image, separating objects from the background. Additionally, the algorithm refines the labeling process to handle multiple labels for the same region and merges them to define a single region.

---

### Image Preprocessing

The initial step is to convert the color image into a grayscale image, and then into a binary image. A threshold value of 130 is applied, where pixel values above this threshold are set to 1 (representing objects) and those below are set to 0 (representing the background).

- **Original Image**  
<p align="center">
  <img src="https://raw.githubusercontent.com/Mayankgbrc/Image-Region-Labelling/refs/heads/main/images/0.png" align="center" height="400px" alt="Original Image" />
 </p>

- **Grayscale Image**  
<p align="center">
  <img src="https://raw.githubusercontent.com/Mayankgbrc/Image-Region-Labelling/refs/heads/main/images/1.png" align="center" height="400px" alt="Grayscale Image" />
 </p>

- **Binary Image**  
<p align="center">
  <img src="https://raw.githubusercontent.com/Mayankgbrc/Image-Region-Labelling/refs/heads/main/images/2.png" align="center" height="400px" alt="Binary Image" />
 </p>
---

### Region Labeling Algorithm

The algorithm iterates over each pixel in the binary image, and upon encountering a pixel with a value of 1, it assigns a new label. It checks neighboring pixels of each labeled pixel to determine connectivity, using a recursive method that stores visited pixel indices in a list.

#### Refinement for Noise Reduction
A refinement step eliminates noise by resetting labels with fewer than a threshold number of pixels to 0.

- **Processed Image after Refinement**  
<p align="center">
  <img src="https://raw.githubusercontent.com/Mayankgbrc/Image-Region-Labelling/refs/heads/main/images/3.png" align="center" height="400px" alt="Processed Image" />
 </p>

---

### Calculating Image Moments

Image moments are utilized to derive essential parameters like the center of each labeled region (mean_x, mean_y) and the orientation (theta). These values are crucial for analyzing and characterizing the labeled regions.

- **Labeled Image**  
 <p align="center">
  <img src="https://raw.githubusercontent.com/Mayankgbrc/Image-Region-Labelling/refs/heads/main/images/4.png" align="center" height="400px" alt="Labeled Image" />
 </p>

---

### Orientation and Dimensions

Below are the orientation and dimensions of each object, computed through analysis:

| Object | Theta (degrees) | Length (px) | Width (px) |
|--------|-----------------|-------------|------------|
| 01     | -39.49           | 118         | 64         |
| 02     | 46.92            | 111         | 73         |
| 03     | -86.76           | 113         | 73         |
| 04     | 79.36            | 112         | 69         |
| 05     | -75.09           | 112         | 65         |
| 06     | -75.78           | 115         | 60         |
| 07     | 50.89            | 112         | 66         |
| 08     | 46.34            | 115         | 64         |
| 09     | -58.61           | 110         | 62         |
| 10     | 14.01            | 108         | 58         |
| 11     | -14.87           | 105         | 62         |
| 12     | 28.76            | 113         | 67         |
| 13     | -83.97           | 112         | 64         |
| 14     | 30.50            | 120         | 62         |
| 15     | 79.33            | 115         | 71         |

#### Mean and Standard Deviation
- **Length Mean**: 112.73 px  
- **Width Mean**: 65.33 px  
- **Length Std**: 3.56 px  
- **Width Std**: 4.37 px

**Labeled Image**  
 <p align="center">
  <img src="https://raw.githubusercontent.com/Mayankgbrc/Image-Region-Labelling/refs/heads/main/images/5.png" align="center" height="400px" alt="Final Labeled Image" />
 </p>

---

### Summary

This report demonstrates the use of pixel connectivity for region labeling in images. The approach effectively labels regions across binary, grayscale, and color images, making it useful for object recognition and segmentation. However, further algorithm improvements are needed to enhance region detection in noisy environments.

---

# AUTOMATED-VISUAL-INSPECTION-SYSTEM-FOR-INDUSTRIAL-QUALITY-CONTROL
A computer vision algorithm to automate quality control of plastic caps for industries, by utilizing Hough Transforms, Canny and Sobel edge detection and gradient thresholding to detect and localize and classify manufacturing defects in the caps.

The algorithm classifies caps into three categories:
*   **GOOD:** Cap is intact with a complete liner.
*   **DEFECTIVE (Missing Liner):** The liner is entirely absent.
*   **DEFECTIVE (Incomplete Liner):** The liner is present but cut or damaged.

## Features & Methodology
The inspection pipeline utilizes several image processing techniques:
*   **Cap Localization:** Uses Gaussian blurring, Canny Edge Detection, and the Hough Circle Transform to find the cap's center and radius.
*   **Missing Liner Detection:** Creates a circular mask and calculates the average pixel intensity to determine if the dark liner is present against the lighter cap background.
*   **Incomplete Liner Detection:** Uses Sobel operators to calculate image gradients, isolates the inner liner area, and applies the Probabilistic Hough Line Transform (`HoughLinesP`) to identify the straight cuts characteristic of a damaged liner.

## Prerequisites
To run this script, you will need Python installed along with the following libraries:
*   `opencv-python` (cv2)
*   `numpy`
*   `matplotlib`

You can install the dependencies via pip:
```bash
pip install opencv-python numpy matplotlib

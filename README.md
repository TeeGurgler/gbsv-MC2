This project explores how tropical weather conditions (like haze and clouds) affect classical computer vision algorithms when extracting coastlines from satellite images. I am using a NASA MODIS satellite image of Hispaniola (Dominican Republic and Haiti) as the baseline.

## Project Structure

The project is split into three sequential notebooks:

* **`2.1 - Image Augmentation.ipynb`**
  Simulates tropical atmospheric degradations (light and heavy haze) using a combination of Gaussian blur and contrast reduction. It uses exactly one metric—Sharpness (Variance of the Laplacian)—to measure the loss of edge detail.

* **`2.2 - Pattern Detection.ipynb`**
  Implements a classical Canny edge detector step-by-step from scratch (Gaussian smoothing, Sobel gradients, non-maximum suppression, and queue-based hysteresis tracking). It evaluates how well the coastline can be detected under hazy conditions using the Edge Density % metric.

* **`2.3 - Image Segmentation & Morphological Operators.ipynb`**
  Segments the landmass from the ocean using a Green-minus-Blue channel difference and Otsu's thresholding. It uses a sharpness-adaptive cloud mask (HSV + RGB checks) to clean up clouds, extracts the island's central skeleton, and measures segmentation accuracy using the Intersection over Union (IoU) metric.

---

## Setup & Requirements

To run these notebooks, you will need Python 3 and the following libraries installed:

```bash
pip install opencv-python numpy matplotlib pandas
```

Simply open the notebooks in Jupyter Lab or Jupyter Notebook and run the cells from top to bottom. All notebooks are already pre-run with the plots and tables saved inside.


# Book Detection on Shelf (SIFT + FLANN + RANSAC)

This repository contains an implementation of a **classical computer vision pipeline** for detecting books on shelves using local feature matching.
It leverages **SIFT descriptors**, **FLANN-based matching**, and **RANSAC-based homography estimation** to identify and localize books.

The system is capable of detecting **multiple instances** of each book within a scene.

---

## Project Structure

```
book-detection/
│
├── Book Detection.ipynb              # Main Jupyter Notebook
└── README.md
```

---

## Techniques Used

* **SIFT (Scale-Invariant Feature Transform)** for feature extraction
* **FLANN (Fast Library for Approximate Nearest Neighbors)** for efficient descriptor matching
* **Lowe's ratio test** for filtering ambiguous matches
* **RANSAC (Random Sample Consensus)** for robust homography estimation
* **Bounding box transformation** for visualizing detected books

---

## Dataset

* **Model images**: Grayscale images of individual book covers
* **Scene images**: Grayscale images of bookshelves containing multiple books


---

## Detection Pipeline

1. Extract SIFT keypoints and descriptors for both model and scene images.
2. Perform descriptor matching with FLANN.
3. Apply Lowe’s ratio test to retain good matches.
4. Use RANSAC to estimate homography between model and scene.
5. Project book corners into the scene and draw bounding boxes.
6. Prevent duplicate detections by excluding reused keypoints.

---

## How to Run

1. Open the notebook in **Google Colab** or locally with Jupyter.
2. Make sure dependencies are installed:

```bash
pip install opencv-python numpy matplotlib
```

3. Run all cells from top to bottom.
4. The detections will be visualized on scene images with bounding boxes.

---

## Future Work

* Extend to deep-learning-based detection (e.g., YOLO, Faster R-CNN) for larger-scale datasets
* Improve duplicate suppression with non-maximum suppression (NMS)
* Benchmark against modern object detection models

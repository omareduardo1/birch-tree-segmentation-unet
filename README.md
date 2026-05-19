# Birch Tree Semantic Segmentation in Aerial Imagery 🌲🚁

This repository contains the code and the final research report for the **Neurocomputing** university project. The objective of this work is to apply binary semantic segmentation to aerial forest imagery to identify birch trees, supporting emergency landing site assessments for aviation.

📄 **[Read the full Project Report (PDF)](./Project_Report.pdf)**

## 🧠 Project Overview
Reliably identifying tree-covered regions versus potentially open terrain is safety-critical for emergency landings. This project systematically evaluates different Convolutional Neural Network (CNN) architectures to perform pixel-level classification of aerial images, distinguishing birch trees (obstacles) from the background.

We iteratively developed and tested two main versions of our pipeline:
* **Version 1 (Exploratory):** Baseline U-Net testing, data augmentation, specialized loss functions (F1/Dice), and Transfer Learning (VGG16-UNet).
* **Version 2 (Optimized):** Refined architecture with dynamic Learning Rate schedulers (`ReduceLROnPlateau`) and optimized augmentations to prevent boundary instability.

## ⚙️ Tech Stack & Methods
* **Language:** Python
* **Frameworks:** TensorFlow / Keras
* **Data Handling:** `h5py` (Dataset provided in HDF5 format)
* **Architectures Evaluated:** * Custom Baseline U-Net
  * U-Net with BCE + Dice Loss
  * VGG16-UNet (Frozen and Fine-Tuned Encoder)

## 📊 Key Results
The highest performing model was our **Optimized 64-filter Custom U-Net** trained with a combined BCE and Dice loss and dynamic learning rate scheduling.

| Metric | Score (Test Split) |
| :--- | :--- |
| **Intersection over Union (IoU)** | `0.9380` |
| **Dice Coefficient** | `0.9650` |

*Note: Transfer learning with a VGG16 encoder underperformed compared to our custom end-to-end task-specific architecture on this specific aerial dataset.*

## 📂 Repository Structure
* `notebooks/` - Contains the Jupyter Notebooks with the model architectures and training loops.
* `Project_Report.pdf` - The detailed academic paper discussing our methodology, ablation studies, and qualitative/quantitative analyses.

## 👥 Authors
* **Omar Eduardo Borges Montero**
* **Gabriele Franco**

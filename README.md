# Automatic Classification of Works of Art

---

## 📜 Project Overview

This project focuses on the **automatic classification of artworks** using state-of-the-art deep learning and clustering techniques. The goal is to classify paintings into their respective artistic styles and visualize the relationships between these styles in a meaningful way. The project leverages **ResNet** and **DenseNet** architectures for feature extraction, **t-SNE** and **UMAP** for dimensionality reduction, and **Gaussian Mixture Models (GMM)** for clustering.

The dataset consists of **3,060 paintings** from **100 artists**, spanning a wide range of artistic movements from the 1400s to the present day. The project aims to provide insights into the stylistic relationships between artworks and assist art historians, curators, and enthusiasts in understanding art history.

Here is a clustering we obtained :
![Screenshot from 2025-02-27 14-53-03](https://github.com/user-attachments/assets/6dc40b78-518e-4521-93e2-95a087c96614)

With "Hollow in the snow" as an input, the model was able to give us similar paintings, that belonged to the same art movement (Impressionism) :
![Screenshot from 2025-02-27 14-53-20](https://github.com/user-attachments/assets/6eb8b6f8-b35f-42fc-9ef5-123301c140cf)


---

## 🛠️ Methodology

### 1. Dataset
- **3,060 paintings** from **100 artists**.
- Covers a wide range of artistic movements (Renaissance, Baroque, Impressionism, etc.).
- Imbalanced distribution of paintings per artist.

### 2. Model Architecture
- **ResNet-18** and **DenseNet-121** pre-trained on ImageNet.
- Fine-tuned for feature extraction and classification.
- Custom fully connected layers for painter classification.

### 3. Feature Extraction
- High-level features extracted from the penultimate layer of ResNet and DenseNet.
- Manual feature extraction (color, edges) was explored but outperformed by deep learning.

### 4. Dimensionality Reduction
- **t-SNE** and **UMAP** used to project features into 2D space.
- t-SNE performed better for visualizing local structures in the dataset.

### 5. Clustering
- **Gaussian Mixture Models (GMM)** used to cluster paintings by artistic style.
- Birthdate of artists incorporated as an additional feature to improve clustering.

---

## 📊 Results

### Key Findings
- **t-SNE** outperformed **UMAP** in visualizing artistic styles.
- **ResNet** provided better feature extraction compared to DenseNet.
- Incorporating **birthdate** as a feature significantly improved clustering accuracy.
- Clusters aligned well with known artistic movements (e.g., Impressionism, Baroque).

### Visualizations
- **2D Maps**: Visual representations of artistic styles and their relationships.
- **Clustering**: Paintings grouped by style, with clear timelines tracing artistic movements.

---

## 🚀 How to Use This Repository

Note that the database is not available, but all the paintings can be downloaded from https://www.wikiart.org/
You can open the xlsx file to see all the paintings I used, grouped by artist.

### 1. Clone the Repository
```bash
git clone https://github.com/HugoCrochet/automatic-art-classification.git
cd automatic-art-classification
```

### 2. Install Dependencies
```bash
pip install -r requirements.txt
```

### 3. Repository Structure 📂
```bash
automatic-art-classification/
├── data/                    # Dataset (not available on git)
├── paintings.xslx           # all the paintings grouped by artists
├── notebook.ipynb           # main notebook
├── feature_extraction.ipynb # notebook with manual features extraction
├── requirements.txt         # Python dependencies
├── report.pdf               # Project report (PDF)
├── taxonomy.pdf             # All the considered painters and their styles (PDF)
└── README.md                # This file
```

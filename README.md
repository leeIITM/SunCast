# Solar Flare Prediction using Graph Attention Networks (GAT) and LSTM

A deep learning framework for **multi-class solar flare prediction** that combines **Graph Attention Networks (GAT)** for spatial feature learning with **Long Short-Term Memory (LSTM)** networks for temporal sequence modeling.

The model captures both the spatial relationships among solar active region features and their temporal evolution, leading to robust flare prediction performance across multiple random seeds.

---

## Overview

Solar flares are sudden releases of magnetic energy from the Sun that can disrupt satellites, GPS systems, radio communication, and power grids.

This project proposes a hybrid **Graph Attention Network + LSTM** architecture that models:

- Spatial correlations between solar features using Graph Attention Networks
- Temporal evolution using LSTM
- Multi-class solar flare prediction

The notebook contains the complete pipeline from preprocessing to evaluation and visualization.

---

## Features

- Graph-based representation of solar active regions
- Graph Attention Network (GAT) encoder
- LSTM temporal modeling
- Multi-class flare classification
- Training across multiple random seeds
- Precision, Recall and F1-score evaluation
- Performance visualization
- Heatmap-based metric comparison

---

## Project Structure

```
.
├── GAT + LSTM.ipynb          # Complete notebook
├── checkpoint.pth            # Saved model checkpoint
├── README.md
└── plots/
    ├── accuracy.png
    ├── metrics.png
    └── heatmap.png
```

---

## Methodology

### 1. Data Preprocessing

The dataset is first cleaned and transformed into a graph-based representation.

The preprocessing pipeline includes:

- Data loading
- Feature normalization
- Label encoding
- Graph construction
- Train/Test split

---

### 2. Graph Construction

Each sample is represented as a graph where:

- Nodes correspond to feature representations.
- Edges capture relationships between features.
- Graph statistics are analyzed before training.

Observed graph statistics:

| Statistic | Value |
|-----------|-------|
| Mean Degree | **12.4** |
| Variance | **2.48** |
| Standard Deviation | **1.57** |

---

### 3. Model Architecture

The proposed model consists of two stages.

#### Graph Attention Network (GAT)

The GAT learns spatial dependencies by assigning attention weights to neighboring nodes.

It enables the network to focus on the most informative relationships instead of treating all neighbors equally.

---

#### LSTM Network

The embeddings produced by the GAT are passed to an LSTM that captures temporal dependencies across observations.

The LSTM output is finally fed to a fully connected classifier.

Pipeline:

```
Input Features
      │
      ▼
Graph Construction
      │
      ▼
Graph Attention Network
      │
      ▼
Graph Embeddings
      │
      ▼
LSTM
      │
      ▼
Fully Connected Layer
      │
      ▼
Multi-class Prediction
```

---

## Training

The model is trained over multiple random seeds to evaluate robustness and stability.

Training includes:

- Checkpoint saving/loading
- Loss monitoring
- Best validation accuracy tracking
- Mean and standard deviation computation

---

## Experimental Results

### Overall Performance

| Metric | Value |
|--------|-------:|
| Mean Accuracy | **87.58%** |
| Standard Deviation | **4.52%** |
| Final Result | **87.58 ± 4.52 %** |

---

### Class-wise Performance

| Class | Precision | Recall | F1-score |
|------:|----------:|-------:|---------:|
| 0 | **0.961** | **0.981** | **0.970** |
| 1 | **0.848** | **0.896** | **0.871** |
| 2 | **0.820** | **0.761** | **0.788** |
| 3 | **0.868** | **0.865** | **0.866** |

---

## Visualizations

The notebook generates several visualizations to analyze model performance.

### Included plots

- Model accuracy comparison
- Precision / Recall / F1 comparison
- Heatmap of mean and standard deviation
- Training statistics

Add the extracted figures inside a `plots/` folder and reference them as:

```markdown
## Accuracy

![Accuracy](plots/accuracy.png)

## Performance Metrics

![Metrics](plots/metrics.png)

## Heatmap

![Heatmap](plots/heatmap.png)
```

---

## Technologies Used

- Python
- PyTorch
- PyTorch Geometric
- NumPy
- Pandas
- Scikit-learn
- Matplotlib
- NetworkX

---

## How to Run

Clone the repository

```bash
git clone <repository_url>
cd repository
```

Install dependencies

```bash
pip install -r requirements.txt
```

Run the notebook

```bash
jupyter notebook "GAT + LSTM.ipynb"
```

---

## Results Summary

- Hybrid GAT-LSTM architecture successfully captures both spatial and temporal information.
- Stable performance across multiple random seeds.
- High F1-score for all classes.
- Achieved an average classification accuracy of **87.58%**.

---

## Future Improvements

- Graph Transformers
- Dynamic graph construction
- Self-supervised pretraining
- Attention visualization
- Larger benchmark datasets
- Explainable AI (XAI) for solar flare prediction

---

## Citation

If you use this work in your research, please cite the corresponding publication once available.

---

## Author

**Kutraleeswaran N H**

Department of Aerospace Engineering & IDDD Robotics  
Indian Institute of Technology Madras

# AI Drone Landing Zone Evaluation System

Group Member IDNos.
Anurag Padhy(Leader) - 2023A3PS0301H
Khushal Vardhan Neeli - 2023B4A40680H
Harshit Verma - 2022A3PS0510H

## Project Overview

This project implements an Artificial Intelligence system for autonomous drone package delivery landing zone selection using:

- Semantic Segmentation
- Monocular Depth Estimation (MiDaS)
- Knowledge Graph Semantic Reasoning
- Geometric Safe-Zone Search
- Cost Function Optimization

The system identifies the safest and closest landing region relative to a user-specified target coordinate.

---

# Features

- 4 Encoder + 4 Decoder CNN architecture
- Semantic segmentation on TU Graz Semantic Drone Dataset
- Intel MiDaS depth estimation
- Binary safe-zone generation
- Rotational candidate search
- Knowledge-graph-based semantic reasoning
- Weighted cost optimization
- GPU acceleration using CUDA

---

*** Include dataset (semantic_drone_dataset/) in main folder if you want to train model.

## Folder Structure

```text
CSF407_2026_2023A3PS0301H_Assignment-II/
│
├── src/
│   ├── config.py
│   ├── dataset.py
│   ├── geometry.py
│   ├── knowledge_graph.py
│   ├── main.py
│   ├── model.py
│   ├── semantic_brain.py
│   ├── train.py
│   ├── utils.py
│   ├── split_data.py
│   ├── best_model.pth
│   ├── mission_config.json
│   ├── clean_dataset/
│   └── test_images/
│
├── semantic_drone_dataset/
├── requirements.txt
├── config.yml
└── README.md
```

# Installation

Install all dependencies:

```bash
pip install -r requirements.txt

---
# Important Execution Note

All commands must be executed from inside the `src/` directory.

Example:

```bash
cd src
python train.py
```

This is required because dataset and configuration paths are defined relative to the `src/` folder.

# Dataset Preparation

Run:

```bash
python split_data.py
```

This creates:

- clean_dataset/train
- clean_dataset/val

---

# ANN Training

Run:

```bash
python train.py
```

The best model checkpoint will automatically be saved as:

```
best_model.pth
```

---

# Running the Full AI Pipeline

Run:

```bash
python main.py test_images/sample.jpg 400 300
```

Where:
- 400 = target X coordinate
- 300 = target Y coordinate

---

# Expected Outputs

The system generates:

## output.jpg
- Final landing placement visualization
- Green optimal bounding box
- Target coordinate marker

## output_analysis.jpg
6-panel dashboard:
1. Original Image
2. Semantic Segmentation
3. Depth Map
4. Safe Mask
5. Best Placement
6. Cost Breakdown

---

# Technologies Used

- Python
- PyTorch
- OpenCV
- MiDaS
- CUDA
- NumPy
- Matplotlib

---

BITS Pilani Hyderabad Campus  
CS F407 Artificial Intelligence  
Project Assignment-II

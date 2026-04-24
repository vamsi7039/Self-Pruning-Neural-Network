# Self-Pruning Neural Network

## Overview
This project implements a self-pruning neural network that dynamically removes less important weights during training using a learnable gating mechanism.

Instead of pruning after training, the model learns which connections to remove during training itself.

---

## Key Idea
Each weight in the network is associated with a learnable gate parameter.  
The gate controls whether a weight contributes to the output.

Pruned Weight = Weight × Sigmoid(Gate Score)

---

## Methodology
- Custom PrunableLinear layer
- Learnable gate parameters
- Sigmoid activation to control gates
- L1 regularization to enforce sparsity
- Training on CIFAR-10 dataset
- Evaluation using accuracy and sparsity

---

## Results

| Lambda | Accuracy (%) | Sparsity (%) |
|--------|-------------|--------------|
| 0.001  | 47.19       | 59.75        |
| 0.05   | 44.73       | 81.14        |
| 0.5    | 41.75       | 89.10        |

---

## Key Observations
- Increasing lambda increases sparsity
- Higher sparsity reduces accuracy
- Model successfully learns to prune itself during training

---

## Gate Distribution
The distribution shows a strong spike near zero, indicating that most connections are pruned, while a smaller group of connections remains active.
![alt text](image.png)
---

## Tech Stack
- Python
- PyTorch
- Torchvision
- Matplotlib

---

## How to Run

1. Open the notebook in Google Colab or Jupyter
2. Run all cells

OR

```bash
pip install -r requirements.txt

```md
# Self-Pruning Neural Network Report

## 1. Introduction
This project focuses on building a neural network that can prune itself during training by learning which connections are unnecessary.

---

## 2. Why L1 Regularization Encourages Sparsity
L1 regularization penalizes the sum of gate values. Since gate values are positive after applying the sigmoid function, minimizing this loss forces many gates toward zero.

As a result, the corresponding weights become inactive, leading to a sparse network.

---

## 3. Results

| Lambda | Accuracy (%) | Sparsity (%) |
|--------|-------------|--------------|
| 0.001  | 47.19       | 59.75        |
| 0.05   | 44.73       | 81.14        |
| 0.5    | 41.75       | 89.10        |

---

## 4. Observations
- Low lambda → low sparsity, high accuracy
- Medium lambda → balanced trade-off
- High lambda → high sparsity, reduced accuracy

---

## 5. Gate Distribution Analysis
The histogram of gate values shows a strong spike near zero, indicating that many weights have been pruned.

A secondary cluster of values away from zero represents important connections retained by the model.

---

## 6. Conclusion
The model successfully learns to identify and remove redundant connections during training. This demonstrates effective dynamic pruning and validates the approach of using L1 regularization for sparsity.
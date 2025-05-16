# CIFAR-10 Image Classification – Machine Learning Project

This project explores multiple machine learning approaches for classifying images from the CIFAR-10 dataset. Various preprocessing strategies and classification models were evaluated, including deep learning and ensemble methods.

##  Dataset

- **CIFAR-10**: 60,000 32×32 color images across 10 balanced classes.
- Classes: airplane, automobile, bird, cat, deer, dog, frog, horse, ship, truck

##  Preprocessing Steps

- **Flattening**: Images reshaped from 32×32×3 to 1D vectors.
- **Labeling**: Assigning correct labels to each image.
- **Normalization**: Applied to standardize pixel intensity distributions.
- **PCA**: Used to reduce dimensionality to 217 components, retaining 95% of data variance.
- **Whitening**: Applied for decorrelation before clustering (K-Means).

##  Models Evaluated

| Model              | Accuracy | Precision | Recall | ROC AUC |
|-------------------|----------|-----------|--------|---------|
| Softmax Regression| 38.00%   | 37.00%    | 38.00% | 80.23%  |
| SVM (RBF kernel)  | 36.40%   | 37.83%    | 36.40% | 80.72%  |
| Random Forest      | 43.91%   | 43.46%    | 43.91% | 83.25%  |
| XGBoost (HOG features)| 55.93%| 55.68%    | 55.93% | 90.43%  |
| MLP               | 58.56%   | —         | —      | —       |
| K-Means + SVM     | **73.00%**| 73.10%   | 73.00% | —       |

## 🔍 Feature Engineering

- **HOG (Histogram of Oriented Gradients)** used for XGBoost to extract structural and textural information.
- **Patch extraction** + **K-Means** + **Triangle encoding** for unsupervised feature learning in ensemble models.

##  Best Performing Model

The **K-Means + SVM** pipeline achieved the highest classification accuracy at **73%**, significantly outperforming all other models. This approach benefited from patch-based whitening, unsupervised feature learning, and spatial pooling.




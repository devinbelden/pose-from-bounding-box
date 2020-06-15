# Predicting 3D World Position Given A 2D Bounding Box


 For this project, we are taking a modified dataset procured from the [Peking University](https://www.kaggle.com/c/pku-autonomous-driving) Kaggle dataset, and seeing if we can use bounding boxes to predict the actual position in 3-dimensional space. In other words, we're trying to use monocular vision to "see" in three dimensions.
 
## Methods

The bounding boxes (and the positional/dimensional data therein) were created using YOLO, by another user on Kaggle. The bounding box data is located [here](https://www.kaggle.com/alvaroibrain/carworldpositions). Due to the format of this dataset, no image processing is required. Instead, we take a singular Pandas dataframe, scale the data, and run it through an array of models, including:
- K-Nearest Neighbors
- Random Forest (with Gradient Boosting, AdaBoost, and XGBoost)
- Support Vector Machines
- Neural Networks

## Accuracy

A relatively high degree of accuracy was obtained from the XGBoost methodology. The R-squared value was 0.881, and the R-squared breakdown by dimension was as follows:
- X: 0.977
- Y: 0.822
- Z: 0.861

## Conclusions

We can assume that the reasoning for the lower Y and Z accuracies was due to physical limitations with this method of determining real-world positioning in the first place. In other words, using data from a 2-dimensional photo may not be the most ideal way to determine 3D positioning. Other techniques, or even hardware, should most likely be used; current methods include LiDAR, a repurposed ACC module, and more sophisticated modeling techniques therein.
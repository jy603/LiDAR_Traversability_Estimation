# [i3ce2024] LiDAR-based Traversability Estimation for Ground Robots on Construction Sites Using Self-Supervised Learning

This repository is the official implementation of "LiDAR-based Traversability Estimation for Ground Robots on Construction Sites Using Self-Supervised Learning". 

> [!NOTE]  
> [07/29/24] The codes will be released in a month!

# Abstract 
Navigating autonomous robots through the intricate landscapes of construction sites necessitates an accurate evaluation of traversability, a challenge that our research addresses with a self-supervised learning strategy utilizing 3D LiDAR point cloud data. This approach enables ground robots to autonomously identify traversable areas based on the spatial relationships between their trajectories and the surrounding environmental features. By employing self-supervised trajectory area labeling and Positive-Unlabeled (PU) learning, our method classifies points as traversable or non-traversable without labor-intensive manual annotations. Utilizing the RELLIS-3D and Hilti datasets, coupled with Simultaneous Localization and Mapping (SLAM) for trajectory mapping, we conducted qualitative and quantitative assessments with vehicle/robot-mounted LiDAR systems. Results show that the proposed method can reasonably identify traversable areas from LiDAR data for robots in off-road environments as well as robots on construction sites.

# Dataset Preparation
## Datasets
Both dataset should be prepared in Kitti format
1. [Rellis-3D](https://github.com/unmannedlab/RELLIS-3D)
    - Provided pose files format: [R00, R01, R02, Tx, R10, R11, R12, Ty, R20, R21, R22, Tz]
3. [Hilti](https://hilti-challenge.com/dataset-2022.html)
    - Provided pose files format: [timestamp, Tx, Ty, Tz, QW, QX, QY, QZ]

## Semantic Segmentation Models
- [SphereFormer](https://github.com/dvlab-research/SphereFormer)



# [i3ce2024] LiDAR-based Traversability Estimation for Ground Robots on Construction Sites Using Self-Supervised Learning

- Authors: Jinhee Yu, Swayamjit Saha, Monika Jayakumar, Mikias Gugssa, Jingdao Chen, Jun Wang
  
<p align="center">
<img src=/visualizations/HORIZ_BCoE_CMYK_100px.jpg width="300" />
</p>

This repository is the official implementation of "LiDAR-based Traversability Estimation for Ground Robots on Construction Sites Using Self-Supervised Learning". 

> [!NOTE]  
> [07/29/24] The full codes will be released in a month!

<p align="center">
<img src=/visualizations/rellis_results.png/>
    <em>This figure illustrates some of the results of our traversability estimation method on the RELLIS-3D LiDAR dataset (Velodyne Ultra Puck). On the top row is the RGB camera image, the middle row shows the corresponding model outputs, and the bottom row shows ground truth for comparison. (Red dots represent traversable points, while blue dots represent non-traversable points)</em>
</p>

# Abstract 
Navigating autonomous robots through the intricate landscapes of construction sites necessitates an accurate evaluation of traversability, a challenge that our research addresses with a self-supervised learning strategy utilizing 3D LiDAR point cloud data. This approach enables ground robots to autonomously identify traversable areas based on the spatial relationships between their trajectories and the surrounding environmental features. By employing self-supervised trajectory area labeling and Positive-Unlabeled (PU) learning, our method classifies points as traversable or non-traversable without labor-intensive manual annotations. Utilizing the RELLIS-3D and Hilti datasets, coupled with Simultaneous Localization and Mapping (SLAM) for trajectory mapping, we conducted qualitative and quantitative assessments with vehicle/robot-mounted LiDAR systems. Results show that the proposed method can reasonably identify traversable areas from LiDAR data for robots in off-road environments as well as robots on construction sites.

---
## Environment Setup

We recommend creating a new virtual environment for running the code using either Anaconda or Mamba.

- **Anaconda**
```setup
conda env create -f SemanticTraverse.yml
``` 
- **Mamba**
```setup
mamba env create --file SemanticTraverse.yml
```
---

# Dataset Preparation
## Datasets
Both datasets should be prepared in Kitti format
1. [Rellis-3D](https://github.com/unmannedlab/RELLIS-3D)
    - Provided pose files format: [R00, R01, R02, Tx, R10, R11, R12, Ty, R20, R21, R22, Tz]
3. [Hilti](https://hilti-challenge.com/dataset-2022.html)
    - Provided pose files format: [timestamp, Tx, Ty, Tz, QW, QX, QY, QZ]

# Pose Estimation
If your data does not have pose information, you can use Simultaneous Localization and Mapping (SLAM) to estimate it. SLAM is the process of simultaneously building a map and localizing the robot's position in it. Here, we use [HDL Graph SLAM](https://github.com/koide3/hdl_graph_slam), which is a popular open-source ROS package for real-time 6DOF SLAM poses using 3D LiDAR sensor data for the Hilti dataset.

# Train
```bash
python train_pu.py --config {YOUR_CONFIG_FILE_PATH}
```

# Test
```bash
python test_pu.py --config {YOUR_CONFIG_FILE_PATH}
```

# Acknowledgment
Our code is based on the following repositories:
- [HDL Graph SLAM](https://github.com/koide3/hdl_graph_slam)
- [SphereFormer](https://github.com/dvlab-research/SphereFormer)


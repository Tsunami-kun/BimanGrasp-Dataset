# BimanGrasp-Dataset
This is the official repo for the release of BimanGrasp-Dataset of our RA-L 24' Paper "Bimanual Grasp Synthesis for Dexterous Robot Hands". 

## Introduction

BimanGrasp-Dataset is a large-scale synthetic dataset of a pair of shadow robot hands grasping various objects. All the grasps are verified with Isaac Gym simulator, and through penetration test (threshold： 1.5 mm). In this repo, we provide the grasp pose data together with object meshes and other assets. All the grasps can be visualized with plotly 3D.

## Installation

    # We suggest to use conda/mamba environments for loading and visualizing bimanual grasp poses, e.g.,
    conda create -n bimangrasp python=3.7
    conda activate bimangrasp

    # for cuda == 11.3
    conda install pytorch==1.12.1 torchvision==0.13.1 cudatoolkit=11.3 -c pytorch
    # else, just install the torch version that matches the cuda version
    
    # install some necessary packages
    pip install trimesh plotly numpy argparse transforms3d

    # install pytorch3d that matches torch and python version, e.g., with pytorch==1.12.1:
    cd third_party && wget https://github.com/facebookresearch/pytorch3d/archive/refs/tags/v0.7.1.tar.gz && tar -xzvf v0.7.1.tar.gz && cd v0.7.1.tar.gz && pip install -e. && cd ../..

    # install other third party packages
    cd third_party/pytorch_kinematics && pip install -e .
    cd ../third_party/torchSDF && pip install -e . && cd ../..

## Visualization

First, download the release dataset and object meshes from https://github.com/Tsunami-kun/BimanGrasp-Dataset/releases, and then extract them to the root directory of the repo.

    # This outputs 3d html visualization. ckeck dataset for object names (<object_name>.npy), and use --object_name <object_name> --num <num> to visualize the <num>th pose for the object named by <object_name>.
    
    python visualization.py --object_name <object_name> --num <num>

One visualization example (both 2D screenshot and 3D html vis.) is in the directory examples/.

## Acknowledgement

We would like to express our gratitude to the authors of the following repositories, from which we referenced code:

* [DexGraspNet](https://github.com/PKU-EPIC/DexGraspNet/tree/main)
* [UGG](https://github.com/Jiaxin-Lu/ugg/tree/main)

## Citation
If you find this repository useful in your research, please cite
```
@article{shao2024bimanual,
  title={Bimanual Grasp Synthesis for Dexterous Robot Hands},
  author={Shao, Yanming and Xiao, Chenxi},
  journal={IEEE Robotics and Automation Letters},
  year={2024},
  publisher={IEEE}
}
```
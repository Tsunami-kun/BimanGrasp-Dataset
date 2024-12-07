# BimanGrasp-Dataset
This is the official repo for the release of BimanGrasp-Dataset of our Paper


<p align="center">
  <h2 align="center">Bimanual Grasp Synthesis for Dexterous Robot Hands</h2>


<p align="center">
    <strong>Yanming Shao</strong></a>
    ·
    <strong>Chenxi Xiao*</strong>
 </p>
 
<h3 align="center">RA-L 24' | Transferred to ICRA 25'</h3>

<p align="center">
    <a href="https://arxiv.org/abs/2411.15903">
      <img src='https://img.shields.io/badge/Paper-green?style=for-the-badge&logo=adobeacrobatreader&logoColor=white&labelColor=66cc00&color=94DD15' alt='Paper PDF'>
    </a>
</p>



<table>
  <tr>
    <td><img src="gif/A1.gif" alt="GIF 1" width="240"></td>
    <td><img src="gif/A2.gif" alt="GIF 2" width="240"></td>
    <td><img src="gif/A3.gif" alt="GIF 3" width="240"></td>
  </tr>
  <tr>
    <td><img src="gif/B1.gif" alt="GIF 4" width="220"></td>
    <td><img src="gif/B2.gif" alt="GIF 5" width="220"></td>
    <td><img src="gif/B3.gif" alt="GIF 6" width="220"></td>
  </tr>
  <tr>
    <td><img src="gif/C1.gif" alt="GIF 7" width="220"></td>
    <td><img src="gif/C2.gif" alt="GIF 8" width="220"></td>
    <td><img src="gif/C3.gif" alt="GIF 9" width="220"></td>
  </tr>
</table>


<div style="display: flex; justify-content: center; gap: 10px; flex-wrap: wrap; width: 100%;">
  <img src="gif/A1.gif" alt="GIF 1" style="width: 30%;" />
  <img src="gif/A2.gif" alt="GIF 2" style="width: 30%;" />
  <img src="gif/A3.gif" alt="GIF 3" style="width: 30%;" />
</div>

<div style="display: flex; justify-content: center; gap: 10px; flex-wrap: wrap; width: 100%;">
  <img src="gif/B1.gif" alt="GIF 4" style="width: 30%;" />
  <img src="gif/B2.gif" alt="GIF 5" style="width: 30%;" />
  <img src="gif/B3.gif" alt="GIF 6" style="width: 30%;" />
</div>

<div style="display: flex; justify-content: center; gap: 10px; flex-wrap: wrap; width: 100%;">
  <img src="gif/C1.gif" alt="GIF 7" style="width: 30%;" />
  <img src="gif/C2.gif" alt="GIF 8" style="width: 30%;" />
  <img src="gif/C3.gif" alt="GIF 9" style="width: 30%;" />
</div>

<div style="display: flex; justify-content: center; gap: 10px; flex-wrap: wrap; width: 100%;">
  <img src="gif/D1.gif" alt="GIF 10" style="width: 30%;" />
  <img src="gif/D2.gif" alt="GIF 11" style="width: 30%;" />
  <img src="gif/D3.gif" alt="GIF 12" style="width: 30%;" />
</div>

<div style="display: flex; justify-content: center; gap: 10px; flex-wrap: wrap; width: 100%;">
  <img src="gif/E1.gif" alt="GIF 13" style="width: 30%;" />
  <img src="gif/E2.gif" alt="GIF 14" style="width: 30%;" />
  <img src="gif/E3.gif" alt="GIF 15" style="width: 30%;" />
</div>

<div style="display: flex; justify-content: center; gap: 10px; flex-wrap: wrap; width: 100%;">
  <img src="gif/F1.gif" alt="GIF 16" style="width: 30%;" />
  <img src="gif/F2.gif" alt="GIF 17" style="width: 30%;" />
  <img src="gif/F3.gif" alt="GIF 18" style="width: 30%;" />
</div>



## Introduction

BimanGrasp-Dataset is a large-scale synthetic dataset of a pair of shadow robot hands grasping various objects. All the grasps are verified with Isaac Gym simulator, and through penetration test (less than 1.5 mm). In this repo, we provide the grasp pose data together with object meshes and other assets. All the grasps can be visualized with plotly package.

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

## Examples

[3D Visualization Example](examples/example.html)

![2D Screenshot Example](examples/example.png)

## Acknowledgement

We would like to express our gratitude to the authors of the following repositories, from which we referenced code:

* [DexGraspNet](https://github.com/PKU-EPIC/DexGraspNet/tree/main)
* [UGG](https://github.com/Jiaxin-Lu/ugg/tree/main)

## Citation
If you find BimanGrasp-Dataset useful in your research, please cite
```
@article{shao2024bimanual,
  title={Bimanual Grasp Synthesis for Dexterous Robot Hands},
  author={Shao, Yanming and Xiao, Chenxi},
  journal={IEEE Robotics and Automation Letters},
  year={2024},
  volume={9},
  number={12},
  pages={11377-11384},
  publisher={IEEE},
  doi={10.1109/LRA.2024.3490393}
}
```

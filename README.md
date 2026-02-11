# RNA Base Pair Recognition

## Overview
- Author: Huang Yanjie
- FY (yy): 25
- Topic keywords: RNA, basepair, YOLOv8-pose,SVM 
- Upstream: none

This repository provides the environment and execution instructions for RNA base pair recognition using YOLOv8-Pose and SVM classification.

---

## Environment (must)

- OS: macOS (Apple Silicon, M2)
- Python: 3.10
- Key libraries:
  - ultralytics
  - torch
  - torchvision
  - opencv-python
  - numpy
  - scikit-learn
- GPU/CUDA: Apple MPS (no CUDA)

---

## Setup

### Option A: pip
python -m venv .venv  
source .venv/bin/activate   (Windows: .venv\Scripts\activate)  
pip install -r requirements.txt  

### Option B: conda (recommended)
conda env create -f environment.yml  
conda activate yolov8  

---

## Data policy (must)

### Private dataset

The dataset used in this research is a custom dataset created for RNA base pair models.

Due to size and access restrictions, the dataset is NOT included in this repository.

To obtain the dataset:
- Contact the author

Required directory structure:

dataset/  
 ├── images/  
 ├── labels/  
 └── data.yaml  

Do NOT upload dataset files to this repository.

---

## How to run (reproducibility) (must)

1. Setup environment (see above)
2. Prepare dataset
3. Run:

yolo pose predict model=runs_pose/train20/weights/best.pt source=dataset/images  

If using a custom script:

python angle.py  

Modify paths according to your local environment.

---

## Expected outputs

- Detection results saved in:
  runs/
- Predicted keypoints for each image
- Angle calculation results (console or CSV)
- Classification results for each image

---

## Reproducibility check (must)

Tested on macOS (Apple M2).  
The environment can be reproduced by creating the conda environment and running the commands above.

---

## Manual steps (if any)

- Modify dataset path according to your local environment.
- Modify model path if necessary.
- Ensure the trained weight file exists:

runs_pose/train20/weights/best.pt

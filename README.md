# 🚦 Traffic Light Detection Using YOLOv11

This project focuses on detecting red and green traffic lights using a custom-trained **YOLOv11** model. The training data is annotated using **Label Studio**, and both image and video inputs are supported for inference.

---

## 📁 Project Structure
```
images/                   # All collected traffic light images
videos/                   # Test video for inference
project/                  # Unzipped annotated YOLO dataset
├── images/               # Annotated images
├── labels/               # YOLO format label files
├── classes.txt           # Class names (e.g., red, green)
└── notes.json5           # Metadata from Label Studio
dataset/                  # Organized dataset for training and validation
├── train/
│   ├── images/           # Training images
│   └── labels/           # Training labels
└── val/
    ├── images/           # Validation images
    └── labels/           # Validation labels
data.yaml                 # YAML configuration file for YOLO training
YOLOv11.ipynb             # Jupyter notebook for training and predictions
YOLOv11_custom.pt         # Final trained YOLOv11 weights
run_predictions/          # Output folder for prediction results (images & video)
```

---

## ✅ Steps to Run the Project

1. **Collect Data**
   - Gather all traffic light images and place them inside the `images/` folder.
   - Add a test video inside the `videos/` folder for final inference.

2. **Annotate Using Label Studio**
   - Annotate **red** and **green** traffic lights.
   - Export the annotations in **YOLO format** (as a ZIP file).

3. **Unzip Project**
   - Unzip the exported file (e.g., `project.zip`) into the `project/` directory.
   - The folder should contain:
     - `images/`
     - `labels/`
     - `classes.txt`
     - `notes.json5`

4. **Split Data for Training and Validation**
   - Create `dataset/train/` and `dataset/val/` folders.
   - Move images and labels from `project/` into these folders based on your split.

5. **Create data.yaml**
   Create a file named `data.yaml` with the following content:

   ```yaml
   path: ./dataset
   train: train
   val: val
   nc: 2
   names: ['red', 'green']


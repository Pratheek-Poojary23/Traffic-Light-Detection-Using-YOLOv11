# 🚦 Traffic Light Detection Using YOLOv11

This project focuses on detecting red and green traffic lights using a custom-trained **YOLOv11** model. The training data is annotated using **Label Studio**, and both image and video inputs are supported for inference.

---

## 📸 Sample Output

![Traffic Light Detection](https://github.com/Pratheek-Poojary23/Traffic-Light-Detection-Using-YOLOv11/blob/main/runs/detect/predict/2.jpg)

*Red and Green traffic light detection using YOLOv11*


## 📁 Project Structure
```
images/                   # All collected traffic light images
videos/                   # Test video for inference
project/                  # Unzipped annotated YOLO dataset
├── images/               # Annotated images
├── labels/               # YOLO format label files
├── classes.txt           # Class names (e.g., red, green)
└── notes.json5           # Metadata from Label Studio             
├── train/
    ├── images/           # Training images
    └── labels/           # Training labels
└── val/
    ├── images/           # Validation images
    └── labels/           # Validation labels
data.yaml                 # YAML configuration file for YOLO training
YOLOv11.ipynb             # Jupyter notebook for training and predictions
YOLOv11_custom.pt         # Final trained YOLOv11 weights
run                       # Output folder for prediction results (images & video)
```

---

## ✅ Steps to Run the Project

1. **Collect Data**
   - Gathered all traffic light images and place them inside the `images/` folder.
   - Add a test video inside the `videos/` folder or root directory for final inference.

2. **Annotated the images Using Label Studio**
   - Annotate **redlight** and **greenlight** traffic lights.
   - Export the annotations in **YOLO with image** (as a ZIP file).

3. **Unzip Project**
   - Unzip the exported file (e.g., `project.zip`) into the `project/` directory.
   - The folder should contain:
     - `images/`
     - `labels/`
     - `classes.txt`
     - `notes.json5`

4. **Split Data for Training and Validation**
   - Created `train` and `val` folders in root directory.
   - Move images and labels from `project/` into these folders based on split.

5. **Create data.yaml**
   Create a file named `data.yaml` with the following content:

   ```yaml
   path: ./dataset
   train: train
   val: val
   nc: 2
   names: ['red', 'green']

## 🧪 Model Training and Prediction Workflow

### 📓 1. Create and Use `YOLOv11.ipynb`

Use the notebook `YOLOv11.ipynb`

---

### 🏋️ 2. Training the Model

- After training, the best model weights will be saved at:
```
runs/train/exp/weights/best.pt
```

---

### 📦 3. Prepare Final Model Weights

- Copy the `best.pt` file to your project's root directory.
- Rename it to: YOLOv11_custom.pt

---

### 🔮 4. Prediction

- Use the trained weights:

- You can run predictions on:
- Individual **images**
- Full **videos**

---

### 🖼️ 5. Output

- All prediction results will be saved in the following folder:
```
run
```

**Glove vs No-Glove Detection**

This project is part of a safety compliance system that checks whether workers are wearing gloves on factory floors.
A fine-tuned YOLOv8 (Ultralytics) model is used to detect two classes:

1.glove

2.no_glove

**The system processes a folder of images and generates:**

Annotated images with bounding boxes

JSON logs containing labels, confidence scores, and bounding box coordinates

**Dataset**

I created a custom dataset by manually collecting images of hands with and without gloves.
All images were annotated using VoTT in Pascal VOC format, then converted into YOLO format.

**Augmentation Used**

To improve model performance and robustness, the following augmentations were applied:

1.Flips

2.Zoom

3.Brightness adjustment

4.Sharpness adjustment

5.Rotation

**Classes**

1.glove

2.no_glove

**Model Details**

Framework: Ultralytics YOLO

Base Model: YOLOv8n

Training: Fine-tuned on a 2-class dataset

Epochs: 50

How to Run the Script

Install dependencies

pip install ultralytics opencv-python


Run detection

python detection_script.py --source ./input --out_dir ./output --conf 0.3

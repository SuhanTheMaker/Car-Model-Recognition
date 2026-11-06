# Car Model Recognition System

A fine-grained vehicle recognition system built using YOLOv8 and ResNet50 on the Stanford Cars Dataset.

## Overview

This project implements a two-stage vehicle recognition pipeline:

1. Detect and crop the vehicle using YOLOv8.
2. Classify the vehicle model using a fine-tuned ResNet50.

The system is designed to improve classification accuracy by reducing background noise and focusing on the vehicle itself.

---

## Dataset

Stanford Cars Dataset

- 196 vehicle categories
- Fine-grained classification task
- Thousands of labeled vehicle images

---

## Model Architecture

### Stage 1: Vehicle Detection

YOLOv8 is used to:

- Detect vehicles in the image
- Select the largest detected vehicle
- Crop and preprocess the vehicle region

### Stage 2: Vehicle Classification

ResNet50 Transfer Learning:

- ImageNet pretrained weights
- Fine-tuned on Stanford Cars Dataset
- 196 output classes

---

## Technologies

- Python
- PyTorch
- YOLOv8
- ResNet50
- Gradio
- Hugging Face Spaces

---

## Results

| Model | Validation Accuracy |
|---------|---------|
| ResNet50 Fine-tuning | 84.29% |
| YOLOv8 + ResNet50 Pipeline | ~90% |

The YOLO preprocessing stage significantly improved recognition performance by removing irrelevant background information.

---

## Deployment

The model was deployed using:

- Gradio
- Hugging Face Spaces

Users can upload a vehicle image and receive the predicted vehicle make and model.

---

## Repository Structure

```text
app.py                 # Gradio application
requirements.txt       # Dependencies

reports/
├── training_resnet50_finetuning.html
├── experiment_yolo_pipeline.html
└── experiments_resnet50_cropped.html

## Demo Results

Example predictions can be found in:

- results/GoodR1.PNG
- results/GoodR2.PNG
- results/GoodR3.PNG
- results/BadR1.PNG
- results/BadR2.PNG


## Live Demo

🚀 Try the Online Demo:

(https://huggingface.co/spaces/CSSE416Project/CSSE416Project-CarModelRecognition)


## Discussion and Observations

During development, we initially hypothesized that removing background information would improve classification performance by allowing the model to focus solely on vehicle features.

However, some cropped-image experiments did not consistently outperform the baseline model.

One possible explanation we considered was that certain background information may provide useful contextual signals. For example:

* Luxury vehicles are often photographed in dealerships, showrooms, or urban environments.
* Off-road vehicles may appear in outdoor or natural settings.
* Vehicle type and surrounding scene may exhibit statistical correlations within the dataset.

As a result, removing all background information may eliminate both irrelevant noise and potentially useful contextual cues.

While this hypothesis was not formally validated, it became an important discussion point during model development and helped motivate further exploration of the YOLOv8 + ResNet50 pipeline.

This experience highlighted the importance of validating assumptions through experimentation rather than relying solely on intuition.


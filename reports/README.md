# Experiment Reports

This directory contains exported Jupyter Notebook reports documenting the development process of the Car Model Recognition System.

The project evolved through multiple stages, starting from a baseline ResNet50 classifier and eventually reaching a complete YOLOv8 + ResNet50 two-stage recognition pipeline.

---

## Experiment Timeline

### Stage 1: Baseline Vehicle Classification

**File:** `training_resnet50_finetuning.html`

This report contains the initial transfer learning experiments using ResNet50 on the Stanford Cars Dataset.

Contents include:

* Dataset preprocessing
* Data augmentation
* Transfer learning setup
* Hyperparameter configuration
* Training and validation performance
* Accuracy evaluation

**Objective**

Establish a baseline fine-grained vehicle classification model using full vehicle images.

---

### Stage 2: Cropped Vehicle Classification

**File:** `experiments_resnet50_cropped_images.html`

This report investigates whether removing background information can improve classification accuracy.

Contents include:

* Vehicle image cropping experiments
* Background noise reduction analysis
* Dataset reconstruction
* ResNet50 retraining and evaluation
* Performance comparison with baseline results

**Objective**

Evaluate the impact of focusing the classifier on vehicle-only regions instead of full-scene images.

---

### Stage 3: YOLOv8 + ResNet50 Two-Stage Pipeline

**File:** `experiment_yolo_pipeline.html`

This report documents the final end-to-end recognition pipeline.

Pipeline:

1. Detect vehicles using YOLOv8
2. Crop the detected vehicle region
3. Classify the vehicle model using a fine-tuned ResNet50

Contents include:

* YOLOv8 object detection setup
* Vehicle extraction pipeline
* Integration with ResNet50 classifier
* End-to-end inference workflow
* Final system evaluation

**Objective**

Build a production-style two-stage recognition system capable of improving classification performance through object detection and vehicle-focused preprocessing.

---

## Key Findings

| Experiment                 | Purpose                                       |
| -------------------------- | --------------------------------------------- |
| ResNet50 Fine-Tuning       | Establish baseline classification performance |
| Cropped Vehicle Training   | Reduce background interference                |
| YOLOv8 + ResNet50 Pipeline | Build complete recognition workflow           |

The final system adopted the YOLOv8 + ResNet50 architecture because it achieved better recognition performance by isolating vehicle regions before classification.

---

## Notes

These HTML files are exported notebook reports and are included for documentation and portfolio purposes.

The deployed application and source implementation can be found in the project root directory:

* `app.py`
* `requirements.txt`

A live demonstration of the project is available through Hugging Face Spaces.

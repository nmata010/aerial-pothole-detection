# Aerial Pothole Detection
Computer vision experiment and comparison for identifying road defects from drone footage using custom trained YOLO models (and SAM 3).

## Overview
This project explores the impact of data strategy on custom computer vision models and compares the utility of custom trained models with SOTA zero-shot promptable models (like [meta/SAM 3](insert-link)).

I started off with a model trained on street-level potholes (which performed poorly on aerial-view potholes) and iteratively improved it with a domain-specific dataset. I benchmarked these models against eachother and Meta's SAM 3 to compare object detection between fine tuned custom models and publicly available off-the-shelf solutions.

## Repo structure 
- `requirements.txt`: Dependencies (note SAM 3 dependencies omitted intentionally)
- notebooks/
    - `01_train_and_validate_yolo.ipynb`: Main training, validation, and inference. (adapted from [yolo template](https://github.com/mfranzon/yolo-training-template))
    - `02_sam3_get_labels.ipynb`: Setup and run SAM 3. Convert object masks to polygon labels in yolo format.

## Setup
- This repo assumes you're connecting to Google's Colab environment
- Some inference tasks require a Roboflow API key to access hosted models (incl SAM3).
- The SAM 3 notebook uses HF API to download the model. You'll need to request access to the repo and provide your HF API key (instructions provided)

## Models & Results

| # | Model | Epochs | mAP50 | Download
| -- | -- | -- | -- | -- 
| 1 | Control_1e | 1 | 0.45% | [Link (HF)](https://huggingface.co/nmata010/street-level-pothole-detection-11192025_1epoch)
| 2 | Control_20e | 20 | 0.42% | [Link (HF)](https://huggingface.co/nmata010/street-level-pothole-detection-11192025_20epoch)
| 3 | Aerial_1e | 1 | 10.2% | [Link (HF)](https://huggingface.co/nmata010/aerial-pothole-detection-11212025_1Epoch_newDS)
| 4 | Aerial_20e | 20 | 42.9% | [Link (HF)](https://huggingface.co/nmata010/aerial-pothole-detection-11252025_20Epoch_newDS)
| 5 | Aerial_350e | 350 | 50.4% | [Link (HF)](https://huggingface.co/nmata010/aerial-pothole-detection-12022025_350Epoch_newDS)
| 6 | RoboflowAerial_350e | 350 | 57% | --




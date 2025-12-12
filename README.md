# Aerial Pothole Detection
Computer vision experiment and comparison for identifying road defects from drone footage using custom trained YOLO models (and SAM 3).

## Overview
This project explores the impact of data strategy on custom computer vision models and compares the utility of custom trained models with SOTA zero-shot promptable models (like [meta/SAM 3](insert-link)).

I started off with a model trained on street-level potholes (which performed poorly on aerial-view potholes) and iteratively improved it with a domain-specific dataset. I benchmarked these models against eachother and Meta's SAM 3 to compare object detection between fine tuned custom models and publically available off-the-shelf solutions.

**Results:**
- **Baseline; Ground-level images @ 1 Epoch:** 0.45% mAP50
- **Baseline; Ground-level images @ 20 Epoch:** 0.43% mAP50
- **Aerial Images @ 20 Epochs:** 42.9% mAP50
- **Aerial Images @ 350 Epochs:** 50.4% mAP50
- **Aerial Images, Hyperparameter tuned @ 350 Epochs:** 57.0% mAp50

## Repo structure
- here's the notebooks
    - One to train/validate (yolo template)
    - One to compare (?)
    - One to turn sam3 into yolo labels
- here's the data
- here's the models
- requirements (idk do i really need this?)
- 


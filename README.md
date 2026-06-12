# Computer Vision 2024

This repo contains the projects I completed for the **Computer Vision course (CSE344 / CSE544 / ECE344 / ECE544)** in Winter 2024.  
Each project follows a cycle of **building from scratch → improving with advanced methods → analyzing results and limitations**

## Image Classification & Segmentation using Deep Learning

### Image Classification
1. CNN from scratch: First trained a CNN model from scratch on the Russian Wildlife dataset F1 0.65. The model didn't perform as well, revealing the limitations of small custom architectures.
2. Pre-trained ResNet18: Fine tuned a pre-trained Resnet model on the same dataset. The model performed well, accuracy improved to F1 0.83 but showed overfitting, highlighting risks of high-capacity models on limited data.
Analysis of misclassification errors showed that both low-color and cropped images were classified incorrectly.
3. Data augmentation: 
Augmented data with Colour Blasted, Cropped and rotated images and retrained Resenet18 Pre-trained model. This Boosted accuracy to F1 0.90. This solved overfitting and fixed misclassifications (e.g. black vs brown bear).  

### Image Segmentation 
Applied a DeepLabv3+ model trained on Cityscapes to the Indian Driving Dataset. It performed well on sky, vegetation, and buildings but failed on scooters and pedestrians, revealing strong dataset bias. The model, optimized for European road scenes, struggled to generalize to Indian street conditions.

## Camera Calibration & LIDAR-Camera Cross-Calibration  
1. Estimated camera intrinsics, extrinsics, distortion coefficients, and reprojection errors using chessboard images.  
2. Solved the 3D transformation between camera and LIDAR, projecting LIDAR points into the image to analyze alignment errors.  
Gained hands-on understanding of how multi-sensor systems are aligned in robotics and autonomous driving.  

## Panorama Generation  
1. Derived epipoles from the Essential matrix and studied rectification to build intuition about stereo geometry.
2. implemented a panorama pipeline using SIFT keypoints, BruteForce and FLANN matching, RANSAC homography, warping, and stitching.
3. I extended the pipeline to support multi-image sequences, applying stereo vision concepts to create a complete panorama stitching system from scratch.

## Vision-Language Models (Segmentation & VQA)  
- Open-Vocabulary Segmentation (CLIPSeg): Segmented images using text prompts instead of fixed labels. Compared outputs with ground truth and DeepLabv3+ from Image Segmentation Project, computing mAP to evaluate strengths and gaps.  
- Visual Question Answering (BLIP): Used BLIP to answer natural language questions about images. Extended to a dataset of images + annotated Q&A, computed accuracy, and analyzed failure cases when the model misunderstood context.  

## Takeaways
- Built end-to-end systems: classification, segmentation, calibration, panorama stitching, 3D reconstruction.  
- Experienced both **deep learning** (CNNs, ResNet, DeepLabv3+) and **geometry-based CV** (epipolar geometry, SfM).  
- Learned to analyze **results, biases, and limitations**, not just train models.  
  

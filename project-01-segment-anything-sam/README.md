# Segment Anything (SAM) — Interactive Image Segmentation

This project demonstrates zero-shot image segmentation using Meta AI’s **Segment Anything Model (SAM)** with the **ViT-B** checkpoint.

## What this notebook does
- Installs required libraries (OpenCV, Pillow, Matplotlib) and SAM
- Downloads SAM model weights (`sam_vit_b_01ec64.pth`)
- Runs segmentation using:
  - **Single-point prompt** (click-based segmentation)
  - **Multi-point prompt** (include + exclude points)
  - **Bounding-box prompt**
- Tests **zero-shot segmentation** on a second image
- Saves visualization outputs as PNG files
- Includes a small timing test (image encoding vs mask prediction)

## Files
- `ML_CourseProject.ipynb` — main notebook

## Requirements
Recommended to run in **Google Colab** (GPU optional but helpful).
Libraries used:
- opencv-python
- pillow
- matplotlib
- segment-anything (from GitHub)

## Model weights
The notebook downloads weights here:
- `model_weights/sam_vit_b_01ec64.pth`

## Input images (IMPORTANT)
The notebook currently loads images from paths like:
- `/content/white-collar_Pat-Roque-1024x731.jpg`
- `/content/img_7166.jpg`

If you run in Colab:
1. Upload your images to Colab, or mount Google Drive
2. Update the `cv2.imread(...)` paths to match your filenames

## Outputs
The notebook saves visual results as:
- `01_original_image.png`
- `02_segmentation_result.png`
- `03_multi_point_segmentation.png`
- `04_bbox_segmentation.png`
- `05_zero_shot_example.png`

## Notes
- SAM generates multiple masks per prompt; the notebook selects the best one using the highest score.
- Multi-point prompts help refine results by explicitly excluding background regions.

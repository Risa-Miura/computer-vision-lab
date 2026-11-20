# Computer Vision Lab

My notebooks and scripts from the free
[OpenCV Bootcamp](https://opencv.org/university/free-opencv-course/) by OpenCV
University, covering modules 1–12 of 14: image basics, video, filtering, feature
alignment, panoramas, HDR, object tracking and face detection.

The notebooks, scripts and sample assets are course material. My changes are listed
below and marked ✏️ in the module table.

## What I changed

- Notebooks 06 and 11 run locally on Windows. The course versions assume Google
  Colab, so I replaced the Colab paths and used `imageio-ffmpeg` for H.264 conversion.
- Notebook 10: fixed NaN pixels from Mantiuk tone mapping that broke the saved image.
- Notebook 11: switched to `opencv-contrib-python` so the legacy trackers (Boosting,
  TLD, MedianFlow, MOSSE) are available.
- `camera.py` and `camera_filters.py`: line-by-line study notes.
- `display_image.py`: works from any working directory.

## Previews

**Panorama stitching (module 09):**

![Boat photos stitched into one panorama](docs/images/panorama.jpg)

**CSRT object tracking (module 11):**

![CSRT tracker following a race car](docs/images/tracking-csrt.jpg)

<!-- TODO: add docs/images/camera-filters-canny.jpg (camera_filters.py in Canny mode, key C) -->

## Modules

| # | Topic | Files |
|---|-------|-------|
| 01 | Reading, displaying and saving images | Notebook, `display_image.py` ✏️ |
| 02 | Cropping, resizing, flipping, pixel access | Notebook |
| 03 | Drawing shapes and text | Notebook |
| 04 | Brightness/contrast, thresholding, bitwise ops | Notebook |
| 05 | Webcam preview | `camera.py` ✏️ |
| 06 | Writing video files | Notebook ✏️ |
| 07 | Live blur, Canny edges, corner detection | `camera_filters.py` ✏️ |
| 08 | Form alignment with ORB + homography | Notebook |
| 09 | Panorama stitching | Notebook |
| 10 | HDR and tone mapping | Notebook ✏️ |
| 11 | Object tracking (KCF, CSRT, GOTURN, ...) | Notebook ✏️ |
| 12 | Face detection with a DNN model | `face_detection.py` |

## Project structure

- `notebooks/` — one folder per module (`01-image-basics/` … `12-face-detection/`) with its notebook or script and assets
- `docs/images/` — README screenshots
- `main.py` — prints the installed OpenCV version
- `requirements.txt` — Python dependencies

## Credits

- [OpenCV Bootcamp](https://opencv.org/university/free-opencv-course/), OpenCV
  University. The notebooks, scripts, images, videos and models in `notebooks/` are
  theirs.
- GOTURN model: Held, Thrun and Savarese,
  [Learning to Track at 100 FPS with Deep Regression Networks](https://arxiv.org/abs/1604.01802),
  ECCV 2016.

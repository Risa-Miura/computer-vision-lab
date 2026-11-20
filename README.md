# Computer Vision Lab 📷✨

hello! this is my lab notebook from the free
[OpenCV Bootcamp](https://opencv.org/university/free-opencv-course/) by OpenCV
University 🎓 I've done 12 of the 14 modules so far, and they all live here: everything
from loading my very first image to stitching panoramas, HDR, tracking a race car 🏎️
and finding faces 🙂

most of what's here is course material (the notebooks, scripts and sample
assets), so the credit for that goes to OpenCV.org 💛 the bits I added myself:

- got the video-writing (06) and object-tracking (11) notebooks running on my
  Windows laptop. the course versions expect Google Colab, so I swapped in portable
  paths and `imageio-ffmpeg` for the H.264 conversion
- fixed the HDR notebook (10), where Mantiuk tone mapping was sneaking NaN pixels
  into the saved image
- switched to `opencv-contrib-python` so the older trackers (Boosting, TLD,
  MedianFlow, MOSSE) work again
- left line-by-line study notes in the camera scripts (05, 07) while I was
  figuring out array shapes, BGR order and `waitKey`
- a small fix so the image display demo (01) works from any folder

| panorama stitching (09) | CSRT tracking (11) |
| --- | --- |
| ![Boat photos stitched into one panorama](docs/images/panorama.jpg) | ![CSRT tracker following a race car](docs/images/tracking-csrt.jpg) |

<!-- TODO: add docs/images/camera-filters-canny.jpg (camera_filters.py in Canny mode, key C) -->

## modules

✏️ = I changed something here

| # | what it's about | files |
| --- | --- | --- |
| 01 | image basics: reading, displaying, saving, BGR vs. RGB | notebook, `display_image.py` ✏️ |
| 02 | cropping, resizing, flipping, poking at pixels | notebook |
| 03 | drawing shapes and text | notebook |
| 04 | brightness/contrast, thresholding, bitwise ops | notebook |
| 05 | webcam preview | `camera.py` ✏️ |
| 06 | writing video files | notebook ✏️ |
| 07 | live blur, Canny edges and corner detection | `camera_filters.py` ✏️ |
| 08 | lining up a scanned form with ORB + homography | notebook |
| 09 | panorama stitching | notebook |
| 10 | HDR and tone mapping | notebook ✏️ |
| 11 | object tracking (KCF, CSRT, GOTURN, ...) | notebook ✏️ |
| 12 | face detection with a DNN model | `face_detection.py` |

## running things

the camera scripts use your webcam by default, or you can hand them a video file
instead

```powershell
# webcam preview (Esc to quit)
python notebooks/05-camera-access/camera.py

# live filters: P preview, B blur, C edges, F corners, Q/Esc quit
python notebooks/07-image-filtering-and-edge-detection/camera_filters.py

# same thing, no webcam needed
python notebooks/07-image-filtering-and-edge-detection/camera_filters.py notebooks/06-video-writing/race_car.mp4
```

face detection has to run from its own folder, since it downloads the model files
there the first time:

```powershell
Set-Location notebooks/12-face-detection
python face_detection.py
```

for the notebooks, start Jupyter from inside the module folder so the relative
asset paths work:

```powershell
Set-Location notebooks/09-panorama-creation
jupyter notebook 09_panorama.ipynb
```

the tracking notebook (11) needs a kernel restart after its setup cell.

## credits

- [OpenCV Bootcamp](https://opencv.org/university/free-opencv-course/) by OpenCV
  University. the notebooks, scripts, images, videos and models in `notebooks/`
  are theirs.
- GOTURN model: Held, Thrun and Savarese, *Learning to Track at 100 FPS with Deep
  Regression Networks* (ECCV 2016).

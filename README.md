# SkinDetector
[![Build Status](https://travis-ci.org/WillBrennan/SkinDetector.svg?branch=master)](https://travis-ci.org/WillBrennan/SkinDetector)

This is a high-speed python based skin detection system using OpenCV, it is done using adaptive thresholding, reference
papers can be found below. It is designed for processing VGA sized images in real time for Gesture Control.


## Quick Start
Getting the app to run is pretty easy. This script will not [install OpenCV](http://docs.opencv.org/doc/tutorials/introduction/linux_install/linux_install.html).
However to install the rest of the project dependencies and run the demo script use the following commands;

```bash
# Clone the repo
git clone https://github.com/WillBrennan/SkinDetector && cd SkinDetector
make install
python FromFile.py <directory of images> --display
```

## Usage

```python
import cv2
import skin_detector

img_path = raw_input("Please Enter Image Path")
image = cv2.imread(img_path)
mask = skin_detector.process(image)
cv2.imshow("input", image)
cv2.imshow("mask", mask)
cv2.waitKey(0)
```

## Demonstration
![Demo on Astronaut](https://raw.githubusercontent.com/WillBrennan/SkinDetector/master/docs/assets/demo.png "Demonstration")

## Based Upon
This repo is based upon the paper; 
 - Skin Segmentation Using Multiple Thresholds (2003) - http://www.ivl.disco.unimib.it/papers2003/EI06-EI109%20Skin-paper.pdf
 
 . Which is no longer accessiable; its similar to the technique used in the more modern paper, [Skin color segmentation using multi-color space threshold](https://www.semanticscholar.org/paper/Skin-color-segmentation-using-multi-color-space-Rahmat-Chairunnisa/c06873e619c679fd1aa7648a6e402a7d57ea0e20?tab=abstract&citingPapersSort=is-influential&citingPapersLimit=10&citingPapersOffset=0&year%5B0%5D=&year%5B1%5D=&citedPapersSort=is-influential&citedPapersLimit=10&citedPapersOffset=10).


# License-plate-Recognition

This project demonstrates the process of automatic License Plate Recognition (LPR) using Python, the `imutils` library for image processing, and `easyocr` for Optical Character Recognition (OCR). The system captures an image, detects the license plate, and reads the characters on the plate.

## Table of Contents

- [Introduction](#introduction)
- [Features](#features)
- [Installation](#installation)
- [Usage](#usage)
- [Project Steps](#project-steps)
- [License](#license)

## Introduction

License Plate Recognition (LPR) is widely used in various fields such as traffic management, parking systems, and law enforcement. This project identifies and reads license plates from images through a pipeline of image processing and OCR using `imutils` and `easyocr`.

## Features

- Detects and reads license plates from images.
- Uses image processing techniques for plate localization.
- Leverages Optical Character Recognition (OCR) to extract license plate text.

## Installation

1. Clone this repository:

    ```bash
    git clone https://github.com/yourusername/license-plate-recognition.git
    ```

2. Install the required Python packages:

    ```bash
    pip install -r requirements.txt
    ```

    Make sure the following libraries are included in your `requirements.txt`:

    ```plaintext
    imutils
    easyocr
    opencv-python
    numpy
    matplotlib
    ```

## Usage

1. Prepare an image with a clear view of the license plate.
2. Run the Python script with the path to the image:

    ```bash
    python recognize_plate.py --image path/to/your/license_plate_image.jpg
    ```

3. The script will output the license plate text and display the detected plate region.

## Project Steps

### 1. Read in Image
The input image containing the vehicle and its license plate is loaded using OpenCV.

### 2. Grayscale and Blur
The image is converted to grayscale to reduce noise, and a Gaussian blur is applied to smooth the image.

### 3. Apply Filter and Find Edges for Localization
We apply edge detection (Canny edge detection) to find sharp changes in the intensity, highlighting the edges of the license plate.

### 4. Find Contours and Apply Mask
Contours are detected to find the rectangular area of the license plate. A mask is applied to isolate the region of interest (ROI).

### 5. Use EasyOCR to Read Text
The extracted license plate area is passed through `easyocr` to read the text.

### 6. Render Result
The detected license plate text is displayed on the original image and printed in the console.

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

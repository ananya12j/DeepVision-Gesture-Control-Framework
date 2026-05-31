# DeepVision Gesture Control Framework

## Overview

DeepVision Gesture Control Framework is a computer vision-based human-computer interaction system that enables touchless control of desktop operations using real-time hand gesture recognition.

The system uses OpenCV for image acquisition, a Convolutional Neural Network (CNN) built with TensorFlow/Keras for gesture classification, and PyAutoGUI for executing system-level actions. Users can control common desktop tasks such as scrolling, navigation, screenshots, window management, and application launching through predefined hand gestures captured via a webcam.

## Features

* Real-time hand gesture recognition using webcam input
* Custom gesture dataset collection pipeline
* CNN-based gesture classification model
* Touchless desktop control
* Automatic screenshot capture
* Browser navigation controls (Back / Forward)
* Scroll up and scroll down functionality
* Window management operations
* Application launching through gestures
* Confidence thresholding for reliable predictions
* Action cooldown mechanism to prevent unintended repeated actions

## Supported Gestures

| Gesture      | Action                        |
| ------------ | ----------------------------- |
| Scroll Up    | Scroll page upward            |
| Scroll Down  | Scroll page downward          |
| Back         | Navigate back                 |
| Forward      | Navigate forward              |
| Screenshot   | Capture and save screenshot   |
| Close Window | Close active window           |
| Open App     | Launch predefined application |
| None         | No action performed           |

## Project Architecture

### 1. Dataset Collection

* Captures gesture images using OpenCV.
* Defines a Region of Interest (ROI) for consistent hand positioning.
* Automatically stores images in gesture-specific directories.
* Collects 50 images per gesture class.

### 2. Model Training

* Preprocesses and normalizes captured images.
* Resizes images to 64×64 pixels.
* Uses a Convolutional Neural Network consisting of:

  * Convolution layers
  * Max Pooling layers
  * Fully Connected Dense layers
  * Dropout regularization
* Trains the model using TensorFlow/Keras.
* Saves the trained model as `gesturefinal.h5`.

### 3. Real-Time Gesture Recognition

* Loads the trained CNN model.
* Captures live webcam feed.
* Performs gesture prediction in real time.
* Executes desktop actions using PyAutoGUI.

## Tech Stack

* Python
* OpenCV
* TensorFlow / Keras
* NumPy
* Scikit-Learn
* PyAutoGUI

## Dataset Structure

```text
gesture1/
├── scroll_up/
├── scroll_down/
├── back/
├── forward/
├── screenshot/
├── close_window/
├── openapp/
└── none/
```

## Installation

```bash
git clone https://github.com/ananya12j/deepvision-gesture-control.git
cd deepvision-gesture-control

pip install -r requirements.txt
```

## Usage

### Step 1: Collect Gesture Data

```bash
python collect_dataset.py
```

### Step 2: Train the CNN Model

```bash
python train_model.py
```

### Step 3: Run Gesture Controller

```bash
python gesture_controller.py
```

## Future Enhancements

* Media player controls
* Volume adjustment gestures
* Presentation mode navigation
* Multi-hand gesture recognition
* Transfer learning using MobileNet or EfficientNet
* Improved gesture tracking with MediaPipe
* Cross-platform gesture automation

## Results

The system successfully performs real-time gesture classification and desktop automation with low latency, enabling an intuitive touchless interaction experience for productivity and accessibility applications.



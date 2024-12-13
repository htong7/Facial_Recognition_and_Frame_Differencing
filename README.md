# Video Movement Analysis

This project involves the analysis of movement in video files using two different methods: Frame Differencing and Optical Flow. The movement is quantified, and the results are visualized using matplotlib.

## Table of Contents
- [Installation](#installation)
- [Usage](#usage)
- [Functions](#functions)
  - [get_fps(video_file_path)](#get_fps-video_file_path)
  - [process_video_movement_frame_differencing(video_path)](#process_video_movement_frame_differencing-video_path)
  - [plotMovingAverage(series, window, plot_actual=False, scale=1.96)](#plotMovingAverage-series-window-plot_actual=False-scale-1.96)
- [Visualization](#visualization)
- [Contributing](#contributing)
- [License](#license)

## Installation

To use the code in this repository, you need to have Python installed along with the following libraries:
- pandas
- numpy
- opencv-python
- matplotlib

You can install these libraries using pip:

```sh
pip install pandas numpy opencv-python matplotlib
```

## Usage

To use the functions provided in this project, follow these steps:

1. Import the necessary libraries:
    ```python
    import pandas as pd
    import numpy as np
    import cv2
    import matplotlib.pyplot as plt
    import matplotlib.patches as mpatches
    import time
    ```

2. Define the functions `get_fps`, `process_video_movement_frame_differencing`, and `plotMovingAverage` as provided in the code.

3. Call the functions with appropriate parameters:
    ```python
    video_path = '/path/to/your/video/file'
    
    # Process video using Frame Differencing
    movement_per_second_differencing_with_timestamps = process_video_movement_frame_differencing(video_path)
    
    # Visualize movement analysis
    visualize_movement(movement_per_second_differencing_with_timestamps)
    
    # Calculate and plot moving average
    series = pd.Series([element[1] for element in movement_per_second_differencing_with_timestamps])
    plotMovingAverage(series, window=7, plot_actual=True)
    ```

## Functions

### `get_fps(video_file_path)`

This function calculates the Frames Per Second (FPS) of a given video file.

**Parameters:**
- `video_file_path` (str): The path to the video file.

**Returns:**
- `fps` (float): The FPS of the video file.

### `process_video_movement_frame_differencing(video_path)`

This function processes the movement in a video using frame differencing.

**Parameters:**
- `video_path` (str): The path to the video file.

**Returns:**
- `movement_per_second_differencing_with_timestamps` (list of tuples): A list of tuples where each tuple contains a second and the average movement for that second.

### `plotMovingAverage(series, window, plot_actual=False, scale=1.96)`

This function plots the moving average of a series.

**Parameters:**
- `series` (pd.Series): The data series to plot.
- `window` (int): The window size for the moving average.
- `plot_actual` (bool): Whether to plot the actual values alongside the moving average. Default is `False`.

## Visualization

The project includes visualization of the movement analysis results using matplotlib. The results are displayed as plots showing the movement per second and the moving average of the movement.

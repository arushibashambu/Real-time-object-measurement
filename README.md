# Real-Time Contour Detection and Measurement

This project implements a real-time contour detection and measurement system using OpenCV. It captures video from a webcam, detects quadrilateral shapes (such as rectangles or squares), and calculates their real-world dimensions (width, height, and area) based on user-defined parameters. The program displays the processed images and overlays the measurements directly on the detected shapes.
## Features

- **Real-time video capture** from the webcam.
- **Adjustable parameters** via a GUI (trackbars) for:
  - Edge detection thresholds.
  - Minimum area for detecting shapes.
  - Distance and scaling factors for real-world dimension calculations.
- **Contour detection** for quadrilateral shapes (shapes with four corners).
- **Real-world measurements** of width, height, and area in centimeters and square meters.
- **Overlay measurements** on detected contours with real-world dimensions and arrowed lines for visualization.
- **Image stacking** for displaying the original, processed, and contour-detected images in one view.

## Requirements

- Python 3.x
- OpenCV 4.x
- NumPy

You can install the necessary dependencies with the following command:

```bash
pip install opencv-python numpy
```

## How It Works

1. **Video Capture**: The application captures video frames from the default webcam.
2. **Image Processing**:
   - The captured frame is blurred, converted to grayscale, and edges are detected using Canny edge detection.
   - The edges are further processed using dilation and erosion to highlight contours.
3. **Contour Detection**: It detects contours in the processed image and filters them based on:
   - **Area**: Only contours larger than a certain threshold (adjustable via trackbars) are considered.
   - **Corners**: Only contours with four corners (quadrilaterals) are processed.
4. **Reordering Points**: The corner points of the detected shapes are reordered to ensure consistent orientation.
5. **Measurement Calculation**: Real-world width, height, and area of the shape are calculated based on user-defined scaling and distance parameters.
6. **Display**: The original, processed, and contour-detected images are displayed in a stacked format. Measurements are overlayed directly on the contours.

## Trackbars (Adjustable Parameters)

- **Threshold1 & Threshold2**: Control the sensitivity of the Canny edge detection.
- **Area**: Sets the minimum area required to consider a contour (in square pixels).
- **Distance**: A parameter to adjust the scaling of real-world measurements.
- **Scale**: A scaling factor used in calculating real-world dimensions.

## Usage

1. Run the program:

   ```bash
   python <your_script_name>.py
   ```

2. A window titled "Parameters" will open with trackbars for adjusting various parameters.

3. Use the trackbars to adjust thresholds, area, distance, and scale as needed.

4. The program will display two windows:
   - "Result": Stacked images showing the original frame, edge-detected frame, thresholded frame, and contour-detected frame.
   - "Measurement": The contours and measurements overlayed on the original frame.

5. Press `q` to quit the program.

## Example Output

- Detected quadrilaterals with width, height, and area overlayed.
- Stacked image display showing various stages of the image processing pipeline.

## Customization

You can customize the following:
- Change the number of corners (`corners` variable) if you're interested in detecting shapes other than quadrilaterals.
- Adjust the color of the contour lines and text by changing the `color` variable.
- Modify the scaling and distance logic to fit specific use cases for real-world measurements.

## Known Issues

- The code assumes that the camera is positioned properly for consistent distance and scaling measurements.
- Detection accuracy may decrease for complex backgrounds or when the shapes have broken edges.

## Future Improvements

- Add support for detecting more complex shapes with different corner counts.
- Implement automatic calibration to improve the accuracy of real-world measurements based on the camera's position.
- Enhance contour detection for shapes with broken edges or incomplete contours.

## License

This project is licensed under the MIT License.

---

Enjoy real-time shape detection and measurement with this OpenCV project!

# Smoke_colour_detection
Smoke Detection:
The ROI is converted to HSV color space and thresholds are applied to create a binary mask identifying smoke pixels.

Contour Analysis (if smoke detected):
Contours are found in the smoke mask. If a significant contour exists, it's approximated with a polygon.

Mask Creation:
A transparent mask is created with the chosen boundary color. Another mask is created to fill the smoke contour with white.

Highlighting and Overlay:
The transparent mask's alpha channel is adjusted based on the smoke mask (higher smoke probability = higher transparency). This mask is blended with the ROI for a translucent smoke effect. Finally, the masked ROI is overlaid on the original image.

![smoke_colour_4](https://github.com/Deeplearner11/Smoke_colour_detection/assets/87230145/5a9de21a-c96f-40ff-a67b-4aa4b034ed6b)

![smoke_colour_2](https://github.com/Deeplearner11/Smoke_colour_detection/assets/87230145/d9dc76f8-e74b-46b8-a97f-410ea6718455)

Average Color Calculation (if smoke detected):
It calculates the average Blue, Green, and Red values within the smoke region. This is done using OpenCV's cv2.sumElems function, which efficiently sums the elements of a masked array.
The calculation involves multiplying each color channel with the smoke_mask to consider only smoke pixels. The sum is then divided by the total smoke pixel count to get the average value for each channel.

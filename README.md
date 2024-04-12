# Smoke_colour_detection
Smoke Detection:
The ROI is converted to HSV color space and thresholds are applied to create a binary mask identifying smoke pixels.

Contour Analysis (if smoke detected):
Contours are found in the smoke mask. If a significant contour exists, it's approximated with a polygon.

Mask Creation:
A transparent mask is created with the chosen boundary color. Another mask is created to fill the smoke contour with white.

Highlighting and Overlay:
The transparent mask's alpha channel is adjusted based on the smoke mask (higher smoke probability = higher transparency). This mask is blended with the ROI for a translucent smoke effect. Finally, the masked ROI is overlaid on the original image.

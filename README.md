# OPENING--AND-CLOSING
## Aim:
To implement Opening and Closing using Python and OpenCV.

## Software Required:
1. Anaconda - Python 3.7
2. OpenCV
## Algorithm:
### Step1:
Import the necessary packages

### Step2:
Give the input text using cv2.putText()

### Step3:
Perform opening operation and display the result

### Step4:
Similarly, perform closing operation and display the result

 
## Program:

``` Python
import cv2
import numpy as np
import matplotlib.pyplot as plt
# Create a blank image
image = np.zeros((500, 500, 3), dtype=np.uint8)

# Add text on the image using cv2.putText
font = cv2.FONT_HERSHEY_SIMPLEX
cv2.putText(image, 'Amruthavarshini', (100, 250), font, 1, (255, 255, 255), 2, cv2.LINE_AA)

# Create a simple square kernel (3x3)
kernel = np.ones((3, 3), np.uint8)

# Display the input image
plt.imshow(cv2.cvtColor(image, cv2.COLOR_BGR2RGB))  # Convert BGR to RGB for displaying
plt.title("Input Image with Text")
plt.axis('off')

# Opening is erosion followed by dilation
opened_image = cv2.morphologyEx(image, cv2.MORPH_OPEN, kernel)

# Display the result of Opening
plt.imshow(cv2.cvtColor(opened_image, cv2.COLOR_BGR2RGB))  # Convert BGR to RGB
plt.title("Opening Operation")
plt.axis('off')

# Closing is dilation followed by erosion
closed_image = cv2.morphologyEx(image, cv2.MORPH_CLOSE, kernel)
plt.imshow(closed_image)
plt.axis("off")
```
## Output:

### Display the input Image

<img width="486" height="503" alt="Screenshot 2025-10-07 161217" src="https://github.com/user-attachments/assets/a979c294-63ba-4621-be5b-4dac386470f1" />


### Display the result of Opening

<img width="484" height="509" alt="Screenshot 2025-10-07 161226" src="https://github.com/user-attachments/assets/02db0f82-3ed8-415a-bdb9-5132bd95bb8a" />

### Display the result of Closing

<img width="488" height="478" alt="Screenshot 2025-10-07 161419" src="https://github.com/user-attachments/assets/d0ba85ec-a9a4-4828-976c-3c95ce08506e" />


## Result:
Thus the Opening and Closing operation is used in the image using python and OpenCV.

# EXP-10-Record-IMPLEMENTATION OF OPENING AND CLOSING
## NAME: RAGASUDHA R
## REG NO: 212224230215

## AIM

To perform morphological opening and closing operations on an image using OpenCV to observe the effects of erosion and dilation.

## PROCEDURE

1.Import the required libraries such as OpenCV, NumPy and Matplotlib.

2.Create a blank image using NumPy.

3.Add text to the image using the cv2.putText() function.

4.Create a 3×3 structuring element (kernel) using NumPy.

5.Display the input image using Matplotlib.

6.Perform the opening operation using erosion followed by dilation with cv2.morphologyEx().

7.Display the opening operation output.

8.Perform the closing operation using dilation followed by erosion.

9.Display the resulting image and observe the effects of both operations.

## CODE
```python
import cv2
import numpy as np
import matplotlib.pyplot as plt
# Create a blank image
image = np.zeros((500, 500, 3), dtype=np.uint8)
# Add text on the image using cv2.putText
font = cv2.FONT_HERSHEY_SIMPLEX
cv2.putText(image, 'RAGASUDHA', (100, 250), font, 1, (255, 255, 255), 2, cv2.LINE_AA)
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
```

## OUTPUT
<img width="902" height="786" alt="image" src="https://github.com/user-attachments/assets/2efcbae2-70e4-4d3c-8959-f257c0b8cbc7" />
<img width="902" height="470" alt="image" src="https://github.com/user-attachments/assets/dbe5f436-b33b-4d0c-abb9-df3e4696abd0" />
<img width="812" height="467" alt="image" src="https://github.com/user-attachments/assets/1581b2ec-4c4d-4c80-b17a-c1e4dfd42e74" />


## RESULT
The morphological opening and closing operations were implemented successfully using OpenCV, and the effects of erosion and dilation on the input image were observed.

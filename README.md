# DIPT-EXP-9-Record-IMPLEMENTATION-OF-EROSION-AND-DILATION

**Name:** VENKATANATHAN P R  
**Register No:** 212223240173

---

## Aim

To write a Python program using OpenCV to perform morphological operations such as **Erosion** and **Dilation** on an image.

The program performs the following operations:

- Image Erosion
- Image Dilation

---

## Software Used

- Anaconda – Python 3.7
- Jupyter Notebook / VS Code
- OpenCV (cv2)
- NumPy
- Matplotlib

---

## Algorithm & Explanation

---

### Step 1: Import Libraries

Import the required libraries such as OpenCV, NumPy, and Matplotlib for image processing, numerical operations, and visualization.

---

### Step 2: Create a Blank Image

Create a blank image of size 500 × 500 pixels with three color channels using NumPy.

---

### Step 3: Insert Text onto the Image

Insert the text **"Hello World"** onto the blank image using OpenCV's text drawing function. The text is displayed in white color with a suitable font and thickness.

---

### Step 4: Display the Original Image

Display the created input image containing the text using Matplotlib. The image is converted from BGR to RGB format before displaying.

---

### Step 5: Create a Structuring Element

Create a 3 × 3 structuring element (kernel) using NumPy. This kernel is used for performing the morphological operations.

---

### Step 6: Image Erosion

Apply the erosion operation to the input image using the created kernel.

Erosion removes pixels from the boundaries of foreground objects, causing the white text to become thinner or smaller.

---

### Step 7: Display the Eroded Image

Display the image after applying the erosion operation using Matplotlib.

---

### Step 8: Image Dilation

Apply the dilation operation to the input image using the same kernel.

Dilation adds pixels to the boundaries of foreground objects, causing the white text to become thicker or larger.

---

### Step 9: Display the Dilated Image

Display the image after applying the dilation operation using Matplotlib.

---

### Step 10: Compare the Images

Compare the input image, eroded image, and dilated image to observe the effects of the two morphological operations.

---

## Program

```python
import cv2
import numpy as np
import matplotlib.pyplot as plt


# Create a blank image
image = np.zeros(
    (500, 500, 3),
    dtype=np.uint8
)


# Add text on the image using cv2.putText
font = cv2.FONT_HERSHEY_SIMPLEX

cv2.putText(
    image,
    'Hello World',
    (100, 250),
    font,
    1,
    (255, 255, 255),
    2,
    cv2.LINE_AA
)


# Display the input image
plt.imshow(
    cv2.cvtColor(
        image,
        cv2.COLOR_BGR2RGB
    )
)

plt.title("Input Image with Text")
plt.axis('off')
plt.show()


# Create a simple square kernel (3x3)
kernel = np.ones(
    (3, 3),
    np.uint8
)


# Apply erosion (shrinking effect)
eroded_image = cv2.erode(
    image,
    kernel,
    iterations=1
)


# Display the eroded image
plt.imshow(
    cv2.cvtColor(
        eroded_image,
        cv2.COLOR_BGR2RGB
    )
)

plt.title("Eroded Image")
plt.axis('off')
plt.show()


# Apply dilation (expanding effect)
dilated_image = cv2.dilate(
    image,
    kernel,
    iterations=1
)


# Display the dilated image
plt.imshow(
    cv2.cvtColor(
        dilated_image,
        cv2.COLOR_BGR2RGB
    )
)

plt.title("Dilated Image")
plt.axis('off')
plt.show()
```

---

## Output

### Original Image

The blank image with the text **"Hello World"** is displayed as the input image.

### Erosion

The erosion operation shrinks the boundaries of the foreground text, making the text thinner.

### Dilation

The dilation operation expands the boundaries of the foreground text, making the text thicker.

---

## Result

Thus, the morphological operations **Erosion** and **Dilation** were successfully implemented using OpenCV. The effects of erosion and dilation were observed by comparing the original image with the eroded and dilated images.

---

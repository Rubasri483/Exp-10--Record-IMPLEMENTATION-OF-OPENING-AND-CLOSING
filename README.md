# EXP. 10 – IMPLEMENTATION OF OPENING AND CLOSING USING OPENCV

## NAME: RUBASRI R 
## REG NO: 212224240139

## Aim

To implement morphological operations such as Opening and Closing using OpenCV and Python to study their effects on an image.

## Software Requirements

- Python
- Anaconda
- Jupyter Notebook
- OpenCV
- NumPy
- Matplotlib

## Morphological Operations

- Opening Operation
- Closing Operation

## Algorithm

1. Import the required libraries: OpenCV, NumPy, and Matplotlib.
2. Create a blank image of size 500 × 500 with three colour channels.
3. Add the text "Open and Close" to the image using `cv2.putText()`.
4. Create a 3 × 3 square kernel using `np.ones()`.
5. Display the original input image.
6. Apply the Opening operation using `cv2.morphologyEx()` with `cv2.MORPH_OPEN`.
7. Display the result of the Opening operation.
8. Apply the Closing operation using `cv2.morphologyEx()` with `cv2.MORPH_CLOSE`.
9. Display the result of the Closing operation.

## Implementation

### 1. Import Libraries

```python
import cv2
import numpy as np
import matplotlib.pyplot as plt
```

### 2. Create a Blank Image

```python
image = np.zeros((500, 500, 3), dtype=np.uint8)
```

### 3. Add Text on the Image

```python
font = cv2.FONT_HERSHEY_SIMPLEX

cv2.putText(
    image,
    'Open and Close',
    (100, 250),
    font,
    1,
    (255, 255, 255),
    2,
    cv2.LINE_AA
)
```

### 4. Create a Kernel

```python
kernel = np.ones((3, 3), np.uint8)
```

### 5. Display the Input Image

```python
plt.imshow(cv2.cvtColor(image, cv2.COLOR_BGR2RGB))
plt.title("Input Image with Text")
plt.axis('off')
```

**OUTPUT:**

<img width="528" height="429" alt="image" src="https://github.com/user-attachments/assets/0eda9901-6019-4b07-9e87-d8c175d0db1b" />

### 6. Apply Opening Operation

Opening is the morphological operation performed by applying Erosion followed by Dilation.

```python
opened_image = cv2.morphologyEx(
    image,
    cv2.MORPH_OPEN,
    kernel
)

plt.imshow(cv2.cvtColor(opened_image, cv2.COLOR_BGR2RGB))
plt.title("Opening Operation")
plt.axis('off')
```

**OUTPUT:**

<img width="462" height="413" alt="image" src="https://github.com/user-attachments/assets/dc8fd833-5b9c-4402-96d2-9c5f0079cd41" />


### 7. Apply Closing Operation

Closing is the morphological operation performed by applying Dilation followed by Erosion.

```python
closed_image = cv2.morphologyEx(
    image,
    cv2.MORPH_CLOSE,
    kernel
)

plt.imshow(cv2.cvtColor(closed_image, cv2.COLOR_BGR2RGB))
plt.title("Closing Operation")
plt.axis('off')
```

**OUTPUT:**

<img width="457" height="419" alt="image" src="https://github.com/user-attachments/assets/b22360fb-e67b-4ff3-9b9c-509fa89be920" />

## Result

Thus, the morphological operations Opening and Closing were successfully implemented using OpenCV and Python. Opening performs Erosion followed by Dilation, whereas Closing performs Dilation followed by Erosion.

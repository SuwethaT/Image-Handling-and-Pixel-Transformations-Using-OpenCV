# Image-Handling-and-Pixel-Transformations-Using-OpenCV 

## AIM:
Write a Python program using OpenCV that performs the following tasks:

1) Read and Display an Image.  
2) Adjust the brightness of an image.  
3) Modify the image contrast.  
4) Generate a third image using bitwise operations.

## Software Required:
- Anaconda - Python 3.7
- Jupyter Notebook (for interactive development and execution)

## Algorithm:
### Step 1:
Load an image from your local directory and display it.

### Step 2:
Create a matrix of ones (with data type float64) to adjust brightness.

### Step 3:
Create brighter and darker images by adding and subtracting the matrix from the original image.  
Display the original, brighter, and darker images.

### Step 4:
Modify the image contrast by creating two higher contrast images using scaling factors of 1.1 and 1.2 (without overflow fix).  
Display the original, lower contrast, and higher contrast images.

### Step 5:
Split the image (boy.jpg) into B, G, R components and display the channels

## Program Developed By:
- **Name: Suwetha T
- **Register Number: 212225040446

### Ex. No. 01

---Program---
Step 1 : Read and display the image 
---
import cv2

import matplotlib.pyplot as plt

img=cv2.imread('suwe3.webp',cv2.IMREAD_COLOR)

img_rgb=cv2.cvtColor(img,cv2.COLOR_BGR2RGB)

plt.imshow(img_rgb,cmap='viridis')

plt.title("Original Image")

plt.axis('off')

plt.show()
---
Step 2 : Image with line 
---
import cv2

import matplotlib.pyplot as plt

img = cv2.imread('suwe3.webp')

img_rgb = cv2.cvtColor(img, cv2.COLOR_BGR2RGB)

h, w = img_rgb.shape[:2]

line_img = cv2.line(img_rgb, (0, 0), (w-1, h-1), (255, 0, 0), 2)

plt.imshow(line_img)

plt.title("Image with line")

plt.axis('off')

plt.show()
---
Step 3 : Image with line form left side
---
import cv2

import matplotlib.pyplot as plt

img = cv2.imread('suwe3.webp')

img_rgb = cv2.cvtColor(img, cv2.COLOR_BGR2RGB)

h, w = img_rgb.shape[:2]

line_img = cv2.line(img_rgb, (w-1, 0), (0, h-1), (255, 0, 0), 2)

plt.imshow(line_img)

plt.title("Image with line")

plt.axis('off')

plt.show()
---
Step 4 : Image with rectangle
---
import cv2

import matplotlib.pyplot as plt

img = cv2.imread('suwe3.webp')

img_rgb = cv2.cvtColor(img, cv2.COLOR_BGR2RGB)

h, w = img_rgb.shape[:2]

rect_img = cv2.rectangle(img_rgb, 
                         (w//4, h//4),
                         (3*w//4, 3*h//4),
                         (255, 0, 0), 2)

plt.imshow(rect_img)

plt.title("Image with Rectangle")

plt.axis('off')

plt.show()
---
Step 5 : Image with text
---
import cv2

import matplotlib.pyplot as plt

img = cv2.imread('suwe3.webp')

img_rgb = cv2.cvtColor(img, cv2.COLOR_BGR2RGB)

text_img = cv2.putText(img_rgb, "My Beautiful Picture",
                       (50, 100),
                       cv2.FONT_HERSHEY_SIMPLEX,
                       1, (255, 0, 0), 2)

plt.imshow(text_img)

plt.title("Image with Text")

plt.axis('off')

plt.show()
---
Step 6 : HSV Image
---
import cv2

import matplotlib.pyplot as plt

img = cv2.imread('suwe3.webp')

img_rgb = cv2.cvtColor(img, cv2.COLOR_BGR2RGB)

img_hsv = cv2.cvtColor(img_rgb, cv2.COLOR_RGB2HSV)

plt.imshow(img_hsv)

plt.title("HSV Image")

plt.axis('off')

plt.show()
---
Step 7 : Grayscale Image
---
import cv2

import matplotlib.pyplot as plt

img = cv2.imread('suwe3.webp')

img_rgb = cv2.cvtColor(img, cv2.COLOR_BGR2RGB)

img_hsv = cv2.cvtColor(img_rgb, cv2.COLOR_RGB2HSV)

img_gray = cv2.cvtColor(
    cv2.cvtColor(img_hsv, cv2.COLOR_HSV2RGB),
    cv2.COLOR_RGB2GRAY
)

plt.imshow(img_gray, cmap='gray')

plt.title("Grayscale Image")

plt.axis('off')

plt.show()
---
Step 8 : Modified Image
---
import cv2

import matplotlib.pyplot as plt

img = cv2.imread('suwe3.webp')

img_rgb = cv2.cvtColor(img, cv2.COLOR_BGR2RGB)

img_rgb[200:500, 200:500] = [255, 255, 255]

plt.imshow(img_rgb)

plt.title("Modified Image")

plt.axis('off')

plt.show()
---
Step 9 : Resized Image
---
import cv2

import matplotlib.pyplot as plt

img = cv2.imread('suwe3.webp')

img_rgb = cv2.cvtColor(img, cv2.COLOR_BGR2RGB)

resized_img = cv2.resize(img_rgb, None, fx=0.5, fy=0.5)

plt.imshow(resized_img)

plt.title("Resized Image")

plt.axis('off')

plt.show()
---
Step 10 : Cropped Image
---
import cv2

import matplotlib.pyplot as plt

img = cv2.imread('suwe3.webp')

img_rgb = cv2.cvtColor(img, cv2.COLOR_BGR2RGB)

cropped_img = img_rgb[50:150, 50:150]

plt.imshow(cropped_img)

plt.title("Cropped Image")

plt.axis('off')

plt.show()
---
Step 11 : Horizontal Flipped Image 
---
import cv2

import matplotlib.pyplot as plt

img = cv2.imread('suwe3.webp')

img_rgb = cv2.cvtColor(img, cv2.COLOR_BGR2RGB)

flipped_img = cv2.flip(img_rgb, 1)

plt.imshow(flipped_img)

plt.title("Horizontally Flipped Image")

plt.axis('off')

plt.show()
---
Step 12 : Vertically Flipped Image
---
import cv2

import matplotlib.pyplot as plt

img = cv2.imread('suwe3.webp')

img_rgb = cv2.cvtColor(img, cv2.COLOR_BGR2RGB)

flipped_img = cv2.flip(img_rgb, 0)

plt.imshow(flipped_img)

plt.title("Vertically Flipped Image")

plt.axis('off')

plt.show()
---


## Output:
---
#1. Original image displayed using OpenCV and Matplotlib.

<img width="676" height="573" alt="image" src="https://github.com/user-attachments/assets/30f8d4f5-529c-41c6-9c7c-256c4781d62a" />

#2. Image with a line drawn from the top-left to the bottom-right.

<img width="695" height="562" alt="image" src="https://github.com/user-attachments/assets/431281df-a052-47ee-9954-dc17aba778ae" />

#3. Image with a line drawn from the bottom-right to the top-left.

<img width="650" height="562" alt="image" src="https://github.com/user-attachments/assets/a96dd48b-3f9d-4da7-af21-916a549cbf61" />

#4. Image with Rectangle.

<img width="607" height="567" alt="image" src="https://github.com/user-attachments/assets/c69f2d73-4681-4055-8378-04f9433d779b" />

#5. Image with text.

<img width="587" height="560" alt="image" src="https://github.com/user-attachments/assets/54dfbcb3-d67e-4187-aa3f-e256f62368e8" />

#6. HSV Image.

<img width="607" height="557" alt="image" src="https://github.com/user-attachments/assets/4b573bcb-e22e-49eb-9db5-15e3d69b6cad" />

#7. Grayscale Image.

<img width="628" height="566" alt="image" src="https://github.com/user-attachments/assets/10ac17fd-f271-4245-be6a-9f0714fd410f" />

#8. Modified Image.

<img width="642" height="587" alt="image" src="https://github.com/user-attachments/assets/2f18b69b-1777-4884-8d6b-f8160c986354" />

#9. Resized Image.

<img width="637" height="557" alt="image" src="https://github.com/user-attachments/assets/d59c4f44-6c9e-4962-ba3a-3f190b48526b" />

#10. Cropped Image.

<img width="622" height="570" alt="image" src="https://github.com/user-attachments/assets/515168ce-7f49-45ca-894a-e8cdcf28d0d0" />

#11. Horixontal Flipped Image.

<img width="635" height="557" alt="image" src="https://github.com/user-attachments/assets/6cab5248-3108-4ab9-916f-5da2f6bf45bd" />

#12. Vertically Flipped Image.

<img width="657" height="560" alt="image" src="https://github.com/user-attachments/assets/210f3c9e-bc34-4bca-a1a5-a41c0800964e" />

---

## Result:
Thus, the images were read, displayed, brightness and contrast adjustments were made, and bitwise operations were performed successfully using the Python program.


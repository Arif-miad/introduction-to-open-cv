# introduction-to-open-cv
Computer vision is a field of study focused on enabling computers to interpret and understand the visual world. OpenCV provides a comprehensive set of tools and algorithms for various tasks in computer vision, including image and video processing, object detection and tracking, facial recognition, augmented reality
```
python

import numpy as np
import cv2
import matplotlib.pyplot as plt
image_path = "/kaggle/input/introduction-to-open-computer-vesion/Image.png"
image = cv2.imread(image_path, cv2.IMREAD_GRAYSCALE)
blur = cv2.GaussianBlur(image, (5,5),0)
edge = cv2.Canny(blur, 100, 200)
contours, hierarchy = cv2.findContours(edge, cv2.RETR_EXTERNAL, cv2.CHAIN_APPROX_SIMPLE)
contour_image = cv2.cvtColor(image, cv2.COLOR_GRAY2BGR)
cv2.drawContours(contour_image, contours, -1, (0, 255, 0), 3)


plt.figure(figsize = (10, 12))


plt.subplot(1, 3, 1)
plt.imshow(image, cmap = "gray")
plt.title("Orginal Image")
plt.axis("off")


plt.subplot(1, 3, 2)
plt.imshow(edge, cmap = "gray")
plt.title("Edge Image")
plt.axis("off")


plt.subplot(1, 3, 3)
plt.imshow(contour_image)
plt.title("Contours")
plt.axis("off")


plt.show()```


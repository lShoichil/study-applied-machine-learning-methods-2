датасет:
https://universe.roboflow.com/dogbreeds/dog-breeds-142de

```
result1[0].boxes

xywh = result1[0].boxes.xywh
xywhn = result1[0].boxes.xywhn
xyxy = result1[0].boxes.xyxy
xyxyn = result1[0].boxes.xyxyn
xywh, xywhn, xyxy, xyxyn

import matplotlib.pyplot as plt
import matplotlib.patches as patches
import imageio

image_path = (f"test/miniature-pinscher.jpg")
image = imageio.imread(image_path)
fig, ax = plt.subplots(1)

ax.imshow(image)
for x_center, y_center, width, height in result2[0].boxes.xywhn.cpu():
    x = x_center - width / 2
    y = y_center - height / 2
    rect = patches.Rectangle((x * image.shape[1], y * image.shape[0]), width * image.shape[1], height * image.shape[0], linewidth=1, edgecolor='r', facecolor='none')
    ax.add_patch(rect)
plt.show()

```

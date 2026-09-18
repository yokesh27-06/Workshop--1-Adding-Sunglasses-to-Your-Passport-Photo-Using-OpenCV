# DIPT-WORKSHOP-1
## Adding Sunglasses to Your Passport Photo Using OpenCV
## Name : Yokesh H
## Reg.no : 21224230312
```
# Import libraries
import cv2
import numpy as np
import matplotlib.pyplot as plt
# Load the Face Image
faceImage = cv2.imread("photo .png")
plt.imshow(cv2.cvtColor(faceImage, cv2.COLOR_BGR2RGB))
plt.title("Face")
plt.axis("off")
# Load the Sunglass image with Alpha channel
glassPNG = cv2.imread("sunglass.jpeg", cv2.IMREAD_UNCHANGED)
plt.imshow(cv2.cvtColor(glassPNG, cv2.COLOR_BGRA2RGBA))
plt.title("glassPNG")
plt.axis("off")
# Resize the sunglass to fit the face
# Tuned for the uploaded image
glassPNG = cv2.resize(glassPNG, (170, 63), interpolation=cv2.INTER_AREA)
print(glassPNG.shape)
# Separate the Color and alpha channels
glassBGR = glassPNG[:,:,0:3]
glassMask1 = glassPNG[:,:,2]
glassBGR.shape
# Display the images for clarity
plt.figure(figsize=[15,15])
plt.subplot(121);plt.imshow(glassBGR[:,:,::-1]);plt.title('Sunglass Color channels');
plt.subplot(122);plt.imshow(glassMask1,cmap='gray');plt.title('Sunglass Alpha channel');
# Make a copy
#faceWithGlassesNaive = resized_faceImage.copy()
faceWithGlassesNaive = faceImage.copy()

# Replace the eye region with the sunglass image
faceWithGlassesNaive[750:1000,480:1250]=glassBGR

plt.imshow(faceWithGlassesNaive[...,::-1])
glassBGR.shape
```


<img width="273" height="409" alt="download" src="https://github.com/user-attachments/assets/5f0e5b89-0afd-4c93-9b30-b40208521166" />
<img width="515" height="256" alt="download" src="https://github.com/user-attachments/assets/d05c8f10-8d9a-4470-b720-b2503d5db05f" />
<img width="1345" height="276" alt="image" src="https://github.com/user-attachments/assets/c7fddba9-b24f-4ceb-9e73-a68db192ed86" />
<img width="319" height="418" alt="download" src="https://github.com/user-attachments/assets/f45c2084-9072-48a0-a705-95c70cbb0e77" />

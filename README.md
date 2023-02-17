# Barcode-Scanner

The project aims at detecting the barcodes in a given image.This scanner doesn't use any pre trained model as such. All the tasks are done using OpenCV and the pyzbar library.
The dataset included 13 images.There were 6 tasks to be accomplished.Tasks 1,2,3 have been done in the same file.All the other tasks have a seperate file.The bulk code involves Image Preprocessing and is the same in all the tasks. The only difference was
the Region of Interest (ROI) for each task.

## Description

Image Preprocessing involves 4 steps:
- Converting each image from RGB to Gray and smoothening the pixels with different intensities by 'MedianBlur' function.
- Removing the shadows in the image by dilating the image.
- Trying to Filter out noise in the image by Area Thresholding. We tried multiple thresholds and by Hit And Trial 10000 pixels was the set value.
- Seperated each object in the filtered image by getting the boundaries.

After seperating each object we used the Pyzbar library to detect the barcodes codes and drew the approriate bounding Rectangles.

## Key Inference

- The model works well if the objects in the image are at a certain distance and there is a monochromatic background with no shadows.
- For some reason the library also detects QR codes.
- If the barcode is partially visible but not readable the library fails to recognize it as a barcode and thus,we couldn't differentiate between images with no barcodes and partially visible barcodes.

To seperate the partially visible barcodes, we tried to get a template of the barcode and find similar objects in the image but that didn't give results.
We could use pre trained models like Tiny Yolo to improve our accuracy.

The images are taken from :
https://drive.google.com/drive/folders/1ONhcr1Z5_UuRmnkKu4xx4KFzIeJBMhnW?usp=sharing

Results of all tasks can be seen at: https://drive.google.com/drive/folders/1-ebLiRuUv44ytmXfHzTn3Y2Q6od6x-T4?usp=share_link







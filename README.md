# COLOR_CONVERSIONS_OF-IMAGE
## AIM
Write a Python program using OpenCV that performs the following tasks:

i) Read and Display an Image.

ii) 	Draw Shapes and Add Text.

iii) Image Color Conversion.

iv) Access and Manipulate Image Pixels.

v) Image Resizing

vi) Image Cropping

vii) Image Flipping

viii)	Write and Save the Modified Image


## Software Required:
Anaconda - Python 3.7
## Algorithm:
### Step1:
Load an image from your local directory and display it.
### Step2:
o	Draw a line from the top-left to the bottom-right of the image.
o	Draw a circle at the center of the image.
o	Draw a rectangle around a specific region of interest in the image.
o	Add the text "OpenCV Drawing" at the top-left corner of the image.

### Step3:
o	Convert the image from RGB to HSV and display it.
o	Convert the image from RGB to GRAY and display it.
o	Convert the image from RGB to YCrCb and display it.
o	Convert the HSV image back to RGB and display it.

### Step4:
o	Access and print the value of the pixel at coordinates (100, 100).
o	Modify the color of the pixel at (200, 200) to white.

### Step5:
o	Resize the original image to half its size and display it.
### Step6:
o	Crop a region of interest (ROI) from the image (e.g., a 100x100 pixel area starting at (50, 50)) and display it.
### Step7:
o	Flip the original image horizontally and display it.
o	Flip the original image vertically and display it.

### Step8:
o	Save the final modified image to your local directory.


##### Program:
### Developed By: RIYA P L
### Register Number: 212223240141

### i)Read and Display an Image
```
# Step 1: Load an image from your local directory and display it
import cv2
image_path = 'puppies.jpg'  # Replace with your image path
image = cv2.imread(image_path)

# Check if the image was loaded successfully
if image is None:
    print("Error: Could not read the image.")
else:
    cv2.imshow('Original Image', image)
    cv2.waitKey(0)
```
### OUTPUT:
!<img width="298" alt="Screenshot 2024-09-10 at 11 56 41 AM" src="https://github.com/user-attachments/assets/431316f7-e3f0-4c4b-8e6a-9dcd9b802191">



### ii)Draw Shapes and Add Text
```
# Step 2: Draw Shapes and Add Text
# Draw a line from the top-left to the bottom-right
start_point = (0, 0)
end_point = (image.shape[1], image.shape[0])
line_color = (255, 0, 0)  # Blue color in BGR
thickness = 2
image_with_line = cv2.line(image.copy(), start_point, end_point, line_color, thickness)

# Draw a circle at the center of the image
center_coordinates = (image.shape[1] // 2, image.shape[0] // 2)
radius = 50
circle_color = (0, 255, 0)  # Green color in BGR
thickness = 3
image_with_circle = cv2.circle(image_with_line, center_coordinates, radius, circle_color, thickness)

# Draw a rectangle around a specific region of interest
top_left = (50, 50)
bottom_right = (200, 200)
rectangle_color = (0, 0, 255)  # Red color in BGR
thickness = 2
image_with_rectangle = cv2.rectangle(image_with_circle, top_left, bottom_right, rectangle_color, thickness)

# Add text to the image
text = "OpenCV Drawing"
org = (10, 30)  # top-left corner of the text string
font = cv2.FONT_HERSHEY_SIMPLEX
font_scale = 1
text_color = (255, 255, 255)  # White color
thickness = 2
image_with_text = cv2.putText(image_with_rectangle, text, org, font, font_scale, text_color, thickness, cv2.LINE_AA)

cv2.imshow('Image with Shapes and Text', image_with_text)
cv2.waitKey(0)
```
### OUTPUT:
<img width="298" alt="Screenshot 2024-09-10 at 11 56 41 AM" src="https://github.com/user-attachments/assets/f62e4c92-72bf-413b-8fbf-07b474eb616a">

### iii)Image Color Conversion
```
# Step 3: Image Color Conversion
# Convert the image from RGB to HSV and display it
hsv_image = cv2.cvtColor(image, cv2.COLOR_BGR2HSV)
cv2.imshow('HSV Image', hsv_image)
cv2.waitKey(0)

# Convert the image from RGB to GRAY and display it
gray_image = cv2.cvtColor(image, cv2.COLOR_BGR2GRAY)
cv2.imshow('Gray Image', gray_image)
cv2.waitKey(0)

# Convert the image from RGB to YCrCb and display it
ycrcb_image = cv2.cvtColor(image, cv2.COLOR_BGR2YCrCb)
cv2.imshow('YCrCb Image', ycrcb_image)
cv2.waitKey(0)

# Convert the HSV image back to RGB and display it
hsv_to_rgb_image = cv2.cvtColor(hsv_image, cv2.COLOR_HSV2BGR)
cv2.imshow('HSV to RGB Image', hsv_to_rgb_image)
cv2.waitKey(0)
```
### OUTPUT:
<img width="734" alt="Screenshot 2024-09-11 at 8 41 38 AM" src="https://github.com/user-attachments/assets/fd06a38f-2e0d-4a5f-9864-29ac6d249f72">


### iv)Access and Manipulate Image Pixels
```
# Step 4: Access and Manipulate Image Pixels
# Access and print the value of the pixel at coordinates (100, 100)
pixel_value = image[100, 100]
print(f"Pixel value at (100, 100): {pixel_value}")

# Modify the color of the pixel at (200, 200) to white
image[200, 200] = [255, 255, 255]
print(f"Modified pixel value at (200, 200): {image[200, 200]}")
```
### OUTPUT:
<img width="374" alt="Screenshot 2024-09-11 at 8 44 51 AM" src="https://github.com/user-attachments/assets/360695ba-8267-4ea1-938f-1939fe8d7b67">

### v)Image Resizing
```
# Step 5: Image Resizing
# Resize the original image to half its size and display it
resized_image = cv2.resize(image, (image.shape[1] // 2, image.shape[0] // 2))
cv2.imshow('Resized Image', resized_image)
cv2.waitKey(0)
```
### OUTPUT:
<img width="374" alt="Screenshot 2024-09-11 at 8 44 51 AM" src="https://github.com/user-attachments/assets/c380564d-4e9d-471c-80d7-a9442c059f79">

### vi)Image Cropping
```
# Step 6: Image Cropping
# Crop a region of interest (100x100 pixels starting at (50, 50)) and display it
roi = image[50:150, 50:150]
cv2.imshow('Cropped ROI Image', roi)
cv2.waitKey(0)
```
### OUTPUT:
<img width="374" alt="Screenshot 2024-09-10 at 1 17 49 PM" src="https://github.com/user-attachments/assets/1fc7af26-6094-41d0-aa39-60a39d5988cf">

### vii)Image Flipping
```
# Step 7: Image Flipping
# Flip the original image horizontally and display it
flipped_horizontally = cv2.flip(image, 1)
cv2.imshow('Horizontally Flipped Image', flipped_horizontally)
cv2.waitKey(0)

# Flip the original image vertically and display it
flipped_vertically = cv2.flip(image, 0)
cv2.imshow('Vertically Flipped Image', flipped_vertically)
cv2.waitKey(0)
```
### OUTPUT:
# Flip the original image horizontally Flip the original image vertically and display it:
<img width="865" alt="Screenshot 2024-09-11 at 8 42 07 AM" src="https://github.com/user-attachments/assets/be752998-9032-4505-9f7b-0e3c7a2118e0">


### viii)Write and Save the Modified Image
```
# Step 8: Write and Save the Modified Image
output_path = 'output.jpg'
cv2.imwrite(output_path, image_with_text)
print(f"Modified image saved as {output_path}")
```
### OUTPUT:
<img width="338" alt="Screenshot 2024-09-11 at 8 47 32 AM" src="https://github.com/user-attachments/assets/c12f00af-a396-4040-a9a1-07629c00942f">

## Result:
Thus the images are read, displayed, and written ,and color conversion was performed  successfully using the python program.








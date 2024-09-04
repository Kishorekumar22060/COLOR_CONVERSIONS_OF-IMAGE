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
![Screenshot 2024-09-02 185344](https://github.com/user-attachments/assets/41822fc8-c64d-4770-b164-e52bb3cc1020)


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
![Screenshot 2024-09-02 185558](https://github.com/user-attachments/assets/79eaae9f-10b9-49cf-96ed-da1752ec7d30)

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
# Convert the image from RGB to HSV and display it:
![Screenshot 2024-09-02 185803](https://github.com/user-attachments/assets/48c5f665-777b-40a9-82df-6b37b064e0aa)
# Convert the image from RGB to GRAY and display it:
![Screenshot 2024-09-02 185815](https://github.com/user-attachments/assets/e36f7c2a-792d-485c-a914-6ba5cccca766)
# Convert the image from RGB to YCrCb and display it:
![Screenshot 2024-09-02 185829](https://github.com/user-attachments/assets/37299544-b9cb-42f7-a1dd-3db4a036ec82)
# Convert the HSV image back to RGB and display it:
![Screenshot 2024-09-02 185842](https://github.com/user-attachments/assets/48f7e3a1-6bfc-4f31-b0e2-3e804382577a)

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
![Screenshot 2024-09-02 185925](https://github.com/user-attachments/assets/d4d3a1af-ce4d-4e88-b8f7-c039af5c5a48)

### v)Image Resizing
```
# Step 5: Image Resizing
# Resize the original image to half its size and display it
resized_image = cv2.resize(image, (image.shape[1] // 2, image.shape[0] // 2))
cv2.imshow('Resized Image', resized_image)
cv2.waitKey(0)
```
### OUTPUT:
![Screenshot 2024-09-02 185954](https://github.com/user-attachments/assets/a67981d6-3d51-45f5-b78b-a2e6ae6d60fb)

### vi)Image Cropping
```
# Step 6: Image Cropping
# Crop a region of interest (100x100 pixels starting at (50, 50)) and display it
roi = image[50:150, 50:150]
cv2.imshow('Cropped ROI Image', roi)
cv2.waitKey(0)
```
### OUTPUT:
![Screenshot 2024-09-02 190028](https://github.com/user-attachments/assets/c6d28613-bc43-491c-9988-ecb37a5ede6f)

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
# Flip the original image horizontally and display it:
![Screenshot 2024-09-02 190207](https://github.com/user-attachments/assets/c4b04f13-26cb-4a0f-a6c8-26082ec6ad06)
# Flip the original image vertically and display it:
![Screenshot 2024-09-02 190235](https://github.com/user-attachments/assets/c8f4229f-9546-4b2b-8b8a-75cfb618917d)

### viii)Write and Save the Modified Image
```
# Step 8: Write and Save the Modified Image
output_path = 'output.jpg'
cv2.imwrite(output_path, image_with_text)
print(f"Modified image saved as {output_path}")
```
### OUTPUT:
![Screenshot 2024-09-02 191531](https://github.com/user-attachments/assets/e2ea95d3-5d7e-407e-8b45-a6b86eca3ceb)

## Result:
Thus the images are read, displayed, and written ,and color conversion was performed  successfully using the python program.








# Teeth-Detection-MediaPipe
 This repository contains code for a teeth detection project using MediaPipe Face Mesh. The code utilizes facial landmark detection to determine whether the teeth are visible in images. It includes functions for image resizing, tooth detection, and supports image inputs from either a local folder or URLs.
The code allows users to input a folder containing different images or image URLs. The program downloads the images from the provided URLs (if applicable) and determines whether the teeth are visible in each image.

Code Explanation
The code consists of two main parts: functions and the main program.

Functions
The code includes the following functions:

get_unique(c): This function takes a list c of tuples and returns a list of unique indices found in the tuples.
resize_and_show(image): This function resizes the input image to the desired height and width.
tooth_detector(image): This function uses MediaPipe Face Mesh to detect the landmarks on the lips and determines whether the teeth are visible in the image. It calculates the distances between the upper lip, lower lip, and the gap between them. If the gap is larger than the combined lengths of the lips, it considers the teeth to be visible and returns "True"; otherwise, it returns "False".


Main Program
The main program performs the following steps:

Defines the desired height and width for resizing the images.
Defines a list of image files or URLs in the variable image_files.
Creates an images dictionary, where the keys are the image names and the values are the corresponding images read using OpenCV.

If the image name starts with "http", it downloads the image from the URL using urllib.request.urlopen and decodes it using OpenCV's imdecode function. The downloaded image is then resized to the desired dimensions.If the image name does not start with "http", it resizes the image to the desired dimensions using the resize_and_show function.

Calls the tooth_detector function to determine whether the teeth are visible in the image.

Appends the result ("True" or "False") to the outcome list.
Prints the outcome list, which contains the results for each image.

Usage
Make sure you have installed the required dependencies mentioned in the "Requirements" section.
Clone this repository or download the code files.
Modify the image_files variable in the code to include the image URLs or paths to your images.
Run the code using the Python interpreter.

The program will output a list (outcome) indicating whether the teeth are visible in each image. The result "True" means the teeth are visible, while "False" means the teeth are not visible.


Limitations
The accuracy of tooth detection depends on the quality of the images and the performance of MediaPipe Face Mesh.
The code assumes that the teeth are visible when the gap between the upper and lower lips is larger than the combined lengths of the lips. This may not be accurate in all cases.
The program is designed to work with individual

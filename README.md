# Computer-Vision
Computer Vision: Algorithms and Applications

+ 2D Computer Graphics: How to draw images
+ Image Processing: How to deal with images


## Handcrafted Visual Features
This is an algorithm to extract valid information from pictures.
It is difficult to extract meaningful information with color information of RGB.
Instead this, we usually use HSV color space or CIE Luv.

### Color histograms
It is hard to tell if each pixel of the image is the same person or not.
This is just a way of expressing the proportion of colors.
In each color patch, the proportion that the color comprises does not change even if deformation occurs.

**How to run**
1. Get average color value per pixel from image.
2. Use the color corresponding to each hue as bin.
3. We need to make quantization of hue because it lacks information to put 18 colors in 360.
Here, divide hue into four parts and form a 4-bin histogram.
4. The average color of each pixel corresponds to one hue.
5. Continue to stack the hue corresponding to each color.
Then color histograms are complete.

**How to calculate if color histograms are similar between two pictures**
![Metric](https://user-images.githubusercontent.com/88317168/128590354-dbb5db7b-f1c3-463c-8a52-0360454bb577.png)
If the difference between the two images is large, then the calculation result will be large.
And if the difference is small, then the result will be small.
The resulting value will always be a number between 0 and 1.
(0: Different, 1: Same)

### Histogram of Oriented Gradients (HOG)
Extract the gradient from the image becuase we will examine similarities in form between two pictures. Especially, it shows strength in the field of Person Detection. It creates a histogram corresponding to each grid from image.

**How to run**
1. Normalize gamma & colour: Convert to color space well-aware the contour and obtain edges.
2. Compute gradients: Calculate gradients ignoring brightness, color information etc.
3. Weighted vote into spatial & orientation cells: Divide image into pixel 'cells' and gather information about gradients.
4. Contrast normalize over overlapping spatial blocks: Add all the histogram information contained in each block.

### Code Execution (Image Retrieval)
Using the code, find and run two data samples with good **Color histograms** and **Histogram of Oriented Gradients** functioning respectively.

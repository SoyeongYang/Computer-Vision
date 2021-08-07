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

**How to calculate whether color histogras are similar between two pictures**

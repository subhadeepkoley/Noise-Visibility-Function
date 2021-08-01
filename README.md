# Noise-Visibility-Function

NVF.M Generate Noise Visibility Map of an image

NVFIMAGE = NVF(IMAGE, WINDOW, D) Generates the noise visibility

functionmap NVFIMAGE of the input IMAGE with the user provided WINDOW

and D. WINDOW represents the standard deviation calculation window and

D represents an experimentally determined constant. IMAGE is a RGB

color or a grayscale image. NVFImage is a matrix having the same height

and width as of the input image. WINDOW must be an integer preferbly

less than 7. D must be an integer in the range of [50, 100].

Class support
-------------
Supported classes for IMAGE are single, double, uint8, uint16, uint32,
uint64, int8, int16, int32, int64. These must be real and non-sparse.
Supported classes for output NVFimage are single and double.

Notes
-----
[1] Window size greater than 7 will generate inaccurate, over
smoothened result.

[2] D value must lie between [50, 100].

[3] output NVF image range lies between [0, 1]. Where 0 represents
areas with low noise visibility and vice-versa.

[4] Default value of window is 3

[5] Default value of D is 75

Example 1
---------
% Compute NVF image of a grayscale image with default parameters

%Read the image

img = imread('cameraman.tif');

% Compute NVF image

NVFimg = nvfV2(img);

% Display the results

figure

montage({img, NVFimg})

title('Original image (left) and NVF image (right)')

Example 2
---------
% Compute NVF image of a RGB color image with custom parameters

% Read the image

img = imread('peppers.png');

% Compute NVF image

sdWindow = 5;

D = 50;

NVFimg = nvfV2(img, sdWindow, D);

%Display the results
 
figure

montage({img, NVFimg})

title('Original image (left) and NVF image (right)')


Reference
---------
Efstratiadis, S.N. and Katsaggelos, A.K., "Adaptive iterative image
restoration with reduced computational load," Optical engineering,
29(12), pp.1458-1469, 1990.

Written by: Subhadeep Koley

CC BY-NC-ND license 2021

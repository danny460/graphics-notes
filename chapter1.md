
---
## Camera Rays
Producing ray traced images requires looping through each pixel and generating corresponding **camera rays**. In ray generation we calculate the **direction of rays** form the **camera origin** to the pixel. This involves converting pixel coordination from **raster space** to **world space**.

> By convention image frame is one unit away from camera origin. The camera orients to the negative z-axis or negative y-axis.
 
####Converting from raster space to world space
 **1. Raster Space to NDC Space**
 
######Raster Space:
>Uses **raster coordinate system**, where the x-axis points to the right (when world space's x-axis points to the right) and y-axis points downwards. 

<br>

>The origin situated at the top-left. A pixel in this coordinate system, is one unit long in x and y.     

######NDC Space (Normalised Device Coordinate Space):

>The NDC coordinate system's origin is situated in the lower-left corner of the canvas.

<br>

>the coordinates of the pixels are now **in the range [0,1]**,

 **2. NDC Space to Screen Space**
 
 //
  
 **3. Screen Space to World Space**
 
 //




#Ray Tracing Fundamentals

---
## Camera Rays
Producing ray traced images requires looping through each pixel and generating corresponding **camera rays**. In ray generation we calculate the **direction of rays** form the **camera origin** to the pixel. This involves converting pixel coordination from **raster space** to **world space**.

> By convention image frame is one unit away from camera origin
 
####Converting from raster space to world space
 **1. Raster Space to NDC Space**
 
> **Raster Space : **

>> Uses **raster coordinate system**, where the x-axis points to the right (when world space's x-axis points to the right) and y-axis points downwards. <br>
A pixel in this coordinate system, is one unit long in x and y.     

<br>
<br>


> **NDC Space:**

 **2. NDC Space to Screen Space**
 
 //
  
 **3. Screen Space to World Space**
 
 //




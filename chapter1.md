#Ray Tracing Fundamentals

---
## Camera Rays
Producing ray traced images requires looping through each pixel and generating corresponding **camera rays**. The challenge in ray generation is to calculate the **direction of rays** based on the pixel coordination and the **origin**. This involves converting pixel coordination from **raster space** to **world space**.

> By convention image frame is one unit away from camera origin
> 

- screen space


## Generating Camera Rays
To produce ray traced images, we loop through each pixel and generate the **camera ray**. We need to calculate the **direction of rays** form the **camera origin** to the pixel. This section is on the techniques of converting pixel coordination from **raster space** to **world space**.

######Note
> By convention, the image frame is one unit away from camera origin. The camera orients to the negative z-axis or negative y-axis.

 
---
####Converting from Raster Space to World Space
 **1. Raster Space to NDC Space**
 
$$PixelNDC_x = \dfrac{(Pixel_x + 0.5)}{ImageWidth},\\

PixelNDC_y = \dfrac{(Pixel_y + 0.5)}{ImageHeight}.$$
 
 **2. NDC Space to Screen Space**
 
 $$PixelScreen_x = 2 * {PixelNDC_x} - 1,\\
 PixelScreen_y = 1 - 2 * {PixelNDC_y} .$$
  
 **3. Account for Aspect Ratio**
   
 $$ImageAspectRatio = \dfrac{ImageWidth}{ImageHeight},\\
PixelCamera_x = (2 * {PixelScreen_x} - 1) * {ImageAspectRatio},\\
PixelCamera_y = (1 - 2 * {PixelScreen_y}).$$

**4. Account for Field of View**


---
####Different Spaces
#####Raster Space:
Uses **raster coordinate system**, where the x-axis points to the right (when world space's x-axis points to the right) and y-axis points downwards. The origin situated at the top-left. A pixel in this coordinate system, is one unit long in x and y.     

#####NDC Space (Normalised Device Coordinate Space):
Origin situates at corner. The coordinates of the pixels are now **in the range [0,1]**. Note NDC in ray tracing is different than that in rasterisation world. For rasterisation, the mapping is generally in the range [-1, 1].

#####Screen Space
Origin situates at the center. The coordinates is **mapped in the range of [-1, 1]**.

#####World Space
The y coordination is still in the range of [-1, 1]. However, **the x coordination is mapped in the range of [-aspect ratio, aspect ratio]**.





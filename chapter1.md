## Generating Camera Rays
To produce ray traced images, we loop through each pixel and generate the **camera ray**. We need to calculate the **direction of rays** form the **camera origin** to the pixel. This section is on the techniques of converting pixel coordination from **raster space** to **world space**.

######Note
> By convention, the image frame is one unit away from camera origin. The camera orients to the negative z-axis or negative y-axis.

 
---
### Converting from Raster Space to Camera Space
 **1. Raster Space to NDC Space**
 
$$PixelNDC_x = \dfrac{(Pixel_x + 0.5)}{ImageWidth},\\

PixelNDC_y = \dfrac{(Pixel_y + 0.5)}{ImageHeight}.$$
 
 **2. NDC Space to Screen Space**
 
 $$PixelScreen_x = 2 * {PixelNDC_x} - 1,\\
 PixelScreen_y = 1 - 2 * {PixelNDC_y} .$$
  
 **3. Account for Aspect Ratio**
   
 $$ImageAspectRatio = \dfrac{ImageWidth}{ImageHeight},\\
PixelCamera_x = PixelScreen_x * {ImageAspectRatio},\\
PixelCamera_y = PixelScreen_y.$$

**4. Account for Field of View**

In the particular case where the camera is $$1 unit$$ away from the image frame, the view angle is $$90^\circ$$. For a view angle $$\alpha$$, we have :

$$PixelCamera_x = PixelScreen_x * {ImageAspectRatio}* tan(\dfrac{\alpha}{2}),\\
PixelCamera_y = PixelScreen_y * tan(\dfrac{\alpha}{2}).
$$

At this point the coordination is converted to the camera space.


---
### More on the Spaces
#####Raster Space:
Uses **raster coordinate system**, where the x-axis points to the right (when world space's x-axis points to the right) and y-axis points downwards. The origin situated at the top-left. A pixel in this coordinate system, is one unit long in x and y.     

#####NDC Space (Normalised Device Coordinate Space):
Origin situates at corner. The coordinates of the pixels are now **in the range [0,1]**. Note NDC in ray tracing is different than that in rasterisation world. For rasterisation, the mapping is generally in the range [-1, 1].

#####Screen Space
Origin situates at the center. The coordinates is **mapped in the range of [-1, 1]**.

#####World Space
The y coordination is still in the range of [-1, 1]. However, **the x coordination is mapped in the range of [-aspect ratio, aspect ratio]**.

---
### Camera at Any Point of View
Previously the conversion relies on camera sitting at default position $$(0,0,0)$$. However, we want to be able to render image from any particular point of view. To achieve this, we need to apply translation and rotation to the camera.

The translation and rotation of the camera can be expressed by a $$ 4 \times 4 \text{ matrix}$$ called the **camera-to-world matrix**.

```cpp
\\todo
```

>todo : 

>1. possible relation to **Quaternion**. Read about it

>2. need a demo for moving camera



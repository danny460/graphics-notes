Geometry
---
---
### Triangles
Complex objects can be modelled by geometric primitives like **polygons**, **NURBS** or **Bezier patches**, **subdivision surfaces** etc. Instead of working with these complex primitives, we can convert an object into a **triangle mesh**, and compute the intersection of rays with every triangle in a mesh. One favourable property with triangles is that, by construction, a triangle is coplanar (with three vertices on the same plane).

#### Ray-Triangle Intersection
The intersection test can be decomposed into a two-step test: 
1. Test if the ray intersect with the plane defined by the triangle
2. If so, test if the intersection point lies inside the triangle.


**Compute triangle's normal**
```cpp
// with know vertices A, B and C.
Vec3f A(-1, -1, 0), B(1, -1, 0), C(0, 1, 0);
Vec3f AB = B - A;
Vec3f AC = C - A;
Vec3f N = cross(AB, AC); // triangle's normal
N.normalize();
```
**Coordinate system handedness**(?)

The order in which a triangle's vertices are define affects the orientation of the surface normal, as the order for the cross product affects the direction of the normal. There will be conflicts when the modelling application and the renderer have different handedness. The solution is to mirror the camera and flip the model's normal direction(?).

#### Ray-Triangle Intersection: Geometric Solution

Suppose the hit point is P, with ray origin O and direction R. D represents the **distance** from the origin to the plane.

Then we have: 
$$ 
O + Rt = P, \\
D + N * P_0 = 0,\\
\text{where } P_0 \text{is any point on the plane.}
$$

The second equation can be derived from 
$$
(P - P_0) \cdot N = 0,    \\
\because P = O + tR,      \\
\therefore P \cdot N = -D 
$$

```cpp

```






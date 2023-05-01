Puzzle solutions. 

The initial plan was to try and have silhouettes be able to be directly matched to a background "solution" image. 

![image](https://user-images.githubusercontent.com/98255931/235386720-c183e5ed-fc6e-465d-8d78-311369d225cd.png)

The above image is a representation of the first idea, taken from Capcom's Resident Evil 7. However, Unreal itself offered no system that directly
supported "image matching" the silhouette. As such, a compromise was reached where instead of actually matching the image and the shadow together, 
a rotational check would be implemented instead to check the solution. On the outside, this would look identical to the original system I had envisioned, 
however, functionally this was a much more reasonable implementation. Additionally, since it was a check of numeric values, this system would be much easier
to bug test as well as attach additional functionalities (such as custom function calls). 

With this new direction in mind, additional research had to be done as to how such functionalities could be implemented. 

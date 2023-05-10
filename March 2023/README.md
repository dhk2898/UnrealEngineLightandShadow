The final level of the game took some more serious iterations to finally get right.

Initially the concept was that of the player traversing the mountaintops with clouds serving as the "wall" on which they would reflect their shadows on to solve puzzles. However, two issues presented themselves with this method. 
The Niagara particle system would have to be used in order to generate the cloud effects, but not only did this turn out to be fairly taxing when applied to a larger scale due to all the particle generation, 
the "cloud" itself produced very uneven shadows which made for an uneven playing experience. 

The next problem was that the "sun" that the players would control in this level was extremely gimmicky. The directional lighting which dictates how the lighting of the level would turn out, takes in three values, X, Y and Z, to adjust its position. However,
 within the game there was no real effective method of giving players control over these three values in a meaningful manner. I wanted to utilize the timeline node in order to give players control of the lighting, much in the same way the timeline node 
 was used to rotate the shadow objects until now, but the problems with this system was twofold. Playing the animation out over a smaller time period meant that the players had too little control over the lighting as it would rotate too quickly. Extending the timeline, 
 however, made it tedious if mistakes were made as it would take that much longer to correct the error. 
 
 The solution for this came in two ways. For the first one, to maintain a dynamic feel but still have a solid backdrop for shadows, I decided to replace the clouds with gently rolling water. The water would fully interact with the objects it touched, making for a more convincing effect
 but at the same time be much less taxing on the system as it was a texture applied to a plane, rather than thousands of particles generated each with their own individual properties to be computed. 
 
 The solution to the issue with player control came in the form of a plugin I discovered called the "Sun Position Calculator". This plugin condenses all the default lighting settings of a level into useful properties for the creator to edit. This includes things such as
 setting the time of the year in order to get different types of lighting, adjusting the brightness of the "sun" directly, and most importantly, giving a fully accessible and editable variable for time called "solar time". With values ranging from 0-24, this gives full
 control of the lighting in the level, in a quick and digestible fashion. With these two discoveries I began to work on the final level in earnest. 

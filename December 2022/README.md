With the main idea of the concept out of the way, it was time to do research on what would be needed to get the project going. 

For started, games in Unreal Engine can be coded in one of two ways, utilizing the Blueprint Visual Scripting system or the more traditional C++ in Visual Studio. 
In larger game studios, prototyping is done with the Blueprint system before it is then usual optimized via C++, because Blueprint is
less efficient in execution over C++ which becomes noticeable in larger projects. However, for the purposes of this project, Blueprint was enough given that the scale
of course wouldn't match those of large studios. 

As such, let's begin with how the puzzle was going to be implemented, starting with the EventTick Node. Nodes in Blueprint are handy modules that can be placed which 
dictate some function. Their modular nature, and easy way of connecting makes it easy to quickly test and iterate upon ideas and logic, also making for much easier 
bug testing. 

The OnComponentBeginOverlap node, is the starting point for our blueprint logic for the puzzle. As the name suggests, this node only activates when the player
overlaps with an assigned hitbox for the puzzle, and is the starting point for our logic. 

The next important node to be is the Timeline node. As you might have guessed, the timeline node allows us to make something happen over a set period of time. In the case
of our puzzle, the timeline will simply increase in value from 0 to 1 over the course of 15 seconds. This will be used to allow players to rotate the object in the light.

The third most important node is the Lerp node. Lerp stands for L(inear) (int)erp(olation) and will be used to set the degrees through which our object is allowed to rotate. 

![image](https://user-images.githubusercontent.com/98255931/236683906-ecccb6e6-4539-45cb-a980-cca52b5265d0.png)

Putting this all together results in an image like that of the above. OnComponentBeginOverlap starts our puzzle, which first passes through a boolean check to make sure it is
unsolved, before beginning the timeline. As the timeline increases from 0 to 1 over the course of 15 seconds, the Lerp node takes these values and translates that into 
the rotational values between 0 and 360. These values are then fed into the SetRelativeRotation node which updates the rotation of the shadow object. 

Once this rotational value falls between a certain threshold (our solution), the boolean condition used to check whether our puzzle is unsolved is set to false.

This is the basic skeleton of the logic that we will be using throughout our game. 

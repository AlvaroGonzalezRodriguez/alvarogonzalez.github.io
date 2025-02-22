---
title : Motores y sistemas de desarrollo para videojuegos' arcade
feed: show
date : 13/01/2023
---

# Arcade game in Unreal Engine 5.
## Author: Álvaro González Rodríguez
alu0101202556
## Motores y sistemas de desarrollo de videojuegos (MSDV)

<p>This game consist in a simple prototype of a shooting arcade game, where you control a pawn who only can move in the X axis. It is set in a spaceship where the rival clan have invaded you. You need to survive waves of enemies who will shoot
 you when they make eye contact with the controlled pawn. But that's not all, you can shoot at them too! If you hit two shots, you will win 100 points and if they hit you four times is a game over. Luckily, there are some health packages that will health
 you once hit, but no more health than you can store.</p>
 
![Alt Text](../assets/img/arcade1.gif)
<p>As you can see the game has no end, it only finish when your health reach zero. So try to get the best hight score!</p>
 
![Alt Text](../assets/img/arcade2.png)
<p>This is the scene, all of the assets you can see in the image are from a free asset package from the marketplace of Epic Games. To point the important ones, there are two spawner, one for the enemies and other for the health package.
 There are also two blocking volumes to prevent the player from getting away from the stage, the player start and a camera.</p>
  
![Alt Text](../assets/img/arcade3.png)
<p>The player blueprint have defined 4 behaviours, the x axis movement, a look at the mouse position, the shoot input and the collisions handle with the bullets. In the image we can see a part of the blueprint where the player look at the mouse position,
 to accomplish this result we use the Break Hit Result node and the Get Hit Result Under Cursor by Channel. All of the animation, material and unique mesh that the player and the enemies have where developed in Blender. To put all of these together I
 create an animation blueprint that respond to the diferent variables from the blueprint and represent the correct animation.</p>
  
![Alt Text](../assets/img/arcade4.png)
<p>The enemy blueprint works along the enemy blackboard, so it has less behavours defined, it has the movement which is in the Y axis, the overlap with the bullet and it also changes some variables from the blackboard. In the image we can see the parto of the attack
 blueprint, it only activate when the enemy see the player, so is defined in the tree behaviour as a task. The bullet blueprint is very simple because it uses the projectile movement component and the collision with other objects is handle by other
 actors.</p>
 
![Alt Text](../assets/img/arcade5.png)
<p>The spawner works for all types of actors, so we can have easily have a spawner of health packs and a spawner of enemies using the same blueprint. The image represent how the health pack heal the player when it overlap with him</p>

![Alt Text](../assets/img/arcade6.png)
<p>The game use a simple widget to represent the heath and the points that the player has as you can see in the execution. It has two custom event to put the variables from the player and the game mode, which is the one who store the points, in the widget,
 so we need to call them in the respectives bluprint.</p>
<p>There are also some sounds and particles that appear when the player or the enemies do some actions and a background music. The sounds and particle are managed in the blueprint and not in the animator</p>

<p>And this is a link to the presentation</p>

[Presentation Arcade Project](https://youtu.be/5L0LkA51wuM)
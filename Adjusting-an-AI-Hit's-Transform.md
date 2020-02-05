# Adjusting an AI's Hit Transform
An AI's Hit transform controls the transform point that other AI will use when using the head look feature allowing them to look at this transform. This transform is also used for ranged combat allowing other AI's projectiles to hit this spot. This is to ensure an AI is always seen, regardless of how large or small they are.

The Hit Transform setting is located in the AI's Settings>Combat>Combat Actions tab near the bottom. This tab must be open in order to see the Hit Transform gizmo.

Adjusting the Hit Transform slider will adjust the red gizmo on your AI.
![](https://i.imgur.com/2FgrIdz.gif)

This is used to determine where other AI will look when using the Head Look feature and where projectiles will aim for when other AI are using projectiles. It is important that this stays within your AI's area and its Box Collider to ensure projectiles don't miss the AI.
![](https://i.imgur.com/QKqIcXY.gif)

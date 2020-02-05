# Adjusting an AI's Hit Transform
An AI's Hit Transform used for controlling 3 important functionalities.

### Info
| Usage  | Description |
| ------------- | ------------- |
| Target Obstruction  | The most important usage for the Hit Transform is used to determine if an AI's target is obstructed when using Ranged Combat. If the Hit Transform is too high or too low, the opposing AI may have problems detecting the AI. |
| Projectile Abilities  | The Hit Transform controls where an opposing AI's projectiles will hit an AI. This is helpful to ensure projectiles don't hit too low or too high and to give users more control for customization.
| Head Look Feature  | The Hit transform is used to control the point that other AI will use when using the head look feature. This is helpful to ensure other AI are looking at the appropriate point of an AI.   |

The Hit Transform setting is located in the AI's Settings>Combat>Combat Actions tab near the bottom. This tab must be open in order to see the Hit Transform gizmo.

### How to use

Adjusting the Hit Transform slider will adjust the red gizmo on your AI.
![](https://i.imgur.com/2FgrIdz.gif)

This is used to determine where other AI will look when using the Head Look feature and where projectiles will aim for when other AI are using projectiles. It is important that this stays within your AI's area and its Box Collider to ensure projectiles don't miss the AI.
![](https://i.imgur.com/QKqIcXY.gif)

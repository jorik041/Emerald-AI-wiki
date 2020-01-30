# Detection Type
An AI’s Detection Type determines how it detects its targets when an AI is within their Detection Radius. Emerald AI features two Detection Types; Trigger and Line of Sight.
![](https://i.imgur.com/pT1YBmh.png)

## Trigger
The Trigger Detection Type allows an AI to detect any target within an AI's Detection Radius, even if the target is obstructed by another object.

<img src="https://i.imgur.com/fnHdHjB.png" width="50%">

## Line of Sight
The Line of Sight Detection Type makes it possible for AI to “see” allowing them to only target objects that they can detect within their Field of View. This works by casting a raycast according to an AI’s Field of View angle. Any object that’s greater than an AI’s Line of Sight will not be visible and anything that’s within it is visible to the AI. This method also allows targets to hide behind objects which obstructs an AI's line of sight.

### A Target within an AI's Line of Sight
<img src="https://i.imgur.com/UQgLnnu.png" width="50%">

### A Target outside of an AI's Line of Sight
<img src="https://i.imgur.com/5tPvJa2.png" width="50%">


# Target Picking Method
An AI’s Target Picking Method is important to get the results you are looking for. Both options have their strengths, but it depends on the situation and playing style. The Target Picking Method can be found under the Detection Options and has two options, First Detected and Closest.

<img src="https://i.imgur.com/VdGd2NQ.png" width="50%">

## First Detected
The First Detected method can be useful for accurate small scale battles where you want your AI to visually see or detect their targets and allow your player to sneak up on an AI. This is more applicable to the Line of Sight Detection Type as this feature actually requires an AI to see their target before it can start to attack. The drawback to this method is that, when in large scale battles, it can make multiple AI all mark the same target resulting in clusters or groups that are too close.

![](https://i.imgur.com/waytpOY.gif)

## Closest
Closest is useful for nearly all situations and is important for large scale battles. This method still requires an AI to visually see or detect a target with their Detection Radius, but it will search for targets within the area and assign the closest one, even though that may mean that the target may not be fully in sight. This feature also keeps AI evenly distributed and prevents AI from all picking the same target resulting in unappealing battle formations that are much too close. 

![](https://i.imgur.com/qLc5o1M.gif)
# Wander Types and Movement
This section is somewhat extensive and so it's covered in two sections. The first section gives a basic explanation of what each wander type does. The second section will explain in detail how to implement each Wander Type. An AI's Wander Type can be found within the Temperament tab.

&nbsp;

Table of Content
* 1
* 2
* 3

&nbsp;

## Wander Type
An AI's Wander Type determines how it moves when not in combat. The Wander Type option can be found within the Temperament tab.

![](https://i.imgur.com/I9kbWYX.png)

| Wander Type  | Description |
| ------------- | ------------- |
| Dynamic  | Allows an AI to randomly wander by dynamically generate waypoints around their Wander Radius.  |
| Waypoints  | Allows you to define waypoints that the AI will move between.  |
| Stationary  | Allows an AI to stay stationary in the same position and will not move unless a target enters their trigger radius.  |
| Destination  | Allows an AI to travle to a single destination. Once it reaches it destination, it will stay stationary.  |

&nbsp;

## Dynamic - Wander Type
The Dynamic Wander Type does a lot of the work for you. It randomly generates a waypoint anywhere within the green radius. You can adjust the size of this radius and set the slope limitation which stops waypoints from generating on unreachable or too steep locations. Note: The green dynamic wandering radius indicator is only visible within the Temperament tab and not during runtime.

![](https://i.imgur.com/ArREX20.png)

<img src="https://i.imgur.com/16c8Y2S.png" width="59%">

## Dynamic - Wander Type
The Dynamic Wander Type allows an AI to stay stationary in the same position and will not move unless a target enters their trigger radius. If an AI attacks and kills a target when using this Wander Type, it will return to the starting stationary destination.

&nbsp;

## Waypoints - Wander Type
Waypoints allow you to create a series of destinations for your AI to move between. AI that are using waypoints will still react to targets according to their Behavior Type. Once a target has been killed, or successfully fled, the AI will resume moving between its waypoints.
If you’d like to create your own waypoint system for your AI, you can do so by going to the Waypoint Editor tab located in the Emerald Editor. By default, the Wander Type is set to Dynamic (which randomly generates waypoints). When you open the Waypoint Editor tab, you will see a button to enable waypoints. Once you’ve done this, you will see the waypoint options appear. You can now create a waypoint by pressing the “Add Waypoint” button.

<img src="https://i.imgur.com/0F86qQN.png" width="50%">

Pressing the Add Waypoint button initially will create your AI’s first waypoint. After this, each time you press the Add Waypoint button, an additional waypoint will be created. Each newly waypoint will be positioned 1 unit on the Z axis to avoid being placed in the same position as the previous waypoint. This also makes it easier for customizing your AI’s route. The blue line you see that goes from your AI to your first waypoint indicates the AI’s direction to the first point. You must have at least 2 waypoints for your AI to move between. Waypoints are only visible while the Waypoint Editor tab is active for each AI. Multi-Object Editing is not available for the Waypoints tab. There is no cap on waypoints that can be created. When you test your scene, your AI will immediately start following its waypoint, given that it is currently in an active state. 

![](https://i.imgur.com/C9P3igX.gif)

If you happen to make a mistake, and need to remove a waypoint that’s located in the middle of 15 points, you can remove that specific waypoint and Emerald will resize itself so you don’t have to start over. If you’d like to completely start over, you also have the option to clear all your waypoints. This can be done by pressing the “Clear All Waypoints” button. Keep in mind that both of these processes cannot be undone. When you play the scene, the AI will follow the waypoints you've set, unless they enter Combat Mode.

![](https://i.imgur.com/SXAnCKJ.gif)

There are three Waypoint Types which determines how your AI will move through the waypoints.

| Waypoint Type  | Description |
| ------------- | ------------- |
| Loop  | When an AI reaches its last waypoint, it will set the first waypoint as its next waypoint thus creating a loop. |
| Reverse  | When an AI reaches its last waypoint, it will reverse the AI's waypoints making the last waypoint its first. This allows AI to patorl back and forth through narrow or one way areas.  |
| Random  | This allows an AI to patrol randomly through all waypoints. An AI will idle each time it reaches a waypoint for as long as its wait time seconds are set. The idle animation that is played is randomly picked from your AI's Idle Animation List.  |  


&nbsp;


## Destination - Wander Type
Destinations are different than waypoints. Destinations allow you to set a point anywhere on the NavMesh and the AI will move to that destination. AI using destinations will not follow any other waypoints and will take the quickest route to get to their set destination. AI that have arrived at their destination will trigger the event ReachEdDestinationEvent(). This can be useful for triggering custom code or quests when an AI arrives at their destination. At anytime, you can change the AI’s destination programmatically by calling the ```c# EmeraldEventsManager.SetDestination(Transform Destination)``` function. This feature can even make it possible for AI to even have schedules through code or a time of day system such as UniStorm. For a working schedule example, see the script here: 

Unlike Waypoints, destinations are set through the Temperament tab. To create a destination for your AI, go to the Temperament tab. Once here, change the Wander Type to Destination. This will automatically create a destination point for your AI.

![](https://i.imgur.com/rfH1yLu.png)

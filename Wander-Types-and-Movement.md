# Wander Types and Movement

## Wander Type
An AI's Wander Type determines how it moves when not in combat. The Wander Type option can be found within the Temperament tab.
![](https://i.imgur.com/I9kbWYX.png)

| Wander Type  | Description |
| ------------- | ------------- |
| Dynamic  | Allows an AI to randomly wander by dynamically generate waypoints around their Wander Radius.  |
| Waypoints  | Allows you to define waypoints that the AI will move between.  |
| Stationary  | Allows an AI to stay stationary in the same position and will not move unless a target enters their trigger radius.  |
| Destination  | Allows an AI to travle to a single destination. Once it reaches it destination, it will stay stationary.  |

## Setting Up Waypoints
Waypoints are a powerful new addition to Emerald AI. They allow you to create a series of destinations for your AI to move between. AI that are using waypoints will still react to targets according to their Behavior Type. Once a target has been killed, or successfully fled, the AI will resume moving between its waypoints.
If you’d like to create your own waypoint system for your AI, you can do so by going to the Waypoint Editor tab located in the Emerald Editor. By default, the Wander Type is set to Dynamic (which randomly generates waypoints). When you open the Waypoint Editor tab, you will see a button to enable waypoints. Once you’ve done this, you will see the waypoint options appear. You can now create a waypoint by pressing the “Add Waypoint” button.

Pressing the Add Waypoint button will create your AI’s first waypoint. You must have at least 2 waypoints for your AI to move between. Waypoints are only visible while the Waypoint Editor tab is active for each AI. Multi-Object Editing is not available for the Waypoints tab.

Each time that you press the Add Waypoint button, a new waypoint will be created. Each newly waypoint will be positioned 1 unit on the Z axis to avoid being placed in the same position as the previous waypoint. This also makes it easier for customizing your AI’s route. The blue line you see that goes from your AI to your first waypoint indicates the AI’s direction to the first point. You have the option to loop your waypoints, which will allow your AI to continue to loop through the waypoints after it has reached the end, or Reverse, which will have your AI walk the same path but in the opposite direction.   
There is no cap on waypoints that can be created. When you test your scene, your AI will immediately start following its waypoint, given that it is currently in an active state. 

If you happen to make a mistake, and need to remove a waypoint that’s located in the middle of 15 points, you can remove that specific waypoint and Emerald will resize itself so you don’t have to start over. If you’d like to completely start over, you also have the option to clear all your waypoints. This can be done by pressing the “Clear All Waypoints” button. Keep in mind that both of these processes cannot be undone.


## Setting Up an AI Destination
Destinations are different than waypoints. Destinations allow you to set a point anywhere on the NavMesh and the AI will move to that destination. AI using destinations will not follow any other waypoints and will take the quickest route to get to their set destination. AI that have arrived at their destination will have a public variable called “AI Reached Destination” set to true. This can be useful for triggering other events. At anytime, you can change the AI’s destination programmatically by calling the SetDestination(Transform Destination) function. This feature can even make it possible for AI to even have schedules through code or a time of day system such as UniStorm (Emerald AI schedule integration with UniStorm is coming soon. This will allow users to set schedules via the Emerald Editor and not just through code).

Unlike Waypoints, destinations are set through the Temperament tab. To create a destination for your AI, go to the Temperament tab. Once here, change the Wander Type to Destination. This will automatically create a destination point for your AI.



This will also open up an additional option called Destination Animation. This gives you control over which animation is used for moving to the AI’s destination point. Walk setting will use the walk animation and walk speed you’ve set via the AI’s Setting options and the Run setting will use the run animation and the run speed you’ve set via the AI’s Setting options. AI will still react to targets according to their Behavior Type. Once they have successfully fled or killed their target, the AI will resume moving to their destination point.

Walk Destination Animation Setting

Run Destination Animation Setting

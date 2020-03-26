# Enabling an AI's Debug Tools
Emerald AI features built-in debugging tools for AI that are not behaving as expected. This can make it easier to pinpoint issues by having previously hidden information visible.

To enable an AI's Debug Tools, go to an AI's Emerald AI editor and navigate to the Docs tab. At the bottom of this tab underneath the Report a Bug button, you will see Enable Debugging. Setting this setting to true will make more options available.

![](https://i.imgur.com/aW6pG4N.png)

The follow table explains what each debugging tool does.

| Debug Tool  | Description |
| ------------- | ------------- |
| Draw Raycasts  | This setting is mostly used by ranged AI and it allows raycasts to be draw and visible, while in the Unity Editor. This can be useful for ensuring raycast are being positioned correctly to targets. A green line indicates that the AI's sight is not obstructed. A red line indicates that an AI's line of sight is obstructed. A orange line indicates an AI's view of each AI within its Line of Sight (When using the Line of Sight Detection Type). Lastly, a yellow line indicates an AI's line of sight towards its look at target. |
| Debug Log Targets  | Allows the target objects to be displayed in the Unity Console. This can be useful for ensure the proper object is being hit when the AI is targeting an object. |
| Debug Log Obstructions  | Allows the AI's obstructions to be displayed in the Unity Console. This can be useful for ensure the proper object is being hit when the AI is targeting an object. |
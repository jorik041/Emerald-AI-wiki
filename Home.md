# Emerald AI Wiki

![](https://i.imgur.com/t4EiLuN.png)

Emerald AI allows developers to quickly create engaging dynamic AI with 100's of AAA quality features, all without having to write a single line of code! Emerald's editor is designed to make creating AI easy, yet incredibly customizable. Emerald caters to all kinds of developers and offers everything users would expect from an all-in-one AI system.

Emerald AI can be found on the Asset Store: [Get Emerald AI](https://assetstore.unity.com/linkmaker/embed/package/40199/widget?aid=1101l3nnr)

## Table of Content
* [Home]
* [Getting Started]
   * [Baking NavMesh]
   * [Creating a New AI]
* [Behaviors and Confidence Levels]
* [Wander Types and Movement]
* [Using Factions and Faction Manager]
* [Creating an AI Ability Object]
* [Detection Settings]
* [Emerald AI Animation Events]
* [Emerald AI API]

[Home]: https://github.com/Black-Horizon-Studios/Emerald-AI/wiki
[Getting Started]: https://github.com/Black-Horizon-Studios/Emerald-AI/wiki/Getting-Started
[Creating a New AI]: https://github.com/Black-Horizon-Studios/Emerald-AI/wiki/Creating-a-New-AI
[Baking NavMesh]: https://github.com/Black-Horizon-Studios/Emerald-AI/wiki/Baking-NavMesh
[Behaviors and Confidence Levels]: https://github.com/Black-Horizon-Studios/Emerald-AI/wiki/Behaviors-and-Confidence-Levels
[Wander Types and Movement]: https://github.com/Black-Horizon-Studios/Emerald-AI/wiki/Wander-Types-and-Movement
[Emerald AI API]: https://github.com/Black-Horizon-Studios/Emerald-AI/wiki/Emerald-AI-API
[Using Factions and Faction Manager]: https://github.com/Black-Horizon-Studios/Emerald-AI/wiki/Using-Factions-and-Faction-Manager
[Creating an AI Ability Object]: https://github.com/Black-Horizon-Studios/Emerald-AI/wiki/Creating-an-AI-Ability-Object
[Emerald AI Animation Events]: https://github.com/Black-Horizon-Studios/Emerald-AI/wiki/Emerald-AI-Animation-Events
[Detection Settings]: https://github.com/Black-Horizon-Studios/Emerald-AI/wiki/Detection-Settings

# Emerald AI Features
Create Any AI
Create any kind of AI such as AI with guns, bosses, guards, villagers, thieves, bandits, creatures, animals, wildlife, zombies, companions, hovering robots, and more.

## Root Motion Support
Emerald AI supports Root Motion allowing an AI's movement to be driven by their animations.

## Modular Abilities
Emerald's new Modular Abilities system allows users to create abilities through scriptable objects. These abilities can then be applied to an AI's ability list giving them added functionality such as healing and summoning other AI. Projectiles and spells can also be created with this system allowing for nearly any kind of weapon to be created. Every Ability Object allows users to customize the sounds, particle effects, timers, and other settings.

## Switchable Ranged and Melee Combat
Switchable ranged and melee combat has been a heavily requested feature so it's been added! This allows AI to switch between ranged and melee combat according to the distance from an AI's target. Users can customize the distance and other setting to best suit their AI.

## Animation Profiles
Animation Profiles allow for users to quickly export and import animations between AI that share the same rigging and animations. This improves the workflow so users no longer have to manually enter animations if they have many AI that share animations. The best part of this feature is that it's multi-object supported!

## Included Needs System
Included with Emerald AI is a needs system that allows an AI to generate waypoints to objects such as food, water, and other resources. An AI will dynamically wander until it's low on resources. When this happens, the AI will search nearby for objects that match its resources layer and begin to replenish its resources upon arrival. When they are full, it will dynamically wander again.

## Setup Manager
Emerald AI's Setup Manager makes the AI setup process easy by applying all needed scripts and components to an animated model.

## Built-In Look At and Aiming Mechanics
The optional Look At feature allows humanoid AI the option to look at their targets or a nearby player while using their current animation. This feature is usable during combat and is also usable while the AI is wandering or walking to a destination. The weight and intensity of the head look and body look can be customized. This feature also allows ranged AI to aim their weapons towards their targets, even if their target is above or below them.

## Behaviors and Temperament
Emerald has 5 preset behaviors each with 3 temperaments to give you control over how your AI dynamically reacts to targets. Companion and Pet behaviors are also possible allowing AI to follow players around to assist them in combat.

## Line of Sight
The Line of Sight feature allows AI to only attack or flee from targets that are visible from the AI's line of sight. This also keeps AI from being able to detect targets through walls or objects. However, an option is also available to not use the line of sight feature, for those who want more of a casual RPG target detection.

## Blocking Support
The optional Blocking option allows an AI to block incoming attacks. Users can control how much damage is mitigated with a successful block, the odds to block, and the angle to block. Users can also customize which blocking animations an AI uses.

## Built-in Aggro System
The optional built-in aggro system allows users to specify how many hits will cause an AI to switch targets with the options to choose based off of the Closest Attacker, Last Attacker, and Random Attacker.

## Built-in UI
A built-in UI system allows AI to have health bars, display an AI's name and level, and combat text. The settings allow users to customize the color, images, size, and position. The UI system will automatically apply your settings and rotate towards your player's camera as needed.

## Built-in Ranged Combat
Emerald features a built-in ranged combat system that allows AI the ability to engage in ranged combat. AI will fight according to what Ability Objects they are currently using. Guns, lasers, Sci-Fi weapons, rocket launchers, bow and arrows, spells and magic, and more are all possible.

## Built-in Waypoint System
Emerald features a built-in Waypoint System that allows users to set a series of waypoints for an AI to follow/patrol. AI will still react to targets using their behaviors while following their waypoint paths and continue to follow them after their target has been killed or escaped. Waypoints can be set, added, manipulated, and cleared all from within the Emerald AI Editor using custom handles and icons.

## Built-in Object Pooling
All objects created with Emerald AI are created from an object pool so objects are recycled and not instantiated. The object pool can automatically expand when needed.

## Built-in Events
Emerald AI has 9 events for added functionality. These events include On Start, On Enable, On Reach Destination, On Player Detection, On Start Combat, On Attack, On Damaged, On Flee, and On Death. Events can be used to call custom code or Emerald AI's own API.

## Built-in Slope Alignment
The optional Alignment feature will align AI to the slope angles of the terrain and other surfaces. Users can specify the speed and maximum angle amounts.

## Ragdoll Support
Emerald AI supports ragdolls and can seamlessly transition between an AI's current animation and their ragdoll on death.

## Auto Optimization System
Emerald AI has an optional feature to disable the AI system for AI that are not visible to the camera or that are culled to increase performance.

## Powerful Easy to Use Editor
Create complex AI with Emerald AI's easy to use, self-documented editor. Everything is explained right from within the editor.

## API and Documentation
Well documented code with tons of API for advanced users. Emerald includes 12 examples scenes each demonstrating a different feature or capability. Scripting Reference site that shows and explains all of Emerald's usable API. Emerald's documentation covers every feature that you may want to use. The documentation is accessible right from within the Emerald Editor.

## Animations
Emerald supports 98 animations an AI can use, allows users to change an AI's animations right from within the editor, and will automatically create and update an AI's Animator Controller. Each animation has its own animation speed control. Emerald's Animation Events allow for perfectly timed attacks and added functionality.
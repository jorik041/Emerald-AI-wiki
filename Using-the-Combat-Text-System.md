# Using the Combat Text System
Emerald AI has a built-in combat text system. This works globally for all AI and can even be called for player damage (discussed below) and is handled through the Combat Text Manager. The combat text system is optional and can be disabled through the Combat Text Manager.

## Combat Text Settings
The Combat Text Settings allow you to control all of the combat text's settings such as whether the combat text system is enabled, text sizes, text animations, and more.

### Animation Type
The Animation Type allows users to control the type of animation the combat text uses. There are a total of 5 preset options.

| Animation Type  | Example |
| ------------- | ------------- |
| Bounce  | ![](https://i.imgur.com/I3k5J2w.gif) |
| Upwards  | ![](https://i.imgur.com/1Q5LPBe.gif)  |
| Outwards v1  | ![](https://i.imgur.com/nBeuNbe.gif)  |
| Outwards v2  | ![](https://i.imgur.com/6JV2xLz.gif)  |
| Stationary  | ![](https://i.imgur.com/WFxX3vx.gif)  |

## Combat Text Color Settings
The Combat Text Color Settings allow you to control all color related settings for the Combat Text System. Player damage text needs to be called programmatically to work for custom character controllers. This is explained in the code section below.
| Setting  | Description |
| ------------- | ------------- |
| Player's Damage Text Color  | Controls the text color of player dealt damage. Note: In order for custom players to use the Combat Text System, they have to call an instanced function. This is explained below.  |
| Player's Critical Hit Text Color  | Controls the text color of player dealt critical hit damage. Note: In order for custom players to use the Combat Text System, they have to call an instanced function. This is explained below.  |
| Player's Take Damage Text Color  | Controls the text color of player received damage.  |
| AI's Critical Hit Text Color  |  Controls the text color of all melee and ranged damage critical hits. |
| Healing Text Color  | Controls the text color of an AI's healing amount done when using Healing abilities.  |


## Accessing the Combat Text System
The Combat Text System is created on Start during runtime. It can be accessed to allow custom character controllers to display their damage dealt to Emerald AI agents.

The Combat Text System function that allows users to display custom combat text with their players is CreateCombatText.
```c#
CreateCombatText(int DamageAmount, Vector3 TextPosition, bool CriticalHit, bool HealingText, bool PlayerTakingDamage)
```

To use this, users must include the Emerald AI namespace at the top of their script.
```C
using EmeraldAI;
```

Emerald AI creates an instance of the Combat Text System at runtime which can be accessed using:
```c#
CombatTextSystem.Instance
```
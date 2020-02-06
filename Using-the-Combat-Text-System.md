# Using the Combat Text System
Emerald AI has a built-in combat text system that's controllable through the Combat Text Manager. This can be accessed by pressing ctrl+shift+C or by going to Window>Emerald AI>Combat Text Manager in Unity. The Combat Text System works globally for all AI and can even be called for player damage (discussed below). The combat text system is optional and can be disabled through the Combat Text Manager.

## Combat Text Settings
The Combat Text Settings allow you to control all of the combat text's settings such as whether the combat text system is enabled, text sizes, text animations, customize the font used by the combat text, and more.

<img src="https://i.imgur.com/fIIJ2u9.png" width="70%">

### Animation Type
The Animation Type allows users to control the type of animation the combat text uses. There are a total of 5 preset options. The position of each text is randomized to minimize the chance of text overlapping each other.

| Animation Type  | Example |
| ------------- | ------------- |
| Bounce  | ![](https://i.imgur.com/I3k5J2w.gif) |
| Upwards  | ![](https://i.imgur.com/1Q5LPBe.gif)  |
| Outwards v1  | ![](https://i.imgur.com/nBeuNbe.gif)  |
| Outwards v2  | ![](https://i.imgur.com/6JV2xLz.gif)  |
| Stationary  | ![](https://i.imgur.com/WFxX3vx.gif)  |

&emsp;

## Combat Text Color Settings
The Combat Text Color Settings allow you to control all color related settings for the Combat Text System. Player damage text needs to be called programmatically to work for custom character controllers. This is explained in the code section below.

<img src="https://i.imgur.com/Xu5eobE.png" width="70%">

| Setting  | Description |
| ------------- | ------------- |
| Player's Damage Text Color  | Controls the text color of player dealt damage. Note: In order for custom players to use the Combat Text System, they have to call an instanced function. This is explained below.  |
| Player's Critical Hit Text Color  | Controls the text color of player dealt critical hit damage. Note: In order for custom players to use the Combat Text System, they have to call an instanced function. This is explained below.  |
| Player's Take Damage Text Color  | Controls the text color of player received damage.  |
| AI's Critical Hit Text Color  |  Controls the text color of all melee and ranged damage critical hits. |
| Healing Text Color  | Controls the text color of an AI's healing amount done when using Healing abilities.  |

&emsp;

## Accessing the Combat Text System
The Combat Text System is created on Start during runtime. It can be accessed to allow custom character controllers to display their damage dealt to Emerald AI agents.

Users must include the Emerald AI namespace at the top of their script in order for the CombatTextSystem class to be visible.
```C
using EmeraldAI;
```

You can then call the CreateCombatText function which allows custom player damage with the following code:
```c#
CombatTextSystem.Instance.CreateCombatText(int DamageAmount, Vector3 TextPosition, bool CriticalHit, bool HealingText, bool PlayerTakingDamage)
```

This should go in the portion of your character controller that damages Emerald AI. It includes special parameters for added functionality. 
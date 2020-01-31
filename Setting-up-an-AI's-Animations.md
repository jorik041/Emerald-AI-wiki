# Setting up an AI's Animations
If you have already generated an AI's Animator Controller, please see the **Updating an AI's Animation** section. Emerald AI features nearly 100 usable animations. However, not all of these have to be used. It is important that all needed animations are setup before testing to avoid errors.

## Step 1
When you first create an AI, you will notice this message at the top of the Emerald AI editor. An AI need to have an Emerald AI generated Animator Controller as it requires specific states and parameters to work well with Emerald AI. For this guide, we will be adding the animations first and then generating the Animator Controller.
![](https://i.imgur.com/oUnr3dz.png)

## Step 2
Go to the Animation tab within the Emerald AI editor. Here, you will notice 4 different tabs each with lots of blank slots for animations.
![](https://i.imgur.com/q4xBbM1.png)

| Animation Tab  | Description |
| ------------- | ------------- |
| Idle  | The Idle Animations tab allows you to set all idle animations that this AI will use when wandering and the idle animations that will be used in combat.  |
| Movement  | The Movement Animations tab allows you to set all movement animations for both non-combat and combat such as walk, run, movement turning, and stationary turning. |
| Combat  | The Combat Animations tab allows you to set all combat animations such as attack, block, hit, death, equip, and unequip animations. Some of these are used depending on if they are enabled, such as the equip and unequip animations. |
| Emote  | The Emote Animations tab allows you to set the emote animations that will play when an AI's PlayEmoteAnimation function is called and passing the emote ID as the parameter. The speed of each animation can be adjusted by changing the speed parameter.  |
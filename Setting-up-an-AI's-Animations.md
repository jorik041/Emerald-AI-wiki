# Setting up an AI's Animations
Emerald AI features nearly 100 usable animations. However, not all of these have to be used. It is important that all needed animations are setup before testing to avoid errors.

**Note:** If you have already generated an AI's Animator Controller, Emerald AI will automatically update an AI's Animator Controller each time a new animation is added so there's no need to manually recreate the Animator Controller.

## Step 1
When you first create an AI, you will notice this message at the top of the Emerald AI editor. An AI need to have an Emerald AI generated Animator Controller as it requires specific states and parameters to work well with Emerald AI. For this guide, we will be adding the animations first and then generating the Animator Controller.

![](https://i.imgur.com/oUnr3dz.png)

## Step 2
Go to the Animation tab within the Emerald AI editor. Here, you will notice 4 different tabs each with lots of blank slots for animations.

![](https://i.imgur.com/q4xBbM1.png)

| Animation Tab  | Description |
| ------------- | ------------- |
| Idle  | The Idle Animations tab allows you to set all idle animations that this AI will use when wandering and the idle animations that will be used in combat.   |
| Movement  | The Movement Animations tab allows you to set all movement animations for both non-combat and combat such as walk, run, movement turning, and stationary turning. If your AI is using both weapon types, you will need to apply animations for both Ranged and Melee. |
| Combat  | The Combat Animations tab allows you to set all combat animations such as attack, block, hit, death, equip, and unequip animations. Some of these are used depending on if they are enabled, such as the equip and unequip animations. If your AI is using both weapon types, you will need to apply animations for both Ranged and Melee. |
| Emote  | The Emote Animations tab allows you to set the emote animations that will play when an AI's PlayEmoteAnimation function is called and passing the emote ID as the parameter. The speed of each animation can be adjusted by changing the speed parameter.  |

## Step 3
Applying animations to an AI is pretty straight forward. Go through each Animation tab and apply the proper animations to each empty animation slot. If you get to an animation that you might not have, such as Walk Left or Walk Right, you can just use the Walk animation in its place. The same goes for the stationary turn animations, idle animations can be used here if your AI doesn't have any. Each animation list requires at least 1 animation, if it's enabled. Any Aggressive or Cautious (Brave or Foolhardy) AI require at least 1 attack animation. It is important that no animations are missed to avoid errors during runtime.

## Step 4
After you have applied all needed animation, you can generate your AI's Animator Controller. This can be done by going to the bottom of the Animation tab and pressing the "Create Animator Controller" button. When you do this, you will be asked to name and find a save location for your generated Animator Controller.

![](https://i.imgur.com/VhAJYQx.png)

![](https://i.imgur.com/puBnKxq.png)

## Step 5
After saving your Animator Controller, the generate process will finalize. This generates an Animator Controller using all of the animations you applied with the correct parameters and states Emerald AI needs. Now, each time you apply animations  to AI, your Animator Controller will automatically be updated so there's no need to regenerate it. If you haven't already done so, you will need to add attack animation events to your AI's attack animations. This can be found with the [Creating Attack Animation Events](https://github.com/Black-Horizon-Studios/Emerald-AI/wiki/Creating-Attack-Animation-Events) section.
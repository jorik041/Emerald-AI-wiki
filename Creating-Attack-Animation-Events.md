# Creating Attack Animation Events
Attack Animation Events are what allows an AI to deal damage. They work by calling the EmeraldAttackEvent at a specific frame of an AI's attack animations. When using the Melee Weapon Type, and an AI's target is within range, the event will successfully damage an AI's target. When using the Ranged Weapon Type, this event will successfully create an AI's Ability or Projectile Ability.

## Part 1
To apply an attack animation event to an AI's attack animation, go to the AI's Animation>Combat tab and select its first attack animation within its Attack Animations List.

![](https://i.imgur.com/oQC3QOf.png)

## Part 2
This will bring you to the Project tab where the animation's location is. Select the object that holds the attack animation and view it within the Inspector.
![](https://i.imgur.com/GRf1XY1.png)

![](https://i.imgur.com/TKGbN48.png)

## Part 3
When scrolling down within this tab, you will see the Events tab. Click it to expand it which will reveal options to create an Animation Event.
![](https://i.imgur.com/QiX0Iue.gif)

## Part 4
Find the exact frame you want the AI to cause damage with its attack animation, or use an Ability, and press the Add Event button. When you've done this, assign EmeraldAttackEvent as the function name. When you've finished this, press Apply. You will need to do this for each attack animation that's in your AI's Attack Animation List. This allows damage and ability events to trigger that looks and functions best for the AI's animation.

![](https://i.imgur.com/JfjwzXR.gif)

## Step 5
Double check that the function name was entered correctly and that the attack animation is being used by the AI. AI will receive errors if an attack animation event is missing or was entered incorrectly. If you haven't already done so, you will need to setup your AI's Tags and Layers as well as its Faction Relations list. These steps are what allow your AI to properly detect other AI and player objects.

[Setting up an AI's Tags and Layers](https://github.com/Black-Horizon-Studios/Emerald-AI/wiki/Setting-up-an-AIs-Layers-and-Tags)

[Setting up an AI's Faction Relations](https://github.com/Black-Horizon-Studios/Emerald-AI/wiki/Using-Factions-and-Faction-Manager)
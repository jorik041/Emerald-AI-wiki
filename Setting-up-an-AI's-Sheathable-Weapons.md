# Setting up an AI's Sheath-able Weapons
Emerald AI features a built-in system that allows an AI to have sheath-able weapons through Animation Events and the game objects attached to their bones. This makes it possible for an AI to have more believable non-combat animation and to show an AI pulling out and putting away their weapons.

![](https://i.imgur.com/xeDEta1.gif)

## Step 1
First, you will need to go to the Animation>Combat tab and enable Use Equip Animations.
![](https://i.imgur.com/L9Rv6q6.png)

## Step 2
Once you have enabled the Use Equip Animation, two additional animation slots will become available. Apply your Equip animation (Pulling the out) to the Equip animation slot and the Unequip animation (Putting the weapon away) to the Unequip animation slot.

## Step 3
Go to the AI's Settings>Combat>Combat Actions tab and enable Use Weapon Object:
![](https://i.imgur.com/2UMraBG.png)

## Step 4
Once you have enabled Use Weapon Object, you will have an option to add a Weapon Object. This object should be a weapon gameobject attached to your AI's hand transform. Ensure that it is disabled after you have finished positioning it and applying it as the AI's Weapon Object.
![](https://i.imgur.com/jB7He0m.png)

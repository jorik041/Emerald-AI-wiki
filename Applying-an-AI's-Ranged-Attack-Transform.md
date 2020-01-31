# Applying an AI's Ranged Attack Transform
Emerald’s ranged combat system allows any AI the ability to use ranged combat all without having to program anything. Everything is handled within the editor and with Ability Objects. All users have to do is customize the Ability Object and its settings.

## Step 1
Go to the AI’s Settings>Combat>Damage Settings tab and set the AI’s Weapon Type to Ranged, if not already done. If you want to use both weapons types, the setup process is the same, just make sure you are in the Ranged Combat tab to see all of the ranged options and that you have all needed ranged animation applied within the AI's Animation tab.

![](https://i.imgur.com/ianHLlm.png)

## Step 2
You will need to assign the AI’s Ranged Attack Transform. This is the AI's bone transform where projectiles will be created and given speed to move towards a target. This can be anything such as an AI’s hand for magic effects, AI’s bow for arrows, or an AI’s gun/barrel for bullets.

![](https://i.imgur.com/3d6aAwq.png)

## Step 3
If you haven't already done so, you will need to create some Ability Objects for your AI to use. This is cover in the [Creating an Ability Object](https://github.com/Black-Horizon-Studios/Emerald-AI/wiki/Creating-an-AI-Ability-Object) section.
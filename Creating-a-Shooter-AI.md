# Creating a Shooter AI
Emerald AI features tons of customizable options to create nearly any AI imaginable. With this Emerald AI tutorial, you will be able to create your own shooter AI that can shoot bullets from their gun and aim their weapon at targets. This tutorial will require users to have their own shooter animated model and effects, but the setup process should universally apply to whatever you are using.

![](https://i.imgur.com/nbi1IEP.png)

## Step 1
If you haven't already done so, you will need to have an AI setup through Emerald AI's Setup Manager with all needed animations applied. This tutorial covers setting up specific shooter AI features, not setting up an AI as this is covered with the guides below:

* [Setting up an AI with the Setup Manager](https://github.com/Black-Horizon-Studios/Emerald-AI/wiki/Creating-an-AI-through-the-Setup-Manager)
* [Setting up an AI's Animations](https://github.com/Black-Horizon-Studios/Emerald-AI/wiki/Setting-up-an-AI's-Animations)

## Step 2
First, you will need to make sure there are no warning messages at the top of your AI's Emerald AI editor. If there are, you will need to resolve these before you continue. These can all be resolved by seeing the [Creating a New AI](https://github.com/Black-Horizon-Studios/Emerald-AI/wiki/Creating-a-New-AI) section. 

**Note:** The Setting up an AI's Ranged Attack Transform and Setting up an AI's Ability Object warnings can be ignored as these will be covered below.
![](https://i.imgur.com/sHdKbbV.png)

## Step 3
Now that your AI is mostly setup, we can focus on the settings that will allow your AI to shoot and aim their weapon.

Start off by creating and naming an Emerald AI Ability Object. This can be done by right clicking in the Project tab and going to Create>Emerald AI>Create>Ability Object. It is recommended that you create this in a custom folder for better organization some AI might have different types of bullets.
![](https://i.imgur.com/QpXMVEG.png)

## Step 4
Now that you have created your first Ability Object, you will need to customize the settings of your bullet to resemble that of a bullet. The first tab will specify the Ability Type as well as the ability's name and description. In order for a bullet to cause damage, you will have the Ability Type set to Damage, which should be set by default. The name and description can be customized how you want.
![](https://i.imgur.com/UtAEMow.png)

## Step 5

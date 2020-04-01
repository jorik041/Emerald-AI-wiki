# Creating a Shooter AI
Emerald AI features tons of customizable options to create nearly any AI imaginable. With this Emerald AI tutorial, you will be able to create your own shooter AI that can shoot bullets from their gun and aim their weapon at targets all without having to write a single line of code. This tutorial will require users to have their own shooter animated model and effects, but the setup process should universally apply to whatever you are using.

![](https://i.imgur.com/nbi1IEP.png)

If you haven't already done so, you will need to have an AI setup through Emerald AI's Setup Manager with all needed animations applied. This tutorial covers setting up specific shooter AI features, not setting up an AI as this is covered with the guides below.

**Note:** Your AI will need to be set to the Ranged Weapon Type so ensure this is done now and not later. Ranged and Melee AI have different animations.

* [Setting up an AI with the Setup Manager](https://github.com/Black-Horizon-Studios/Emerald-AI/wiki/Creating-an-AI-through-the-Setup-Manager)
* [Setting up an AI's Animations](https://github.com/Black-Horizon-Studios/Emerald-AI/wiki/Setting-up-an-AI's-Animations)

# Creating the Bullet/Projectile
This portion of the tutorial will cover creating a bullet/projectile using an Emerald AI Ability Object as well as applying this Ability Object to your AI. It's worth noting that an Ability Object can be shared between multiple AI (if desired) so you don't have to create one for each AI if they have the same weapon/bullets.

## Step 1
First, you will need to make sure there are no warning messages at the top of your AI's Emerald AI editor. If there are, you will need to resolve these before you continue. These can all be resolved by seeing the [Creating a New AI](https://github.com/Black-Horizon-Studios/Emerald-AI/wiki/Creating-a-New-AI) section. 

**Note:** The Setting up an AI's Ranged Attack Transform and Setting up an AI's Ability Object warnings can be ignored as these will be covered below.
![](https://i.imgur.com/sHdKbbV.png)

## Step 2
Now that your AI is mostly setup, we can focus on the settings that will allow your AI to shoot and aim their weapon.

Start off by creating and naming an Emerald AI Ability Object. This can be done by right clicking in the Project tab and going to Create>Emerald AI>Create>Ability Object. It is recommended that you create this in a custom folder for better organization some AI might have different types of bullets.
![](https://i.imgur.com/QpXMVEG.png)

## Step 3
Now that you have created your first Ability Object, you will need to customize the settings of your bullet to resemble that of a bullet. The Ability Info tab will specify the Ability Type as well as the ability's name and description. In order for a bullet to cause damage, you will have the Ability Type set to Damage, which should be set by default. The name, description, and even the icon can be customized how you want.
![](https://i.imgur.com/UtAEMow.png)

## Step 4
Next, go to the Ability Settings tab. Here, you will be able to customize all movement and collision related settings. You are free to customize these settings how you want, depending on what kind of bullet or projectile you want to create. For this tutorial, we will be creating a small, quick moving bullet so set the Projectile Speed to 70 and the Collider Radius to 0.1. You can also enable the Heat Seeking option for about a half a second to allow your AI to have better odds at hitting their targets. However, feel free to tweak these settings as needed.
![](https://i.imgur.com/Jei2eWx.png)

## Step 5
Lastly, go to the Ability Effects & Sounds tab. Here, you can customize the visual and sounds effects the ability will use. The Ability Effect object is the projectile object that will be actually fired from the AI. The Cast Effect can have a Muzzle Flash effect with a quick Cast Effect Timeout time. The Collision Effect can be used for a bullet impact. The Cast Sound can have a firing weapon sound used.
![](https://i.imgur.com/SkDzXdl.png)

## Step 6
Now, you will need to apply your newly created bullet (Ability Object) to your AI. To do this, go to the Emerald AI editor, go to the AI's Settings>Combat>Damage Settings tab, and go to the Abilities section. In the Offensive Abilities list, press the + button to create a new ability for the AI to use. This will allow you to customize the animation that will be used as well as the Ability Object that will be fired. The animations are based off of your AI's Ranged Attack Animation list. You will want to set the bullet we created earlier as the Ability Object.
![](https://i.imgur.com/N0WBd3V.png)
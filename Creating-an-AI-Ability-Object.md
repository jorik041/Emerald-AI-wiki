.markdown-preview.markdown-preview { p, ul, ol {font-size: 1.2em;} }

![](https://i.imgur.com/c3Snnsb.png)
# Creating an AI Ability Object
Ability Objects are customizable objects that can be used to create anything from spells, arrows for bows, bullets for guns, evening healing and summoning other AI. This guide will cover each category of Ability Objects; Offensive Abilities, Support Abilities, and Summoning Abilities. 
Note: If you have not already done so, it is recommended that you setup your Ranged Combat first with the guide. Attack animations need an Animation Event in order for abilities and attacks to be triggered: Setting up Ranged Combat 
To create an Ability Object, right click in the desired folder within the Project tab. Go to Emerald AI>Create>Ability Object. This will create a brand new ability for you to customize. Be sure to give it a name other than New Ability Object.
![](https://i.imgur.com/LPFq3TZ.gif)
 
&nbsp;

## Offensive Abilities
![](https://i.imgur.com/LGcaFAr.gif)

Offensive Abilities are abilities that allow the AI to shoot projectiles at their targets to cause damage. These can spells, arrows for bows, bullets for weapons, and much more. 
### Part 1
After you have created an Ability Object, ensure that the Ability Type is set to Damage. Customize the Ability Name, Description, and Icon as needed.

![](https://i.imgur.com/9ClweSH.png)

### Part 2
Now go to the Ability Settings tab. Here, you will be able to customize all of the Ability’s settings such as timers, damage amounts, and further functionality. Offensive Abilities also have options to make an ability have critical hits, be heat seeking, or even cause damage over time. Customize these settings as needed for your ability.

![](https://i.imgur.com/OZ9HYyz.png)

### Part 3
The Ability Effects & Sounds tab covers all effects and sounds that the ability will use. The only required effect is the Ability Effect as this is the actual object that will be fired at an AI’s target. 
Note: You will need to ensure that your Ability Effect doesn’t have any other components on it that can interfere with the detection process. This includes colliders and Rigidbody components. All components that are needed are added by Emerald AI when the ability is used. All users have to do is create and customize their abilities. 

![](https://i.imgur.com/PQpJSd3.png)

### Part 4
Once you are finished customizing your ability, you will need to add it to your AI. Remember that abilities can be shared between AI. To get to the AI’s Ability Lists section, go to AI’s Settings>Combat tab. 

Once you’ve navigated to the Abilities section, add your Offensive Ability Object to the Offensive Ability list. Be sure to properly organize your abilities so you don’t mistakenly add them to the wrong categories. 

The Offensive Animation is based off of your AI’s Ranged Attack Animation list. This allows you to choose which animation is used for each category of abilities. If you get an error stating there are no ranged attack animations, you will need to create an Animator Controller for your AI and/or apply the AI’s Ranged Attack Animations. If your AI only has one ranged attack animation, that’s okay. You can just use the same animation for each of the 3 categories. Lastly, only one category is required so all 3 do not have to be used.

![](https://i.imgur.com/IUS0RDf.gif)

### Part 5 
Abilities are automatically calculated to maximize an AI’s chance at survival. An AI will first attempt to heal, given that it has a Support Ability. Then an AI will attempt to use a Summon Ability, given that it has a Summon Ability. Lastly, it will attack with its Offensive Abilities. There are no limits to the amount of Ability Objects an AI can use.

![](https://i.imgur.com/ygPk0B0.gif)

&nbsp;

## Support Abilities
![](https://i.imgur.com/jjWSlNA.gif)

Support Abilities are abilities that allow the AI to heal them self if their healing threshold is met. Healing can happen instantly or over time. Support abilities outside of healing will come with future updates.

### Part 1 
After you have created an Ability Object, ensure that the Ability Type is set to Support. Customize the Ability Name, Description, and Icon as needed.

![](https://i.imgur.com/yK4loo8.png)

### Part 2
Now go to the Ability Settings tab. Here, you will be able to customize all of the Ability’s settings such as healing amount and if the cooldown length. Support Abilities also have an option to allow the ability to heal over time, if desired.

![](https://i.imgur.com/w6ba30D.png)

### Part 3
The Ability Effects & Sounds tab covers all effects and sounds that the ability will use. The only required effect is the Ability Effect as this will be the visual effect that is played when the AI heals. 
Note: You will need to ensure that your Ability Effect doesn’t have any other components on it that can interfere with the AI’s detection process. This includes colliders and Rigidbody components.

![](https://i.imgur.com/cM5VXzF.png)

### Part 4
Once you are finished customizing your ability, you will need to add it to your AI. Remember that abilities can be shared between AI. To get to the AI’s Ability Lists section, go to AI’s Settings>Combat tab. 

Once you’ve navigated to the Abilities section, add your Support Ability Object to the Support Ability list. Be sure to properly organize your abilities so you don’t mistakenly add them to the wrong categories. 

The Support Animation is based off of your AI’s Ranged Attack Animation list. This allows you to choose which animation is used for each category of abilities. If you get an error stating there are no ranged attack animations, you will need to create an Animator Controller for your AI and/or apply the AI’s Ranged Attack Animations. If your AI only has one ranged attack animation, that’s okay. You can just use the same animation for each of the 3 categories. Lastly, only one category is required so all 3 do not have to be used.

(Image Needed)

### Part 5
Abilities are automatically calculated to maximize an AI’s chance at survival. An AI will first attempt to heal, given that it has a Support Ability. Then an AI will attempt to use a Summon Ability, given that it has a Summon Ability. Lastly, it will attack with its Offensive Abilities. There are no limits to the amount of Ability Objects an AI can use.

(Image Needed)

&nbsp;

## Summoning Abilities
![](https://i.imgur.com/UDQokWI.gif)
Summoning Abilities are abilities that allow the AI to heal them self if their healing threshold is met. Healing can happen instantly or over time. Support abilities outside of healing will come with future updates.

### Part 1 
After you have created an Ability Object, ensure that the Ability Type is set to Summoning. Customize the Ability Name, Description, and Icon as needed.

![](https://i.imgur.com/vm5fJzZ.png)

### Part 2
Now go to the Ability Settings tab. Here, you will be able to customize all of the Ability’s settings such as the Summon Radius and Summon Length. If you do not want a summon length, you can set the value to an unreachable value.

![](https://i.imgur.com/t9sCn8V.png)

### Part 3
The Ability Effects & Sounds tab covers all effects and sounds that the ability will use. The only required effects are the Ability Effect and the Summon Object. The Summon Object must be a properly setup Emerald AI agent. Be sure to test the summoning object prior to applying it as a Summonable Object. 

**Note:** You will need to ensure that your Ability Effect doesn’t have any other components on it that can interfere with the AI’s detection process. This includes colliders and Rigidbody components.

![](https://i.imgur.com/ufKwuzu.png)

### Part 4
Once you are finished customizing your ability, you will need to add it to your AI. Remember that abilities can be shared between AI. To get to the AI’s Ability Lists section, go to AI’s Settings>Combat tab. 

Once you’ve navigated to the Abilities section, add your Summon Ability Object to the Summon Ability list. Be sure to properly organize your abilities so you don’t mistakenly add them to the wrong categories. 

The Summon Animation is based off of your AI’s Ranged Attack Animation list. This allows you to choose which animation is used for each category of abilities. If you get an error stating there are no ranged attack animations, you will need to create an Animator Controller for your AI and/or apply the AI’s Ranged Attack Animations. If your AI only has one ranged attack animation, that’s okay. You can just use the same animation for each of the 3 categories. Lastly, only one category is required so all 3 do not have to be used.

(Image Needed)

### Part 5
Abilities are automatically calculated to maximize an AI’s chance at survival. An AI will first attempt to heal, given that it has a Support Ability. Then an AI will attempt to use a Summon Ability, given that it has a Summon Ability. Lastly, it will attack with its Offensive Abilities. There are no limits to the amount of Ability Objects an AI can use.

(Image Needed)

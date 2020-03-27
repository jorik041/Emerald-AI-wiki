# Creating an AI through the Setup Manager
The Setup Manager allows users to quickly create AI by automating the process of applying all needed settings and components to the selected object. These settings include Emerald AI settings that are applied directly to the created AI. Once an AI has been created, you can adjust the settings as needed.

**Note:** With 2019+, a prefab object is required to be in your scene in order to be used with the Setup Manager. Not doing so will result in an error. This issue will be resolved with the upcoming 2.4 version of Emerald AI.

## Part 1
To open the Setup Manager, press Ctrl+Shift+E or go to Window>Emerald AI>Setup Manager within Unity.

<img src="https://i.imgur.com/Ht94ZmR.png" width="63%">

## Part 2
Apply the animated model you would like to create an AI with to the AI Object slot. Ensure that this object has an Animator with an Avatar on it and that it has no collider components.
<img src="https://i.imgur.com/G0KbGyX.png" width="59%">

![](https://i.imgur.com/fiZjrIq.png)

## Part 3
Next, assign the Unity Tags and Layers this AI's game object will use for detection and being detected. You can change these after an AI has been created, but it is important that they are setup correctly initially. The Tag cannot use Untagged and Layer cannot use Default.

![](https://i.imgur.com/mklSVUI.png)

## Part 4
The rest of the settings up until the Weapon Type can be setup as needed. The Weapon Type, Death Type, and Movement Type are important because they control the kind of animations your AI will use.

![](https://i.imgur.com/RILBPKN.png)

| Setting  | Description |
| ------------- | ------------- |
| Weapon Type  | The Weapon Type control whether the AI will use Melee, Ranged, or Both animation lists. This setting is important because the lists change depending on the Weapon Type. A common mistake is to leave the setting on Melee when your AI is Ranged. This mistake would require users to reapply all needed combat animations. Ensure this is initially set correctly to avoid extra work. |
| Death Type  | The Death Type controls whether the AI will use a Ragdoll or Death Animation on death. Using the Ragdoll option requires users to have a ragdoll setup up on the AI Object with Unity's Ragdoll Creator or other other custom system. The Animation Death Type requires applying the death animation to the AI's Death Animation List within the Animation Settings after the AI has been created. |
| Movement Type  | The Movement Type Controls whether the AI will use NavMesh or Root Motion driven movement. This is dependent on your AI's animations so ensure you are using the right settings with the right animations. |

## Part 5
The last setup is to press the press the "Setup AI" button at the bottom of the Setup Manager when you are finished setting up your object to be an AI. This will apply the settings you've set and apply all needed components. After this, you will still need to setup your AI's animations and apply a few more settings within the Emerald AI Editor. The Emerald AI editor will tell you what needs to be done next.
![](https://i.imgur.com/s5zFOQJ.png)
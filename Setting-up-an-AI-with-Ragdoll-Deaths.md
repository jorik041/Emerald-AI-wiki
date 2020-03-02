# Setting up an AI with Ragdoll Deaths
Ragdolls can be a great way to add dynamic deaths to your AI. Ragdoll deaths allow Unity's physics to drive your AI's deaths so their bodies collapse and react to their surrounding environment similar to games like Skyrim, Oblivion, Halo, etc. When an Emerald AI agent dies, their current animation will automatically blend with the AI's ragdoll physics.

![](https://i.imgur.com/DzkwhrF.gif)

## Step 1
To create a ragdoll on your AI, you will first need to use Unity's Built-in Ragdoll Wizard to create a ragdoll on your AI object. If you haven't already setup your AI through the Emerald AI Setup Manager, it is recommended that you do this first. A guide on this can be found here: [https://docs.unity3d.com/Manual/wizard-RagdollWizard.html](https://docs.unity3d.com/Manual/wizard-RagdollWizard.html)

The Ragdoll Wizard can be opened by going to GameObject>3D Object>Ragdoll... within Unity.

![](https://i.imgur.com/BMOFAkm.png)

## Step 2
After your AI has been through Unity's Ragdoll Wizard, it should look something like the below. 
![](https://i.imgur.com/p2hQfSv.png)

## Step 3
Emerald AI now needs to have the appropriate Death Type set in order for it to utilize the ragdoll components that have been assigned. To do this, go to your AI's Emerald AI editor and go to the AI's Settings>Combat>Combat Action tab. Go to the very bottom of this tab until you see the Death Type Setting.

![](https://i.imgur.com/k0AQamO.png)

Set this setting to Ragdoll. You can also set what Tag the ragdoll components will use, if desired.
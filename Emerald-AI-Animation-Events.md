# Emerald Animation Events
Animation Events allow you to call script functions at a particular frame within an Animation. Emerald AI has tons of API that can be called for added functionality.

## Creating Emerald AI Animation Events 
Animation Events allow for tons of added functionality to Emerald AI. This allows certain events or actions to be played at the exact frame they're needed, such as an attack animation hitting its target. Please familiarize yourself with how Animation Events with these Unity Guides before creating Animation Events, if you are unfamiliar with the process: 
1) https://docs.unity3d.com/Manual/AnimationEventsOnImportedClips.html 
2) https://docs.unity3d.com/540/Documentation/Manual/animeditor-AnimationEvents.html

This section will be broken down into multiple sections.


## Melee and Range Damage Animation Events
A video tutorial for creating Melee Attack and Ranged Attack Animation Events can be below. When creating an Animation Event, you will need to use the EmeraldAttackEvent function name (Note: The tutorial video uses an outdated function name so use EmeraldAttackEvent instead). If you do not create said Animation Event, you will receive an error telling you which Animation Event is needed.

<a href="http://www.youtube.com/watch?feature=player_embedded&v=s_lLt0xUrF8
" target="_blank"><img src="http://img.youtube.com/vi/s_lLt0xUrF8/0.jpg" 
alt="IMAGE ALT TEXT HERE" width="240" height="180" border="10" /></a>

 

## Walk and Run Sound Animation Events
Please familiarize yourself with how Animation Events with this Unity Guide before creating Animation Events, if you are unfamiliar with the process. https://docs.unity3d.com/Manual/AnimationEventsOnImportedClips.html
Footstep sound Animation Events are covered here: Footstep Sounds Tutorial


## Warning Sound Animation Events
Please familiarize yourself with how Animation Events with this Unity Guide before creating Animation Events, if you are unfamiliar with the process. https://docs.unity3d.com/Manual/AnimationEventsOnImportedClips.html
Warning Sounds can be played by finding the moment you want a warning sound to play on a taunt/warning animation and creating an PlayWarningSound Animation Event. Animation Events allow the sound to play consistently and exactly when needed. A Warning Sound is picked randomly based off of your AI’s Warning Sounds list.




## Attack Sound Animation Events
Please familiarize yourself with how Animation Events with this Unity Guide before creating Animation Events, if you are unfamiliar with the process. https://docs.unity3d.com/Manual/AnimationEventsOnImportedClips.html
Attack Sounds can be played by finding the moment you want an attack sound to play and creating an PlayAttackSound Animation Event. Animation Events allow the sound to play consistently and exactly when needed. An Attack Sound is picked randomly based off of your AI’s Attack Sounds list.
 


## Death Sound Animation Events (Animation Death Only)
Please familiarize yourself with how Animation Events with this Unity Guide before creating Animation Events, if you are unfamiliar with the process. https://docs.unity3d.com/Manual/AnimationEventsOnImportedClips.html
Death Sounds can be played by finding the moment you want a death sound to play on a death animation and creating an PlayDeathSound Animation Event. Animation Events allow the sound to play consistently and exactly when needed. A Death Sound is picked randomly based off of your AI’s Death Sounds list. If you are using Ragdoll deaths, these are played automatically when the AI dies.




## Play Sound ID Animation Events
Please familiarize yourself with how Animation Events with this Unity Guide before creating Animation Events, if you are unfamiliar with the process. https://docs.unity3d.com/Manual/AnimationEventsOnImportedClips.html
Each AI has its own Interact Sounds list located in the General Sounds tab. These allow users to have a list of sounds each with an ID that can be played programmatically or through Animation Events using said ID. These are especially useful for Emote animations.

These sounds can be useful for playing sounds on certain animation. Because they use Animation Events, you can pick the exact frame that they happen and it doesn’t require any additional coding.
To play a sound using an Animation Event, find the frame you would like a sound to play and create an Animation Event then use the Function PlaySoundEfffect. In the Int portion of this, use the Sound ID to specify which sound will be played. In this example, we’re using 7, which is the Drink sound from the image above. This helps with the believability of animations.



## Enable and Disable Interactive Items with Animation Events
Please familiarize yourself with how Animation Events with this Unity Guide before creating Animation Events, if you are unfamiliar with the process. https://docs.unity3d.com/Manual/AnimationEventsOnImportedClips.html
Each AI has its own Items list that can be customized to be used for things such as quests and interactive animations. The Items List can be found under AI’s Settings>Items tab. These allow users to have a list of items each with an ID that can be played programmatically or through Animation Events using said ID. These are especially useful for Emote animations to allow items to be enabled and disabled for an animation such as a cup for drinking water or an item for an AI’s work animation. Note: Typically, you will want the item attached to your AI. In this example, the bucket is attached to the AI’s left hand.

These sounds can be useful for enabling items on certain animation. Because they use Animation Events, you can pick the exact frame that they happen and it doesn’t require any additional coding.
To enable an item using an Animation Event, find the frame you would like the item to be enabled and create an Animation Event then use the Function EnableItem. In the Int portion of this, use the Item ID to specify which item from your item list will be enabled. In this example, we’re using 0, which is the Bucket item from the image above. This will enable the bucket item at this frame and it will stay enabled until you create a DisableItem Animation Event. For this example, a DisableItem Animation Event has been created at the end of this animation using the same Item ID so the bucket is only enabled for the length of this animation. This helps with the believability and realism of animations. Below this image, you can see the final result.

This example has an AI using waypoints placed on each plant. When the AI arrives to its waypoints, it plays its Work Idle animation. At the start of this animation, the bucket item is enabled and when the animation is about to end, it’s disabled. Additional Animation Events, such as Sound ID Animation Events, can also be used to add sound effects to the picking motion for even more believability.

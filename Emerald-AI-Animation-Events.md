# Emerald Animation Events
Animation Events allow you to call script functions at a particular frame within an Animation. Emerald AI has tons of API that can be called for added functionality.

## Creating Emerald AI Animation Events 
Animation Events allow for tons of added functionality to Emerald AI. This allows certain events or actions to be played at the exact frame they're needed, such as an attack animation hitting its target. Please familiarize yourself with how Animation Events with these Unity Guides before creating Animation Events, if you are unfamiliar with the process: 
1) https://docs.unity3d.com/Manual/AnimationEventsOnImportedClips.html 
2) https://docs.unity3d.com/540/Documentation/Manual/animeditor-AnimationEvents.html

&nbsp;

## Melee and Range Damage Animation Events
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
Find the exact frame you want the AI to cause damage with its attack animation, or use an Ability, and press the Create Event button. When you've done this, assign EmeraldAttackEvent as the function name. When you've finished this, press Apply. You will need to do this for each attack animation that's in your AI's Attack Animation List. This allows damage and ability events to trigger that looks and functions best for the AI's animation.

![](https://i.imgur.com/JfjwzXR.gif)

## Step 5
This should be all the you need to do to get AI to damage other AI or the player. Double check that the function name was entered correctly and that the attack animation is being used by the AI. AI will receive errors if an attack animation event is missing or was entered incorrectly.

&nbsp;

## Walk and Run Sound Animation Events
Footstep sound Animation Events are covered with the YouTube tutorial below.

<a href="http://www.youtube.com/watch?feature=player_embedded&v=pL5Z-f8COcY
" target="_blank"><img src="http://img.youtube.com/vi/pL5Z-f8COcY/0.jpg" 
alt="IMAGE ALT TEXT HERE" width="240" height="180" border="10" /></a>

&nbsp;

## Warning Sound Animation Events
Warning Sounds can be played by finding the moment you want a warning sound to play on a taunt/warning animation and creating an PlayWarningSound Animation Event. Animation Events allow the sound to play consistently and exactly when needed. A Warning Sound is picked randomly based off of your AI’s Warning Sounds list.

![](https://i.imgur.com/x5ttknT.png)

&nbsp;

## Attack Sound Animation Events
Attack Sounds can be played by finding the moment you want an attack sound to play and creating an PlayAttackSound Animation Event. Animation Events allow the sound to play consistently and exactly when needed. An Attack Sound is picked randomly based off of your AI’s Attack Sounds list.
 
![](https://i.imgur.com/VxaINQo.png)

&nbsp;

## Death Sound Animation Events (Animation Death Only)
Death Sounds can be played by finding the moment you want a death sound to play on a death animation and creating an PlayDeathSound Animation Event. Animation Events allow the sound to play consistently and exactly when needed. A Death Sound is picked randomly based off of your AI’s Death Sounds list. If you are using Ragdoll deaths, these are played automatically when the AI dies.

![](https://i.imgur.com/nNDw9Sx.png)

&nbsp;

## Play Sound ID Animation Events
Each AI has its own Interact Sounds list located in the General Sounds tab. These allow users to have a list of sounds each with an ID that can be played programmatically or through Animation Events using said ID. These are especially useful for Emote animations.

![](https://i.imgur.com/nmNktJO.png)

These sounds can be useful for playing sounds on certain animation. Because they use Animation Events, you can pick the exact frame that they happen and it doesn’t require any additional coding.
To play a sound using an Animation Event, find the frame you would like a sound to play and create an Animation Event then use the Function PlaySoundEfffect. In the Int portion of this, use the Sound ID to specify which sound will be played. In this example, we’re using 7, which is the Drink sound from the image above. This helps with the believability of animations.

![](https://i.imgur.com/g21doIq.png)

&nbsp;

## Enable and Disable Interactive Items with Animation Events
Each AI has its own Items list that can be customized to be used for things such as quests and interactive animations. The Items List can be found under AI’s Settings>Items tab. These allow users to have a list of items each with an ID that can be played programmatically or through Animation Events using said ID. These are especially useful for Emote animations to allow items to be enabled and disabled for an animation such as a cup for drinking water or an item for an AI’s work animation. Note: Typically, you will want the item attached to your AI. In this example, the bucket is attached to the AI’s left hand.

![](https://i.imgur.com/Nkwmwao.png)

These sounds can be useful for enabling items on certain animation. Because they use Animation Events, you can pick the exact frame that they happen and it doesn’t require any additional coding.
To enable an item using an Animation Event, find the frame you would like the item to be enabled and create an Animation Event then use the Function EnableItem. In the Int portion of this, use the Item ID to specify which item from your item list will be enabled. In this example, we’re using 0, which is the Bucket item from the image above. This will enable the bucket item at this frame and it will stay enabled until you create a DisableItem Animation Event. For this example, a DisableItem Animation Event has been created at the end of this animation using the same Item ID so the bucket is only enabled for the length of this animation. This helps with the believability and realism of animations. Below this image, you can see the final result.

![](https://i.imgur.com/fClYiQX.png)

This example has an AI using waypoints placed on each plant. When the AI arrives to its waypoints, it plays its Work Idle animation. At the start of this animation, the bucket item is enabled and when the animation is about to end, it’s disabled. Additional Animation Events, such as Sound ID Animation Events, can also be used to add sound effects to the picking motion for even more believability.

![](https://i.imgur.com/F2Nt7tt.gif)

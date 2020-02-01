# Emerald AI API
Emerald AI has tons of API that can be accessed to allow for added functionality, custom mechanics, and more. 

## Table of Contents
* [Getting Started](#getting-started)
* [Damaging an AI](#damaging-an-ai)
* [General API](#General-API)
   * [KillAI](#KillAI)
   * [ResetAI](#ResetAI)
   * [InstantlyRefillAIHeath](#InstantlyRefillAIHeath)
   * [ChangeBehavior](#ChangeBehavior)
   * [ChangeConfidenceLevel](#ChangeConfidenceLevel)
   * [ChangeWanderType](#ChangeWanderType)
   * [SetCombatTarget](#SetCombatTarget)
   * [SetFollowerTarget](#SetFollowerTarget)
   * [TameAI](#TameAI)
* [Movement  Destination API](#Movement--Destination-API)
   * [UpdateDynamicWanderPosition](#UpdateDynamicWanderPosition)
   * [SetDynamicWanderPosition](#SetDynamicWanderPosition)
   * [UpdateStartingPosition](#UpdateStartingPosition)
   * [SetDestination](#SetDestination)
   * [SetDestinationPosition](#SetDestinationPosition)
   * [StopMovement](#StopMovement)
   * [ResumeMovement](#ResumeMovement)
   * [StopFollowing](#StopFollowing)
   * [ResumeFollowing](#ResumeFollowing)
   * [CompanionGuardPosition](#CompanionGuardPosition)
* [Sound API](#Sound-API)
   * [PlaySoundClip](#PlaySoundClip)
   * [PlayIdleSound](#PlayIdleSound)
   * [PlayAttackSound](#PlayAttackSound)
   * [PlayWarningSound](#PlayWarningSound)
   * [PlayBlockSound](#PlayBlockSound)
   * [PlayDeathSound](#PlayDeathSound)
   * [WalkFootstepSound](#WalkFootstepSound)
   * [RunFootstepSound](#RunFootstepSound)
   * [PlayRandomSoundEffect](#PlayRandomSoundEffect)
   * [PlaySoundEffect](#PlaySoundEffect)
* [Items  Effect API](#Items--Effect-API)
   * [EnableItem](#EnableItem)
   * [DisableItem](#DisableItem)
   * [DisableAllItems](#DisableAllItems)
   * [EnableWeapon](#EnableWeapon)
   * [DisableWeapon](#DisableWeapon)
   * [SpawnAdditionalEffect](#SpawnAdditionalEffect)
   * [SpawnEffectOnTarget](#SpawnEffectOnTarget)
   * [SpawnBloodSplatEffect](#SpawnBloodSplatEffect)
   * [CreateDroppableWeapon](#CreateDroppableWeapon)
* [Animation API](#Animation-API)
   * [PlayEmoteAnimation](#PlayEmoteAnimation)
   * [LoopEmoteAnimation](#LoopEmoteAnimation)
   * [StopLoopEmoteAnimation](#StopLoopEmoteAnimation)
   * [OverrideIdleAnimation](#OverrideIdleAnimation)
   * [DisableOverrideIdleAnimation](#DisableOverrideIdleAnimation)
* [Utility API](#Utility-API)
   * [UpdateUIHealthBarColor](#UpdateUIHealthBarColor)
   * [UpdateUIHealthBarBackgroundColor](#UpdateUIHealthBarBackgroundColor)
   * [UpdateUINameColor](#UpdateUINameColor)
   * [UpdateUINameText](#UpdateUINameText)


***


&emsp;

## Getting Started
In order for Emerald AI's API to be accessed via code, users must reference their AI’s EmeraldAISystem component. Once this is accessed, users will need to find the EmeraldAIEventsManager that holds all of the AI’s API. 
It is recommended that you use the EmeraldAI namespace at the top of your scripts to make accessing the Emerald AI scripts easier using:
```c#
using EmeraldAI;
```

Next, you will want a reference to an AI’s events manager script. There is one that is located on each AI. This can be done using the following and should be called on Start:

```c#
EmeraldAIEventsManager EventsManager = GetComponent<EmeraldAIEventsManager>();
```

Now, when using the EventsManager variable, you can access all of an AI’s internal functions that allow you to control a wide variety of functionality. The following API is assumed you used the EventsManager variable name as your reference to the EmeraldAIEventsManager component.

Users can also use the EmeraldAISystem for altering an AI's variables directly.

```c#
EmeraldAISystem EmeraldComponent = GetComponent<EmeraldAISystem>();
```

For users who need a working example, please use the following script to get you started. (This script needs to be attached to your AI in order to work correctly)

```c#
using System.Collections;
using System.Collections.Generic;
using UnityEngine;
using EmeraldAI;

public class AccessEmeraldAIExample : MonoBehaviour
{
    EmeraldAISystem EmeraldComponent;
    EmeraldAIEventsManager EventsManager;

    //Get the EmeraldAISystem component and EmeraldAIEventsManager and store them as variables.
    void Start ()
    {
        EmeraldComponent = GetComponent<EmeraldAISystem>();
        EventsManager = EmeraldComponent.EmeraldEventsManagerComponent;
    }
    
    //Changes the AI's current behavior to Aggressive when pressing the H key.
    void Update()
    {
        if (Input.GetKeyDown(KeyCode.H))
        {
            EventsManager.ChangeBehavior(EmeraldAISystem.CurrentBehavior.Aggressive);
        }
    }
}
```

&emsp;

# Damaging an AI
If you’d like to apply damage to an AI directly, for something like a custom character controller, you can do so with the code below. It is assumed you have a reference to the hit target when doing so.

### Damage
Damages an AI with a customizable damage amount, Target Type, Transform to assign as target, and the amount of ragdoll force applied on death.
```c#
Damage (int DamageAmount, TargetType AttackersTargetType, Transform YourTargetsTransform, int RagdollForce)
```

Example:
```c#
//Damages an AI to the YourTargetReference object
if (YourTargetReference.GetComponent<EmeraldAI.EmeraldAISystem>() != null)
{
   YourTargetReference.GetComponent<EmeraldAI.EmeraldAISystem>().Damage(YourDamageAmount, EmeraldAI.EmeraldAISystem.TargetType.Player, YourPlayerTransform, 400);
}
```

***

&emsp;

# Emerald AI Events Manager API
Here's all of the usable Emerald AI Events Manager API. Some of these can be used as Animation Events, such as playing an attack sound or playing footstep sounds.

# General API
### KillAI
Instantly kills this AI
```c#
EventsManager.KillAI();
```

***

### ResetAI
Resets an AI to its default state. This is useful if an AI is being respawned or reused.
```c#
EventsManager.ResetAI();
```

***

### InstantlyRefillAIHeath
Refills the AI's health to full instantly
```c#
EventsManager.InstantlyRefillAIHeath();
```

***

### ChangeBehavior
Changes the AI's Behavior
```c#
EventsManager.ChangeBehavior(EmeraldAISystem.CurrentBehavior NewBehavior)
```
Example:
```c#
//Change the AI's current behavior to Passive
EventsManager.ChangeBehavior(EmeraldAISystem.CurrentBehavior.Passive);
```

***

### ChangeConfidenceLevel
Changes the AI's current Confidence level
```c#
EventsManager.ChangeConfidence(EmeraldAISystem.ConfidenceType NewConfidence)
```
Example:
```c#
//Change the AI's current confidence to Passive
EventsManager.ChangeConfidence(EmeraldAISystem.ConfidenceType.Brave);
```

***

### ChangeWanderType
Changes the AI's current Wander type
```c#
EventsManager.ChangeWanderType(EmeraldAISystem.WanderType NewWanderType)
```
Example:
```c#
//Change the AI's current Wander Type to Stationary
EventsManager.ChangeWanderType(EmeraldAISystem.WanderType.Stationary);
```

***

### SetCombatTarget
Assigns a new combat target for your AI to attack. Using this setting will override your AI's chase limit.
```c#
EventsManager.SetCombatTarget(Transform Target)
```

***

### SetFollowerTarget
Assigns a new follow target for your companion AI to follow.
```c#
EventsManager.SetFollowerTarget(Transform Target)
```

***

### TameAI
Tames the AI to become the Target object’s companion. Note: The tameable AI must have a Cautious Behavior Type and a Brave or Foolhardy Confidence Type. The AI must be tamed before the AI turns Aggressive to be successful.
```c#
EventsManager.TameAI(Transform Target)
```

***


&nbsp;


# Movement & Destination API
### UpdateDynamicWanderPosition
Update the AI's dynamic wandering position to the AI's current position.
```c#
EventsManager.UpdateDynamicWanderPosition();
```

***

### SetDynamicWanderPosition
Sets the AI's dynamic wandering position to the position of the Destination transform. This is useful for functionality such as custom AI schedules. Note: This will automatically change your AI's Wander Type to Dynamic.
```c#
EventsManager.SetDynamicWanderPosition(Transform Destination)
```

***

### UpdateStartingPosition
Updates the AI's starting position to the AI's current position.
```c#
EventsManager.UpdateStartingPosition()
```

***

### SetDestination
Sets the AI's destination using a transform's position.
```c#
EventsManager.SetDestination(Transform Destination)
```

***

### SetDestinationPosition
Sets the AI's destination using a Vector3 position.
```c#
EventsManager.SetDestinationPosition(Vector3 DestinationPosition)
```

***

### StopMovement
Stops an AI from moving. This is useful for functionality like dialogue.
```c#
EventsManager.StopMovement();
```

***

### ResumeMovement
Resumes an AI's movement after using the StopMovement function.
```c#
EventsManager.ResumeMovement();
```

***

### StopFollowing
Stops a Companion AI from moving.
```c#
EventsManager.StopFollowing();
```

***

### ResumeFollowing
Allows a Companion AI to resume following its follower.
```c#
EventsManager.ResumeFollowing();
```

***

### CompanionGuardPosition
Allows a Companion AI to guard the assigned position.
```c#
EventsManager.CompanionGuardPosition(Vector3 PositionToGuard)
```

***


&nbsp;

# Sound API
### PlaySoundClip
Plays a sound clip according to the Clip parameter.
```c#
EventsManager.PlaySoundClip(AudioClip Clip)
```

***

### PlayIdleSound
Plays a random attack sound based on your AI's Attack Sounds list. Can also be called through Animation Events.
```c#
EventsManager.PlayIdleSound();
```

***

### PlayAttackSound
Plays a random attack sound based on your AI's Attack Sounds list. Can also be called through Animation Events.
```c#
EventsManager.PlayAttackSound();
```

***

### PlayWarningSound
Plays a random attack sound based on your AI's Attack Sounds list. Can also be called through Animation Events.
```c#
EventsManager.PlayWarningSound();
```

***

### PlayBlockSound
Plays a random block sound based on your AI's Block Sounds list.
```c#
EventsManager.PlayBlockSound();
```

***

### PlayDeathSound
Plays a random death sound based on your AI's Death Sounds list. Can also be called through Animation Events.
```c#
EventsManager.PlayDeathSound();
```

***

### WalkFootstepSound
Plays a footstep sound from the AI's Footstep Sounds list to use when the AI is walking. This should be setup through an Animation Event.
```c#
EventsManager.WalkFootstepSound();
```

***

### RunFootstepSound
Plays a footstep sound from the AI's Footstep Sounds list to use when the AI is running. This should be setup through an Animation Event.
```c#
EventsManager.RunFootstepSound();
```

***

### PlayRandomSoundEffect
Plays a random sound effect from the AI's General Sounds list.
```c#
EventsManager.PlayRandomSoundEffect();
```

***

### PlaySoundEffect
Plays a sound effect from the AI's General Sounds list using the Sound Effect ID as the parameter. This is useful for creating sounds with Animation Events such an interaction sound.
```c#
EventsManager.PlaySoundEffect(int SoundEffectID)
```

***


&emsp;

# Items & Effect API

### EnableItem
Enables an item from your AI's Item list using the Item ID.
```c#
EventsManager.EnableItem(int ItemID)
```

***

### DisableItem
Disables an item from your AI's Item list using the Item ID.
```c#
EventsManager.DisableItem(int ItemID)
```

***

### DisableAllItems
Disables all items from your AI's Item list.
```c#
EventsManager.DisableAllItems()
```

***

### EnableWeapon
Enables the AI's weapon object and plays the AI's equip sound effect, if one is applied.
```c#
EventsManager.EnableWeapon()
```

***

### DisableWeapon
Disables the AI's weapon object and plays the AI's unequip sound effect, if one is applied.
```c#
EventsManager.DisableWeapon()
```

***

### SpawnAdditionalEffect
Spawns an additional effect object at the position of the AI's Blood Spawn Offset position.
```c#
EventsManager.SpawnAdditionalEffect(GameObject EffectObject)
```

***

### SpawnEffectOnTarget
Spawns an effect object at the position of the AI's target.
```c#
EventsManager.SpawnEffectOnTarget(GameObject EffectObject)
```

***

### SpawnBloodSplatEffect
Spawns a blood splat effect object at the position of the AI's Blood Spawn Offset position. The rotation of this object is then randomized and adjusted based off of your attacker's current location.
```c#
EventsManager.SpawnBloodSplatEffect(GameObject BloodSplatObject)
```

***

### CreateDroppableWeapon
Instantiates an AI's Droppable Weapon Object on death (This should be a prefab object).
```c#
EventsManager.CreateDroppableWeapon()
```


***


&emsp;

# Animation API
### PlayEmoteAnimation
Plays an emote animation according to the Animation Clip parameter. Note: This function will only work if an AI is not in active combat mode. Up to 10 emote animations are supported.
```c#
EventsManager.PlayEmoteAnimation(int EmoteAnimationID)
```

***

### LoopEmoteAnimation
Loops an emote animation according to the Animation Clip parameter until it is called to stop. Note: This function will only work if an AI is not in active combat mode. Up to 10 emote animations are supported.
```c#
EventsManager.LoopEmoteAnimation(int EmoteAnimationID)
```

***

### StopLoopEmoteAnimation
Loops an emote animation according to the Animation Clip parameter until it is called to stop. Note: This function will only work if an AI is not in active combat mode.
```c#
EventsManager.StopLoopEmoteAnimation(int EmoteAnimationID)
```

***

### OverrideIdleAnimation
Manually sets the AI's next Idle animation instead of being generated randomly. This is useful for functionality such as playing a particular idle animation at a certain location such as for an AI's schedule. Note: The animation numbers are from 1 to 6 and must exist in your AI's Idle Animation list. You must call DisableOverrideIdleAnimation() to have idle animations randomly generate again and to disable this feature.
```c#
EventsManager.OverrideIdleAnimation(int IdleIndex)
```

***

### DisableOverrideIdleAnimation
Disables the OverrideIdleAnimation feature.
```c#
EventsManager.DisableOverrideIdleAnimation()
```


***


&emsp;

# Utility API
### UpdateUIHealthBarColor
Updates the AI's Health Bar color
```c#
EventsManager.UpdateUIHealthBarColor(Color NewColor)
```

***

### UpdateUIHealthBarBackgroundColor
Updates the AI's Health Bar Background color
```c#
EventsManager.UpdateUIHealthBarBackgroundColor(Color NewColor)
```

***

### UpdateUINameColor
Updates the AI's Name color
```c#
EventsManager.UpdateUINameColor(Color NewColor)
```

***

### UpdateUINameText
Updates the AI's Name text
```c#
EventsManager.UpdateUINameText(string NewName)
```

***

&emsp;

# Emerald AI **Unity** Events
Emerald AI has 10 built-in Unity Events that called during various Emerald AI actions. You can use these events to trigger custom function calls and other mechanics to expand functionality with AI.

## Creating Emerald AI Unity Event through the Editor
The Emerald AI Unity Events can be found on the AI's Settings>Events tab. Here. you will see 2 tabs; one for General Events and one for Combat Events. Each Event has + and - button that allows you to add or remove an event. When the + button is pressed, it will create a new blank element event for that Event List. This will allow you to apply a script, that's attached to your AI, to call custom functions or Emerald AI's API functions. 

![](https://i.imgur.com/mZu6IOY.png)


## Creating Emerald AI Unity Event through Code
Emerald AI's Unity Events are located on the EmeraldAISystem script. To access these, you will need a reference to the EmeraldAISystem script. This can be done using the code below. It is best to have a class level variable for EmeraldComponent so it can be accessed anywhere within your script.

```c#
EmeraldComponent = GetComponent<EmeraldAISystem>();
```

You can add Emerald AI Unity Events programmatically using the following code format. These should be applied on Start.

```c#
EmeraldComponent.TheEmeraldAIUnityEvent.AddListener(() => { YourFunctionToCall(); });
```

For example, lets say you want to track each AI death and add it to a static variable so the player can track their kills. For this example, lets say the kill count script name is KillCounterSystem and the static variable is an int called AmountOfKills.
```c#
...
void Start ()
{
   //Create a DeathEvent by adding a listener and applying the CountDeath function.
   //Even though this is assigned on start, the CountDeath function will be called when the AI dies.
   EmeraldComponent.DeathEvent.AddListener(() => { CountDeath(); });
}

//The CountDeath function adds the AI's death to the static variable AmountOfKills for tracking kills.
void CountDeath ()
{
   KillCounterSystem.AmountOfKills++;
}
...
```

***

### DeathEvent
The DeathEvent is invoked when an AI is killed.

Example:
```c#
EmeraldComponent.DeathEvent.AddListener(() => { YourCustomFunction(); });
```

***

### DamageEvent
The DamageEvent is invoked each time an AI is damaged.

Example:
```c#
EmeraldComponent.DeathEvent.AddListener(() => { YourCustomFunction(); });
```

***

### ReachedDestinationEvent
The ReachedDestinationEvent is invoked when an AI reaches their destination location (must be using the Destination Wander Type).

Example:
```c#
EmeraldComponent.ReachedDestinationEvent.AddListener(() => { YourCustomFunction(); });
```

***

### OnStartEvent
The OnStartEvent is invoked once within the AI's Start function.

Example:
```c#
EmeraldComponent.OnStartEvent.AddListener(() => { YourCustomFunction(); });
```

***

### OnEnabledEvent
The OnEnabledEvent is invoked when an AI is enabled after it has been deactivated.

Example:
```c#
EmeraldComponent.OnEnabledEvent.AddListener(() => { YourCustomFunction(); });
```

***

### OnPlayerDetectionEvent
The OnPlayerDetectionEvent is invoked when an AI detects a player object. Users can adjust the cooldown for how often this event is invoked within the Emerald AI editor.

Example:
```c#
EmeraldComponent.OnPlayerDetectionEvent.AddListener(() => { YourCustomFunction(); });
```

***

### OnAttackEvent
The OnAttackEvent is invoked when an AI triggers their attack animation.

Example:
```c#
EmeraldComponent.OnAttackEvent.AddListener(() => { YourCustomFunction(); });
```

***

### OnFleeEvent
The OnFleeEvent is invoked when an AI begins to flee (This only happens with AI that have a Brave or Coward Confidence Level). 

Example:
```c#
EmeraldComponent.OnFleeEvent.AddListener(() => { YourCustomFunction(); });
```

***

### OnStartCombatEvent
The OnStartCombatEvent is invoked when an AI first enters combat and is reset when the battle is over.

Example:
```c#
EmeraldComponent.OnStartCombatEvent.AddListener(() => { YourCustomFunction(); });
```

***

### OnKillTargetEvent
The OnKillTargetEvent is invoked when an AI has killed their target. This event is called before an AI's target has been cleared so it can still be accessed if needed.

Example:
```c#
EmeraldComponent.OnKillTargetEvent.AddListener(() => { YourCustomFunction(); });
```

***


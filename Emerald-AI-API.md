# Emerald AI API
Emerald AI has tons of API that can be accessed to allow for added functionality, custom mechanics, and more. 

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

# Emerald AI Events Manager API
Here's all of the usable Emerald AI Events Manager API.

## General API
Instantly kills this AI
```c#
EventsManager.KillAI();
```

Resets an AI to its default state. This is useful if an AI is being respawned or reused.
```c#
EventsManager.ResetAI();
```

Refills the AI's health to full instantly
```c#
EventsManager.InstantlyRefillAIHeath ();
```

Changes the AI's Behavior
```c#
EventsManager.ChangeBehavior(EmeraldAISystem.CurrentBehavior NewBehavior)
```

Changes the AI's Confidence
```c#
EventsManager.ChangeConfidence(EmeraldAISystem.ConfidenceType NewConfidence)
```

Changes the AI's Wander type
```c#
EventsManager.ChangeWanderType(EmeraldAISystem.WanderType NewWanderType)
```

Assigns a new combat target for your AI to attack. Using this setting will override your AI's chase limit.
```c#
EventsManager.SetCombatTarget(Transform Target)
```

Assigns a new follow target for your companion AI to follow.
```c#
EventsManager.SetFollowerTarget(Transform Target)
```

Tames the AI to become the Target object’s companion. Note: The tameable AI must have a Cautious Behavior Type and a Brave or Foolhardy Confidence Type. The AI must be tamed before the AI turns Aggressive to be successful.
```c#
EventsManager.TameAI(Transform Target)
```


## Movement & Destination API
//Update the AI's dynamic wandering position to the AI's current positon.
EventsManager.UpdateDynamicWanderPosition()

//Sets the AI's dynamic wandering position to the position of the Destination transform. This is useful for functionality such as custom AI schedules. Note: This will automatically change your AI's Wander Type to Dynamic.
EventsManager.SetDynamicWanderPosition(Transform Destination)

//Updates the AI's starting position to the AI's current position.
EventsManager.UpdateStartingPosition()

//Sets the AI's destination using a transform's position.
EventsManager.SetDestination(Transform Destination)

//Sets the AI's destination using a Vector3 position.
EventsManager.SetDestinationPosition(Vector3 DestinationPosition)

//Stops an AI from moving. This is useful for functionality like dialogue.
EventsManager.StopMovement()

//Resumes an AI's movement after using the StopMovement function.
EventsManager.ResumeMovement()

//Stops a Companion AI from moving.
EventsManager.StopFollowing()

//Allows a Companion AI to resume following its follower.
EventsManager.ResumeFollowing()

//Allows a Companion AI to guard the assigned position.
EventsManager.CompanionGuardPosition(Vector3 PositionToGuard)

Sound API
//Plays a sound clip according to the Clip parameter.
EventsManager.PlaySoundClip(AudioClip Clip)

//Plays a random attack sound based on your AI's Attack Sounds list. Can also be called through Animation Events.
EventsManager.PlayIdleSound()

//Plays a random attack sound based on your AI's Attack Sounds list. Can also be called through Animation Events.
EventsManager.PlayAttackSound()

//Plays a random attack sound based on your AI's Attack Sounds list. Can also be called through Animation Events.
EventsManager.PlayWarningSound()

//Plays a random block sound based on your AI's Block Sounds list.
EventsManager.PlayBlockSound()

//Plays a random death sound based on your AI's Death Sounds list. Can also be called through Animation Events.
EventsManager.PlayDeathSound()

//Plays a footstep sound from the AI's Footstep Sounds list to use when the AI is walking. This should be setup through an Animation Event.
EventsManager.WalkFootstepSound()

//Plays a footstep sound from the AI's Footstep Sounds list to use when the AI is running. This should be setup through an Animation Event.
EventsManager.RunFootstepSound()

//Plays a random sound effect from the AI's General Sounds list.
EventsManager.PlayRandomSoundEffect()

//Plays a sound effect from the AI's General Sounds list using the Sound Effect ID as the parameter. This is useful for creating sounds with Animation Events such an interaction sound.
EventsManager.PlaySoundEffect(int SoundEffectID)


Items & Effect API
//Enables an item from your AI's Item list using the Item ID.
EventsManager.EnableItem(int ItemID)

//Disables an item from your AI's Item list using the Item ID.
EventsManager.DisableItem(int ItemID)

//Disables all items from your AI's Item list.
EventsManager.DisableAllItems()

//Enables the AI's weapon object and plays the AI's equip sound effect, if one is applied.
EventsManager.EnableWeapon()

//Disables the AI's weapon object and plays the AI's unequip sound effect, if one is applied.
EventsManager.DisableWeapon()

//Spawns an additional effect object at the position of the AI's Blood Spawn Offset position.
EventsManager.SpawnAdditionalEffect(GameObject EffectObject)

//Spawns an effect object at the position of the AI's target.
EventsManager.SpawnEffectOnTarget(GameObject EffectObject)

//Spawns a blood splat effect object at the position of the AI's Blood Spawn Offset position. The rotation of this object is then randomized and adjusted based off of your attacker's current location.
EventsManager.SpawnBloodSplatEffect(GameObject BloodSplatObject)

//Instantiates an AI's Droppable Weapon Object on death (This should be a prefab object).
EventsManager.CreateDroppableWeapon()


Animation API
//Plays an emote animation according to the Animation Clip parameter. Note: This function will only work if an AI is not in active combat mode.
EventsManager.PlayEmoteAnimation(int EmoteAnimationID)

//Loops an emote animation according to the Animation Clip parameter until it is called to stop. Note: This function will only work if an AI is not in active combat mode.
EventsManager.LoopEmoteAnimation(int EmoteAnimationID)
//Loops an emote animation according to the Animation Clip parameter until it is called to stop. Note: This function will only work if an AI is not in active combat mode.
EventsManager.StopLoopEmoteAnimation(int EmoteAnimationID)

//Manually sets the AI's next Idle animation instead of being generated randomly. This is useful for functionality such as playing a particular idle animation at a certain location such as for an AI's schedule. Note: The animation numbers are from 1 to 3 and must exist in your AI's Idle Animation list. You must call DisableOverrideIdleAnimation() to have idle animations randomly generate again and to disable this feature.
EventsManager.OverrideIdleAnimation(int IdleIndex)

//Disables the OverrideIdleAnimation feature.
EventsManager.DisableOverrideIdleAnimation()


Utility API
//Updates the AI's Health Bar color
EventsManager.UpdateUIHealthBarColor(Color NewColor)

//Updates the AI's Health Bar Background color
EventsManager.UpdateUIHealthBarBackgroundColor(Color NewColor)

//Updates the AI's Name color
EventsManager.UpdateUINameColor(Color NewColor)

//Updates the AI's Name text
EventsManager.UpdateUINameText(string NewName)

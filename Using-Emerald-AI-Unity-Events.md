# Using Emerald AI **Unity** Events
Emerald AI has 11 built-in Unity Events that are called during various Emerald AI actions. You can use these events to trigger custom function calls and other mechanics to expand functionality with AI.

## Creating Emerald AI Unity Event through the Editor
The Emerald AI Unity Events can be found on the AI's Settings>Events tab. Here, you will see 2 tabs; one for General Events and one for Combat Events. Each Event has + and - button that allows you to add or remove an event. When the + button is pressed, it will create a new blank element event for that Event List. This will allow you to apply the AI gameobject as the reference object, to call any custom function or Emerald AI's API functions that are available on your AI.

![](https://i.imgur.com/mZu6IOY.png)

An empty Emerald AI Unity Event:
![](https://i.imgur.com/ODl6O2D.png)

Creating a new, unassigned, Emerald AI Unity Event after pressing the + button:
![](https://i.imgur.com/cyOyoGo.png)

Assigning your AI object as the object reference on the Emerald AI Unity Event:
![](https://i.imgur.com/FI5K7mN.png)

All available scripts, functions, components, and API on reference object for the Emerald AI Unity Event. An Emerald AI Unity Event is called when the specified event is invoked. In this Event's case, it's each time the AI is damaged.

![](https://i.imgur.com/drISY3c.png)


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

### OnTakeDamageEvent
The OnTakeDamageEvent is invoked each time an AI is damaged.

Example:
```c#
EmeraldComponent.DamageEvent.AddListener(() => { YourCustomFunction(); });
```

***

### OnDoDamageEvent
The OnDoDamageEvent is invoked each time an AI deals damage for both Melee and Ranged weapon types.

Example:
```c#
EmeraldComponent.OnDoDamageEvent.AddListener(() => { YourCustomFunction(); });
```

***

### OnReachedDestinationEvent
The OnReachedDestinationEvent is invoked when an AI reaches their destination location (must be using the Destination Wander Type).

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


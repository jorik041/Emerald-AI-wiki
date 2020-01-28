# Emerald AI Editor
Emerald AI's Editor is self-documented so almost everything is explained right within the editor. This wiki section will cover some of the editor functionality that may need further clarification or information.


# Temperament
An AI’s Temperament controls various settings on how an AI reacts to targets. Emerald makes things easy by having 5 preset behaviors that your AI can follow. They also have a Confidence level that gives you further control to make your AI’s Behavior more unique and customizable. What an AI does with its Confidence Level varies based on its Behavior Type. Below, these settings will be further explained.

## Behavior
The Behaviors option can be found within the Temperament tab. Each AI can be set to have 1 of 5 different behaviors. The behavior of an AI determines how it will react to other AI and players.
![](https://i.imgur.com/O4unmr4.png)

| Behavior Type  | Description |
| ------------- | ------------- |
| Passive  | Passive AI will not attack. They will simply wander around. If they are attacked, they will react according to their Confidence Level which is either to fight back or flee.  |
| Cautious  | Cautious AI will either flee or act territorial depending on their Confidence Level. Territorial AI will warn targets before attacking their target. An AI is set as territorial if their Confidence Level is set to Brave or higher.  |
| Companion  | Companion AI will follow around a target and help them fight. Companion AI will wander until their follow target is set. This is best done with a script and calling the public function SetTarget.  |
| Aggressive  | Aggressive AI will attack any target of the opposing faction that comes within their trigger radius. Aggressive AI must have AI Attacks Player checked in order to attack players.  |
| Pet  | Pet AI will follow around a player target. They will not fight, engage in combat, or be targeted. They are simply for cosmetic purposes.  |

***

## Confidence
The Confidence option can be found within the Temperament tab. What an AI does with its Confidence Level varies based on its Behavior Type. So, each Confidence Type has been categorized by Behavior Type. Note: The Pet and Companion Behavior Types do not use the Confidence Level setting.

![](https://i.imgur.com/gtspkmn.png)

### Cautious AI
| Confidence Level  | Description |
| ------------- | ------------- |
| Coward  | Content Cell  |
| Brave  | Cautious AI will become territorial when a target enters their trigger radius. If the target doesn't leave its radius before its territorial seconds have been reached, the AI will attack the target. They will attempt to flee once its health reaches the percentage you've set.  |
| Foolhardy  | Cautious AI will become territorial when a target enters their trigger radius. If the target doesn't leave its radius before its territorial seconds have been reached, the AI will attack the target. This AI will never flee and continue to fight until dead or the target has escaped the AI.  |

### Passive AI
| Confidence Level  | Description |
| ------------- | ------------- |
| Coward  | Passive AI will wander according to their wander settings, but only flee when attacked.  |
| Brave  | Passive AI will wander according to their wander settings, but only attack when attacked. They will attempt to flee once its health reaches the percentage you've set.  |
| Foolhardy  | Passive AI will wander according to their wander settings, but only attack when attacked. They will never flee and continue to fight until dead or the target has escaped the AI.  |

### Aggressive AI
| Confidence Level  | Description |
| ------------- | ------------- |
| Coward  | Aggressive AI cannot be set to Coward. AI with this setting will automatically be set to Brave on Start.  |
| Brave  | Aggressive AI will fight any target on sight or detection, but attempt to flee once its health reaches the percentage you've set.  |
| Foolhardy  | Aggressive AI will fight any target on sight or detection and will never flee. They will continue to fight until dead or the target has escaped the AI.  |

***

## Wander Type
The Wander Type option can be found within the Temperament tab. The Wander Type determines how your AI will wander when not in combat.
![](https://i.imgur.com/I9kbWYX.png)

| Wander Type  | Description |
| ------------- | ------------- |
| Dynamic  | Allows an AI to randomly wander by dynamically generate waypoints around their Wander Radius.  |
| Waypoints  | Allows you to define waypoints that the AI will move between.  |
| Stationary  | Allows an AI to stay stationary in the same position and will not move unless a target enters their trigger radius.  |
| Destination  | Allows an AI to travle to a single destination. Once it reaches it destination, it will stay stationary.  |
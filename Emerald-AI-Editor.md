# Temperament
An AI’s Temperament controls various settings of how an AI reacts to targets. Emerald makes things easy by having 5 preset behaviors that your AI can follow. They also have a Confidence level that gives you further control to make your AI’s Behavior more unique and customizable. What an AI does with its Confidence Level varies based on its Behavior Type. Below, these settings will be further explained.

## Behavior
The Behaviors option can be found within the Temperament tab. Each AI can be set to have 1 of 5 different behaviors. The behavior of an AI determines how it will react to other AI and players.
![](https://i.imgur.com/O4unmr4.png)

### Passive Behavior
Passive AI will not attack. They will simply wander around. If they are attacked, they will react according to their Confidence Level which is either to fight back or flee.

### Cautious Behavior
Cautious AI will either flee or act territorial depending on their Confidence Level. Territorial AI will warn targets before attacking their target. An AI is set as territorial if their Confidence Level is set to Brave or higher.

### Companion Behavior
Companion AI will follow around a target and help them fight. Companion AI will wander until their follow target is set. This is best done with a script and calling the public function SetTarget.

### Aggressive Behavior
Aggressive AI will attack any target of the opposing faction that comes within their trigger radius. Aggressive AI must have AI Attacks Player checked in order to attack players.

### Pet Behavior
Pet AI will follow around a player target. They will not fight, engage in combat, or be targeted. They are simply for cosmetic purposes.

## Confidence
The Confidence option can be found within the Temperament tab. What an AI does with its Confidence Level varies based on its Behavior Type. So, each Confidence Type has been categorized by Behavior Type. Note: The Pet and Companion Behavior Types do not use the Confidence Level setting.

### Cautious AI
**Coward** Cautious AI will flee when they encounter a target.

**Brave** Cautious AI will become territorial when a target enters their trigger radius. If the target doesn't leave its radius before its territorial seconds have been reached, the AI will attack the target. They will attempt to flee once its health reaches the percentage you've set.

**Foolhardy** Cautious AI will become territorial when a target enters their trigger radius. If the target doesn't leave its radius before its territorial seconds have been reached, the AI will attack the target. This AI will never flee and continue to fight until dead or the target has escaped the AI.

### Passive AI
**Coward** Passive AI will wander according to their wander settings, but only flee when attacked.

**Brave** Passive AI will wander according to their wander settings, but only attack when attacked. They will attempt to flee once its health reaches the percentage you've set.

**Foolhardy** Passive AI will wander according to their wander settings, but only attack when attacked. They will never flee and continue to fight until dead or the target has escaped the AI.

### Aggressive AI
**Coward**
Aggressive AI cannot be set to Coward. AI with this setting will automatically be set to Brave on Start.

**Brave** Aggressive AI will fight any target on sight or detection, but attempt to flee once its health reaches the percentage you've set.

**Foolhardy** Aggressive AI will fight any target on sight or detection and will never flee. They will continue to fight until dead or the target has escaped the AI.


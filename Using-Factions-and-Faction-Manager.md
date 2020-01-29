# Factions and Faction Manager
The Faction Manager allows users to create and remove factions that are globally available for AI to use. Factions will be available through the Emerald AI Editor to assign to your AI agents. You can also assign the relation of each faction to determine who is an enemy, an ally, or neutral.

## Creating a Faction with the Faction Manager
First, you will need to open the Faction Manager. This can be done by pressing Ctrl+Shift+R or by gong to Window>Emerald AI>Faction Manager within Unity. To create a new faction, simply type out a faction in the Faction Name area and press “Add Faction”. When you do this, you will see the newly created faction added to the Current Factions list. You can add or remove factions at anytime. The default factions that are included do not have to be used.
![](https://i.imgur.com/UGpZk0C.gif)

&nbsp;

## Assigning a Faction to an AI
Each AI can be assigned a Faction based off of the list of available factions created with the Faction Manager. The Faction Manager can be opened by pressing the Open Faction Manager button below the Faction setting. Each time you add or remove a faction through the Faction Manager, an AI's Faction dropdown list of available faction will be updated. An AI's Faction is the name used to control combat reaction with other AI. This is the name other AI will use when looking for opposing targets.

![](https://i.imgur.com/HE2nep8.png)

&nbsp;

## Setting up Faction Relations
### Player Relation
An AI's Faction Relations determines an AI's relation to each faction you assign within this list. Not all faction have to be assigned. AI who do not have an assigned faction will simply ignored as if they were natural, even if the target is aggressive.

| Relation  | Description |
| ------------- | ------------- |
| Enemy  | An AI with an Enemy relation to the player will be considered a threat and the AI will react according to its Behavior Type.  |
| Neutral  | An AI with an Neutral relation to the player will not be attacked by the AI and will be considered passive.  |
| Friendly  | An AI with an Friendly relation to the player will be considered friendly. This relation can be used for custom mechanics such as quest offers, special dialogue, or items. See the Emerald API section for code examples.  |

![](https://i.imgur.com/r02SypV.png)


### AI Relations
An AI's Faction Relations determines an AI's relation to each faction you assign within this list. Not all faction have to be assigned. AI who do not have an assigned faction will simply ignored as if they were natural, even if the target is aggressive.

| Relation  | Description |
| ------------- | ------------- |
| Enemy  | Any AI with a relation of Enemy will be considered a threat and the AI will react according to its Behavior Type.  |
| Neutral  | Any AI with a relation of Neutral will be simply be ignored. This relation can be helpful to for quests or custom mechanics.  |
| Friendly  | Any AI with a relation of Friendly will be ignored, but can have special conditions such as leading to new information or quests.  |

![](https://i.imgur.com/QzKefU3.png)
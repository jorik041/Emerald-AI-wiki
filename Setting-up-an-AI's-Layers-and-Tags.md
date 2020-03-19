# Setting up an AI's Layers and Tags
An AI's needs to be assigned Unity Tags and Layers as well as which Unity Tags and Layers will be used in the detection process. 
**Note:** The Unity Tag and Layers are different than Emerald AI's Factions System. The player's layer will also need to be defined within the AI's Detection Layers. The player's tag is defined within the Faction Options tab.

## Step 1
You can assign the Unity Tags and Layers the AI uses at the top of the game object within the Inspector for each AI.

![](https://i.imgur.com/a6IoPfP.png)

## Step 2
You can setup your AI's detection Unity Tags and Layers through the Detection & Tags>Tag & Faction Options>Tag Options. Emerald AI needs these Unity Tags and Layers for its detection system so only valid objects are searched for. Ensure these are setup correctly according to your project. Note: The Emerald AI tag and AI Layer are not required.
![](https://i.imgur.com/W3cEGXn.png)

| Setting  | Description |
| ------------- | ------------- |
| Emerald Unity Tag  | The Unity Tag used to define other Emerald AI objects. This is the tag that was created using Unity's Tag pulldown at the top of the gameobject.  |
| Detection Layers  | The Detection Layers controls what layers this AI can detect as possible targets, if the AI has the appropriate Emerald Unity Tag.  |
# Game Kit Controller Integration
This tutorial will get Emerald AI working with Game Kit Controller (GKC). This will allow users to use GKC to damage, both ranged and melee, Emerald AI agents as well as have Emerald AI damage the GKC player. Note: This tutorial requires adding a few lines to a couple GKC scripts and some basic understanding of minor editing of scripts.

In order for Emerald AI to work correctly, your scenes must be baked with Unity’s NavMesh. For a quick guide on how to do so, see Unity’s guide here: [Baking your Scene with Unity's NavMesh](https://docs.unity3d.com/Manual/nav-BuildingNavMesh.html). Your AI’s attack animations will also need to have Attack Animation Events for ranged/melee attacks. See the tutorial on doing this here: [Attack Animation Event Tutorial](https://www.youtube.com/watch?v=s_lLt0xUrF8)

<a href="http://www.youtube.com/watch?feature=player_embedded&v=miCpkYpyZ_E
" target="_blank"><img src="http://img.youtube.com/vi/miCpkYpyZ_E/0.jpg" 
alt="IMAGE ALT TEXT HERE" width="400" height="280" border="10" /></a>


## applyDamage Code Snippet 
**(Important: There’s an additional step below to add melee damage support that is not covered in the tutorial video)**
This code should be placed right under the last if statement within the applyDamage script in the checkHealth function.
```c#
EmeraldAI.EmeraldAISystem EmeraldAIToCheck = objectToDamage.GetComponent<EmeraldAI.EmeraldAISystem>();
if (EmeraldAIToCheck)
{
   EmeraldAIToCheck.Damage((int)damageAmount, EmeraldAI.EmeraldAISystem.TargetType.Player);
}
```

## Extra Step to add melee damage support
This code should be placed right above return false; within the applyDamage script in the checkCanBeDamage function.
```c#
EmeraldAI.EmeraldAISystem EmeraldAIToCheck = objectToDamage.GetComponent<EmeraldAI.EmeraldAISystem>();
if (EmeraldAIToCheck) 
{
   EmeraldAIToCheck.Damage((int)damageAmount, EmeraldAI.EmeraldAISystem.TargetType.Player);
}
```

## EmeraldAIPlayerDamage Code Snippet
This function should be placed within the EmeraldAIPlayerDamage. Make sure it is called with DamageGameKitController(DamageAmount); in the SendPlayerDamage function.
```c#
//Damage the Game Kit Controller system
void DamageGameKitController (int DamageAmount)
{
   if (GetComponent<health>() != null)
   {
      GetComponent<health>().setDamage((float)DamageAmount, Vector3.forward, this.transform.position, this.gameObject, this.gameObject, true, false);
   }
}
```

This concludes the GKC integration tutorial, if something isn’t working correctly, repeat the steps to ensure nothing was missed. Ensure that you have applied an Animation Event to your AI’s attack animations. If you’re having issues with implementing GKC, and you’ve gone through the tutorial, support can be provided at: Support@BlackHorizonStudios.com

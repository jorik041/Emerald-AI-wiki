# RFPS Integration Tutorial
This tutorial will get Emerald AI working with RFPS. This will allow users to use RFPS to damage, both ranged and melee, Emerald AI agents as well as have Emerald AI damage the RFPS player. This functionality will also allow users to block incoming attacks from Emerald AI agents. Note: This tutorial requires adding a few lines to a couple RFPS scripts and some basic understanding of minor editing of scripts. 

In order for Emerald AI to work correctly, your scenes must be baked with Unity’s NavMesh. For a quick guide on how to do so, see Unity’s guide here: [Baking your Scene with Unity's NavMesh](https://docs.unity3d.com/Manual/nav-BuildingNavMesh.html). Your AI’s attack animations will also need to have Attack Animation Events for ranged/melee attacks. See the tutorial on doing this here: [Attack Animation Event Tutorial](https://www.youtube.com/watch?v=s_lLt0xUrF8)

<a href="http://www.youtube.com/watch?feature=player_embedded&v=v_IYrqBLkAE
" target="_blank"><img src="http://img.youtube.com/vi/v_IYrqBLkAE/0.jpg" 
alt="IMAGE ALT TEXT HERE" width="440" height="280" border="10" /></a>

## WeaponBehavior Code Snippet
This code should be added within case 13 of the WeaponBehavior script above the break; line. This allows your RFPS player to deal damage with all guns and melee weapons.
```c#
//Emerald AI Damage
if(hit.collider.gameObject.GetComponent<EmeraldAI.EmeraldAISystem>() != null)
{			
   hit.collider.gameObject.GetComponent<EmeraldAI.EmeraldAISystem>().Damage((int)damageAmt, EmeraldAI.EmeraldAISystem.TargetType.Player);
   FPSPlayerComponent.UpdateHitTime();//used for hitmarker
}
```

## ArrowObject Code Snippet
This code should be added within case 13 of the ArrowObject script above the break; line. This allows your RFPS player to deal damage with arrows.
```c#
//Emerald AI Damage
if (hitCol.gameObject.GetComponent<Collider>().gameObject.GetComponent<EmeraldAI.EmeraldAISystem>() != null)
{                  
   hitCol.gameObject.GetComponent<Collider>().gameObject.GetComponent<EmeraldAI.EmeraldAISystem>().Damage((int)(damage + damageAddAmt), EmeraldAI.EmeraldAISystem.TargetType.Player);
   FPSPlayerComponent.UpdateHitTime();//used for hitmarker
}
```

## ExplosiveObject Code Snippet
This code should be added within case 13 of the ExplosiveObject script above the break; line. This allows your RFPS player to deal damage with explosives.
```c#
//Emerald AI Damage
if (hitCollider.gameObject.GetComponent<Collider>().gameObject.GetComponent<EmeraldAI.EmeraldAISystem>() != null)
{                           
   hitCollider.gameObject.GetComponent<Collider>().gameObject.GetComponent<EmeraldAI.EmeraldAISystem>().Damage((int)explosionDamageAmt, EmeraldAI.EmeraldAISystem.TargetType.Player);
}
```


This concludes the RFPS integration tutorial, if something isn’t working correctly, repeat the steps to ensure nothing was missed. If you’re having issues with implementing RFPS, and you’ve gone through the tutorial, support can be provided at: Support@BlackHorizonStudios.com

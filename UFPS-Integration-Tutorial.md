# UFPS Integration Tutorial
This tutorial will get Emerald AI working with UFPS version 1.7.5. This will allow users to use UFPS to damage, both ranged and melee, Emerald AI agents as well as have Emerald AI damage the UFPS player. Note: This tutorial requires adding a few lines to a couple UFPS scripts and some basic understanding of minor editing of scripts. 

In order for Emerald AI to work correctly, your scenes must be baked with Unity’s NavMesh. For a quick guide on how to do so, see Unity’s guide here: [Baking your Scene with Unity's NavMesh](https://docs.unity3d.com/Manual/nav-BuildingNavMesh.html). Your AI’s attack animations will also need to have Attack Animation Events for ranged/melee attacks. See the tutorial on doing this here: [Attack Animation Event Tutorial](https://www.youtube.com/watch?v=s_lLt0xUrF8)

<a href="http://www.youtube.com/watch?feature=player_embedded&v=O4zjfXzqXeE
" target="_blank"><img src="http://img.youtube.com/vi/O4zjfXzqXeE/0.jpg" 
alt="IMAGE ALT TEXT HERE" width="400" height="280" border="10" /></a>


## vp_FXBullet Code Snippet
This code should be placed right under the line m_Transform.position = m_Hit.point; within the vp_FXBullet script. Save the script when you’re done.
```c#
//Damage Emerald AI object
if (m_Hit.collider.gameObject.tag == "Emerald AI")
{
   if (m_Hit.collider.gameObject.GetComponent<EmeraldAI.EmeraldAISystem>() != null)
   {
      EmeraldAI.EmeraldAISystem EmeraldComponent = m_Hit.collider.gameObject.GetComponent<EmeraldAI.EmeraldAISystem>();
      EmeraldComponent.Damage((int)Damage, EmeraldAI.EmeraldAISystem.TargetType.Player, m_Source.transform, 400);
   }
}
```

## EmeraldAIPlayerDamage Code Snippet
This code should be placed right under the last commented section within the EmeraldAIPlayerDamage script. Ensure that you have also added the line DamageUFPSPlayer(DamageAmount); within the SendPlayerDamage function. Save the script when you’re done.
```c#
void DamageUFPSPlayer(int DamageAmount)
{
   if (GetComponent<vp_FPPlayerDamageHandler>())
   {
      GetComponent<vp_FPPlayerDamageHandler>().Damage((float)DamageAmount);
   }
}
```

This concludes the UFPS integration tutorial, if something isn’t working correctly, re-watch the video to ensure nothing was missed. If you’re having issues with implementing UFPS, and you’ve gone through the video tutorial, support can be provided at: Support@BlackHorizonStudios.com

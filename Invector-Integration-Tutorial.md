# Invector Integration Tutorial
This tutorial will get Emerald AI working with Invector Third Person Controller. This will allow users to use Invector TPC to damage Emerald AI agents with melee damage, ranged damage, and explosive damage. It also allows Emerald AI agents to damage the Invector TPC player with block support. Note: This tutorial requires adding a few lines to a couple Invector TPC scripts and some basic understanding of minor editing of scripts. In order for Emerald AI to work correctly, your scenes must be baked with Unity’s NavMesh. 

For a quick guide on how to do so, see Unity’s guide here: Setting up and Baking Unity’s Nav Mesh. Your AI’s attack animations will also need to have Attack Animation Events for ranged/melee attacks. See the tutorial on doing this here: Attack Animation Event Tutorial

<a href="http://www.youtube.com/watch?feature=player_embedded&v=he-oUJVES0k
" target="_blank"><img src="http://img.youtube.com/vi/he-oUJVES0k/0.jpg" 
alt="IMAGE ALT TEXT HERE" width="440" height="280" border="10" /></a>

## vMeleeManager Code Snippet
This code should be added right below the line onDamageHit.Invoke(hitInfo); 
```c#
//Emerald AI Damage
if (hitInfo.targetCollider.gameObject.GetComponent<EmeraldAI.EmeraldAISystem>())
{                 
   hitInfo.targetCollider.gameObject.GetComponent<EmeraldAI.EmeraldAISystem>().Damage(hitInfo.attackObject.damage.damageValue, EmeraldAI.EmeraldAISystem.TargetType.Player, transform, 400);
}
```

## vProjectileControl Code Snippet
This code should be added right below the first instance of onCastCollider.Invoke(hitInfo); and damage.damageValue = maxDamage;
```c#
//Emerald AI Damage
if (hitInfo.collider.gameObject.GetComponent<EmeraldAI.EmeraldAISystem>() != null)
{                       
   hitInfo.collider.gameObject.GetComponent<EmeraldAI.EmeraldAISystem>().Damage(damage.damageValue, EmeraldAI.EmeraldAISystem.TargetType.Player);
}
```

## vExplosive Code Snippet
This code should be added right below the line colliders[i].gameObject.ApplyDamage(_damage, null);
```c#
//Emerald AI Damage
if (colliders[i].gameObject.GetComponent<EmeraldAI.EmeraldAISystem>() != null)
{                      
   colliders[i].gameObject.GetComponent<EmeraldAI.EmeraldAISystem>().Damage(damage.damageValue, EmeraldAI.EmeraldAISystem.TargetType.Player);
}
```

## EmeraldAIPlayerDamage Code Snippet
This code should replace the current DamageInvectorPlayer function code as it has been updated to allow blocking.
```c#
void DamageInvectorPlayer (int DamageAmount, Transform Target)
        {
            if (GetComponent<Invector.vCharacterController.vCharacter>())
            {
                //Applies damage to Invector and allows its melee weapons to block incoming Emerald AI damage.
                if (GetComponent<Invector.vCharacterController.vMeleeCombatInput>().meleeManager != null)
                {
                    var PlayerInput = GetComponent<Invector.vCharacterController.vMeleeCombatInput>();
                    var MeleeManager = GetComponent<Invector.vCharacterController.vMeleeCombatInput>().meleeManager;

                    if (PlayerInput.isBlocking)
                    {
                        var _Damage = new Invector.vDamage(DamageAmount);
                        var DamageReduction = MeleeManager != null ? MeleeManager.GetDefenseRate() : 0;
                        if (DamageReduction > 0)
                            _Damage.ReduceDamage(DamageReduction);
                        MeleeManager.OnDefense();
                        _Damage.reaction_id = MeleeManager.GetDefenseRecoilID();
                        _Damage.sender = Target;
                        _Damage.hitPosition = Target.position;
                        GetComponent<Invector.vCharacterController.vCharacter>().TakeDamage(_Damage);
                    }
                    else
                    {
                        var _Damage = new Invector.vDamage(DamageAmount);
                        _Damage.sender = Target;
                        _Damage.hitPosition = Target.position;
                        GetComponent<Invector.vCharacterController.vCharacter>().TakeDamage(_Damage);
                    }
                }
                //If no Melee Manager is found, cause unreduced damage.
                else
                {
                    var _Damage = new Invector.vDamage(DamageAmount);
                    _Damage.sender = Target;
                    _Damage.hitPosition = Target.position;
                    GetComponent<Invector.vCharacterController.vCharacter>().TakeDamage(_Damage);
                }

            }
        }
```

This concludes the Invector TPC integration tutorial, if something isn’t working correctly, re-watch the tutorial video to ensure nothing was missed. If you’re having issues with implementing Invector TPC, and you’ve gone through the tutorial video, support can be provided at: Support@BlackHorizonStudios.com


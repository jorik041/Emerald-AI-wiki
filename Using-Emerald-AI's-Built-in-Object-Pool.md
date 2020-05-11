# Emerald AI Built-in Object Pool
Emerald AI has built-in object pooling allowing Emerald AI projectiles and effects to automatically be recycled so they don't have to be instantiated every time they're used. Users can also utilize the object pooling system to spawn custom objects to help improve performance by not always instantiating the object. Objects created with Emerald AI's object pooling need to be despawned and cannot be destroyed using Unity's Destroy(gameObject); code. 

**Note:** The ```using EmeraldAI.Utility;``` namespace needs to be added at the top of your script in order for the EmeraldAIObjectPool scrip to be visible.

## Spawning an Object
To spawn an object with Emerald AI's object pooling system, you will need to use the following code. If you want the object to be added back to the pool, you will need to call Despawn. This is covered below.
```c#
EmeraldAIObjectPool.Spawn(ObjectToSpawn, SpawnPosition, ObjectRotation);
```

## Spawning an Object with Auto Despawn
To spawn an object with Emerald AI's object pooling system that will automatically despawn after the specified seconds, you will need to use the following code:
```c#
EmeraldAIObjectPool.SpawnEffect(ObjectToSpawn, SpawnPosition, ObjectRotation, DespawnSeconds);
```

## Despawning an Object
In order for a spawned object to be added back to the object pool, you will need to use the following code. If you are using auto despawn as explained above, despawn doesn't need to be called as it's done so automatically.
```c#
EmeraldAIObjectPool.Despawn(ObjectToDespawn);
```

# Setting up and Baking Unity’s NavMesh
In order for your AI to be able to navigate through a scene, they need to have Unity’s Nav Mesh system baked to it. A guide on how to do this can be found here: [Baking your Scene with Unity's NavMesh](https://docs.unity3d.com/Manual/nav-BuildingNavMesh.html). 

1) Every object you want to be included within the NavMesh baking must be marked as static. Marking an object as static can be found by going to the object within the inspector and checking the Static checkbox.
![](https://i.imgur.com/2s50Cpb.png)

2) When you have marked all desired all objects as static, you can open up the Navigation tab. This should be to the right of the Inspector tab. However, if it's missing, you can find it at Window > AI > Navigation.
![](https://i.imgur.com/CsLttJj.png)

3) The baking process can take some time depending on how large and complex a scene is. When a scene has finished baking, blue mesh will be visible within your scene when in the Navigation tab. This is an indicator that the baking process was successful.
![](https://i.imgur.com/DHMk7qI.png)

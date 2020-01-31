# Applying an AI's Head Transform
Applying an AI's head transform is simple and is used for proper target detection. Each AI uses raycasts to detect if targets are objected, for the head look feature, or to detect if a target is within an AI's line of sight. The head transform is used so the raycast is properly calculated from the AI's head for accurate and realistic results.

## Step 1
Find the AI that needs its head transform assigned. Your AI should indicate this within the Emerald AI editor at the top.

![](https://i.imgur.com/QWfAicZ.png)

## Step 2
Within your AI's bone transforms, find the AI's head transform.
![](https://i.imgur.com/gLxgpgs.png)

## Step 3
Go to the AI's Emerald AI editor and open the Detection & Tags>Detection Options tab. Assign the AI's head transform to the Head transform slot. This should remove the Head Transform warning at the top of the Emerald AI editor.

![](https://i.imgur.com/f583n3s.png)
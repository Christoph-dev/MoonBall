# Better Floor Material  

![](images/Pasted%20image%2020260725160813.png)  

- Create a new `Material` inside of the `Art` Folder
	- Call it `M_FloorGrid`
	- Build this logic in the `Material Graph` by right clicking and searching for the names:  
![](<images/Pasted image 20260725160427.png>)  

- Then Assign it to the `Cube` that should already exist in the level.  
![](<images/Pasted image 20260725160542.png>)  

- Also, set the Cubes scale to `[20, 20, 1]`
## Player Start

- Add a `Player Start` to the level through the `Quick Add` menu.  
![](<images/Pasted image 20260725161442.png>)  

- Set its `Location` to `[0, 0, 150]`

## Blocking Volumes
To stop the play from falling off the edge, we need to create some invisible walls.

- Add a `Blocking Volume` through the `Quick Add` menu.  
![](<images/Pasted image 20260725161609.png>)  

- Set the `Blocking Volume`'s transforms to:  
![](<images/Pasted image 20260725165442.png>)

- Then make sure the `Blocking Volume` is selected, press `W` and alt drag the green arrow to create a duplicate.
- Move the second volume to the opposite side would should end up in location: `[0, -1100, 550'`.  
![](<images/Pasted image 20260725162144.png>)  

- Use the same method to create the other sides. You will need to press `E` to rotate.  
![](<images/Pasted image 20260725162349.png>)  
- Don't forget the ceiling.
- It does not need to be perfect, but it should overlap with other sides to avoid anything squeezing through.

## Physics Ball

#### M_Ball
- Go to the `Art` folder and create a `Material` called 'M_Ball'
- Build the material graph below:  
![](<images/Pasted image 20260725164248.png>)  
- Save and close `M_Ball`

#### BP_Ball
- Go to the `Core` folder, right click and create a new `Blueprint Class`
	- Select `Actor` and call it `BP_Ball`, then open it.
- In the `Components` section at the top left, click the `Add` button and add a `Sphere`.
	- You can call the `Sphere` 'Ball'.
- In the `Details` Panel:
	- Tick `Simulate Physics`
	- Tick `Mass (kg)`
		- Set `Mass (kg)` to 10.0.  
![](<images/Pasted image 20260725162837.png>)  

- And set the `Material` to `M_Ball`.

- Drag and drop the ball into the level from the `Content Drawer` to test.

## Goal

![](<images/Pasted image 20260725172108.png>)  

- Go to the `Core` folder, right click and create a new `Blueprint Class`
	- Choose `Actor` and call it `BP_Goal`
- In the components section, add three cubes.

- For each cube, set these transforms to create a goal shape:
Cube 1  
![](<images/Pasted image 20260725164646.png>)  

Cube 2  
![](<images/Pasted image 20260725164656.png>)  

Cube 3  
![](<images/Pasted image 20260725164713.png>)  

- Then add the `M_WhiteE` material to each cube.
- Now add a `Box Collision` component to `BP_Goal`
	- Set its Location to `[0, 0, 200]`
	- Set its `Box Extent` to `[380, 20, 200]`

End of Checkpoint2

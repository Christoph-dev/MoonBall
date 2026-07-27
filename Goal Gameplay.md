
## Manager Variable
- Open up `BP_Goal` from the `Core` folder.
- Add a variable by clicking the plus on the lower left near variables.
![[Pasted image 20260726001713.png]]  
- Name the variable `Manager`
- Change the type from `Boolean` to `BP Manager`
- Then click on `Manager` to highlight it, and in the details panel on the left:
	- Check `Instance Editable`
	- Check `Expose on Spawn`  
![[Pasted image 20260726001924.png]]  
![[Pasted image 20260726001940.png]]  


## Goal Spawn Manager
- Go to your `Core` folder, right click and create a `Blueprint Class`
	- Choose Actor
	- Call it `BP_Manager`
- Open `BP_Manager` and go to the `Event Graph`
- Search for and add a custom event.
![[Pasted image 20260725222902.png]]  
- Call it `Spawn Goal`
- Now right click and search for 'Create Actor From Class'  
- Change the class to `BP_Goal` *The purple pin*
- Then Drag the Return Value and Promote to Variable
	- Call the `BP_Goal` variable 'Goal'
- Finally, Drag the `Manager` blue pin out and search for `Get a ref to self`  
![[Pasted image 20260726145803.png]]  
### Goal Random Location

- Create two new variables in the bottom left:
	- `GoalWidth`, set to float
		- Compile and set default to `420`
	- `FloorWidth`, set to float
		-  Compile and set default to `900`  
![[Pasted image 20260726150002.png]]  

To get a random length along the edge of the floor, we need to build this below:  
![[Pasted image 20260726150056.png]]  

Now we want the goal to spawn along any edge, so we need 4 edge cases.
- Search for and add a `Switch on Int` node.
	- Add 4 pins
- Search for and add a `Random Integer in Range` node.
	- Set Min to 0, and Max to 3  
![[Pasted image 20260726150215.png]]  

- On the `SpawnActor BP Goal` node, right click the orange `Spawn Transform` and click `Split Struct Pin`
- Drag the `Spawn Transform Location` pin and `Promote to Variable`.
- Drag the `Spawn Transform Rotation` pin and `Promote to Variable`.
![[Pasted image 20260726150419.png]]  

- Now search for a `Set Goal Transform Location` and create 4 of them.
- Split all of their Location Vectors
- Set the first two `Location Y` to 900, then -900
	- - Plug the random length math into `Location X`
- Set the second two `Location X` to 900, then -900
	- Plug the random length math into `Location Y`  
**Then Plug the `Swith on Int` into each `Set` node respectively.**  
![[Pasted image 20260726152841.png]]  

- Search for and create two `Set Spawn Transform Rotation` nodes
	- Set the second one to [0, 0, 90]
- Connect as below:
![[Pasted image 20260726153123.png]]  

- Finally, create the node logic below to go BEFORE the `Switch on Int` node:  
![[Pasted image 20260726182954.png]]

- Now go back to `BP_Goal`. Create a `Boolean` variable called `CanScore`
- Create this logic below:  
![[Pasted image 20260726183326.png]]  

- Then open up `BP_Ball`, and add a tag called `Ball`  
![[Pasted image 20260726153533.png]]  
**Save and compile all blueprints**
**Drag a `BP_Manager` into the level and test.**

End of Checkpoint 3.
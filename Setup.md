## New Project  

- Open Unreal Engine and hit `New Project`.
- Use the settings below.  
![](<images/images/Setup1.png>)  

- Choose a suitable directory and hit `Create`

## Folder Structure

- Click the `Content Drawer` in the bottom left.
- Right click inside the `Content Drawer` and create a new folder.
- Make the folders below.  
```
Content
└── MoonBall26
    ├── Maps
    ├── Core
    ├── UI
    ├── Art
    └── Audio
```

## Materials
- Go to the `Art` folder, right click and create a material called `M_WhiteE`
- Open the Material and create this node network below:  
	- *Hint: Hold 3 and click to create the RGB Node*
![](<images/images/Pasted image 20260725133323.png>)  
- Save and close this material.
- Create a second material called `M_GrayE`, as below:  
![](<images/images/Pasted image 20260725133512.png>)  
- Save and close this material.
## Blank Map
- Go inside the `Maps` folder, right click and creata a level called `Map_A`
- Double click to open it.
- Click on the `Quick Add` button in the viewport and create a `Cube`.  
![](<images/images/Pasted image 20260725133016.png>)  
- For now, set the material of the `Cube` to `M_GrayE`, which can be done through the details panel on the bottom right.  
![](<images/images/Pasted image 20260725133801.png>)  

- Then set the Scale of the cube to `[20, 20, 1]` in the details panel.
- Finally set its location to `[0, 0, 0]` aka `World Origin`.

## Core Defaults

- Go to `Core` folder, right click and create a `Blueprint Class`
	- Select `Game Mode Base`
	- Call it `GM_MoonBall`
- Create another `Blueprint Class`
	- Select `Player Controller`
	- Call it `BP_PlayerController`
- Create another `Blueprint Class`
	- Select `Character`
	- Call it `BP_Player`  
![](<images/images/Pasted image 20260725140643.png>)  

- Now in the top menu, go to `Edit -> Project Settings`
- Search for `default` in the search bar, and then change all of these settings:
![](<images/images/Pasted image 20260725140930.png>)  

## Input

### 1 - Input Assets

- Create a new folder inside `Core` called `Input`
- Inside `Input`, right click and create a `Input Action` called `IA_Move`
- Create another `Input Action` called `IA_Look`
- Create one more `Input Action` called `IA_Jump`
- Finally right click and create an `Input Mapping Context` called `IMC_MooBall`  
![](<images/Pasted image 20260725143243.png>)  

- Open `IA_Look`
	- Set `Value Type` to `Axis2D`  
![](<images/Pasted image 20260725143333.png>)  
- Save and Close `IA_Look`
- Open `IA_Move`
	- Set Value Type to `Axis2D`
![](<images/Pasted image 20260725143411.png>)  
- Save and Close `IA_Move`

#### Input Mapping Context - Move

- Now open IMC_MoonBall
- Add a new Mapping  
![](<images/Pasted image 20260725143530.png>)  

- Click the dropdown and set it to `IA_Move`
- Then Click the `Add` button 4 times.
- For each mapping, set them to `W, S, A, D`  
![](<images/Pasted image 20260725143712.png>)  

**Set these Parameters per key:**
- `S`
	- Modifier: `Negate`
- A
	- Modifier 1: `Negate`
	- Modifier 2: `Swizzle`
- D
	- Modifier: `Swizzle`  
![](<images/Pasted image 20260725144451.png>)  

#### Input Mapping Context - Look
- Now add another `Mapping`
![](<images/Pasted image 20260725143530.png>)  

- Set it to IA_Look
- Set its bound input to `Mouse XY 2D-Axis`  
![](<images/Pasted image 20260725144724.png>)  
- Add a `Modifier` and set it to `Negate`
- Expand the `Negate` options and set it to `Y` only.  
![](<images/Pasted image 20260725150308.png>)  
#### Input Mapping Context - Jump
- Add one more `Mapping`
- Set it to `IA_Jump`
- Set its bound key to `Spacebar`
![](<images/Pasted image 20260725144808.png>)  
### 2 - Input Logic
The input needs to be assigned to the player.

#### Player Controller
- Go back to `Core` folder and open `BP_PlayerController`
- Go to the `Event Graph` Tab
- Make this node network below by right clicking in the graph and searching for the node names.
	- Then drag the pins together.  
![](<images/Pasted image 20260725145642.png>)  
- Compile, Save and close `BP_PlayerController`

#### Player Character
- Open BP_Player
- Go to the `Event Graph` Tab
##### Look
- Create these nodes below by right click and searching for their names:  
![](<images/Pasted image 20260725150428.png>)  
- Split the blue `Action Value` pin to expose the `X` and the `Y` values.
##### Move
- Create these nodes below by right click and searching for their names:  
![](<images/Pasted image 20260725150938.png>)  
- Split the blue `Action Value` pin to expose the X and Y values.

##### Jump
- Create these nodes below by right click and searching for their names:  
![](<images/Pasted image 20260725151210.png>)  


End of Checkpoint 1

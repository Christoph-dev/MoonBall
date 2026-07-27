
## Base Setup
- Go to the `UI` folder, right click and create a `Widget Blueprint`
	- Select `User Widget`
	- Call it `WBP_Menu`

- Open up `WBP_Menu`
- From the `Pallete` in the top left, create a `Border` by dragging it into the viewport.
- Change the colour of the border to black and add some transparency.  
![[Pasted image 20260726203402.png]]  

- Then create a `Horizontal Box` by dragging it into the border
- And then drag into the `Horizontal Box` from the pallete these three:
	- A `Spacer`
	- `Vertical Box`
	- Another `Spacer`  
![[Pasted image 20260726201135.png]]  

- Select the two spacers and the vertical box and then:
	- Select `Fill` in the details  
![[Pasted image 20260726200003.png]]  

*Widget so far should look like:*  
![[Pasted image 20260726201201.png]]  

- Then inside of the `Vertical Box`, add these in this order:
	- `Spacer`
	- `Image`
	- `Spacer`
	- `Button`
	- `Spacer`
	- `Button`
	- `Spacer`
- Then as before, select all of those primitives and press `Fill` in the details.
![[Pasted image 20260726201250.png]]  

![[Pasted image 20260726201302.png]]  

## Button Setup

- Click the first button and in the details:
	- Check `Is Variable`
	- Rename it to `BTN_Play`
- Then for the second button:
	- Check `Is Variable`
	- Rename it to `BTN_Exit`

- Then In the `Palette`, drag a `Text` into both buttons.
	- Change the first buttons text to `Play Game`
	- Change the second buttons text to `Exit` or `Quit`
	- Feel free to change the font or colour.  
![[Pasted image 20260726201707.png]]  

## Title Image
- Make a Title Screen image that says `Moon Ball`
- Drag the image into the `Art` folder
- Click on the `image` primitive and change its image to the one you just uploaded.
- Change the `Size` setting to `Auto` if required.  
![[Pasted image 20260726201906.png]]  

## Widget Logic

- Click on the `Graph` button in the top right.

- Use the `Construct` event to build this logic:  
![[Pasted image 20260726202715.png]]  

- Click on `BTN_Play` and press the + next to the `On Clicked` event.  
**![[Pasted image 20260726202121.png]]  

- Build this logic from this event:  
![[Pasted image 20260726202742.png]]  

- Add the `BTN_Exit` click event and simply build this logic:  
![[Pasted image 20260726202811.png]]  

# Spawn the Menu
- Go to BP_Manager
- Search for and add a `Create Widget` node.
- Append it to the `Begin Play`
- Add a `Add to Viewport` to the end as below:  
![[Pasted image 20260726203155.png]]  

**Now test it**  
![[Pasted image 20260726204034.png]]  
## In-game UI

- In the `UI` Folder, create a new `Widget Blueprint`
	- Select `User Widget`, set its name to `WBP_UI`
- Open `WBP_UI`
- Add a `Canvas` primitive rom the palette.
- Then add two `Text` primitives.
	- Call the first one `TXT_Timer`
		- Check `Is Variable`
		- Position X = 100
		- Position Y = 40
		- Font = 48
		- Text = `Time Left:`
	- Call the second one `TXT_Goals`
		- Check `Is Variable
		- Position X = 100
		- Position Y = 128`
		- Font = 48
		- Text = `Goals:`  
![[Pasted image 20260726210150.png]]  

## Timer
- Now go to BP_Manager
- Add this logic to the `Begin Play` event, after creating the main menu:  
	- You will need to search `Get TXT_Goals` to get the lower two references.
	- You will need to drag from `TXT_Goals` to promote to variable:
![[Pasted image 20260726212932.png]]  

- Then Search for and add a `Custom Event`, call it `UpdateTimer`
- Create a new variable called `Timer`, set its type to `Integer`
	- Add this logic below:  
![[Pasted image 20260726213140.png]]  

- Now search for and add a `Set Timer By Event`
- Execute it after creating the `WBP_UI` widget
- Plug the `UpdateTimer` event in
- Set time to 1.0
- Check `Looping`  
![[Pasted image 20260726213322.png]]  

## Increase Goal and Time
We need to modify the `SpawnGoal` Event in `BP_Manager`

- After Destroying the Actor when `Is Valid` is True, we'll update the score.
- Add a `Goals` Variable, which needs to be an `Integer`
- Modify the `SpawnGoal` Logic as below:  
![[Pasted image 20260726214201.png]]  

## End Game Screen

- Create another `Widget Blueprint` in the `UI` folder called `WBP_GameOver`
- Add a border, then a horizontal box.
	- Set the Border's colour to a dark transparent black.
	- Then add a spacer, vertical box and spacer.
	- Select the three previous and change to `Fill`
![[Pasted image 20260726201201.png]]  

- Inside of the vertical box, add a:
	- Spacer
	- Text
	- Spacer
	- Button
		- Text Inside Button
	- Spacer
	- Button
		- Text Inside Button
	- Spacer
- Select all and fill.  
![[Pasted image 20260727075717.png]]  

- Change the top text's name to `TXT_Score`
	- Check `Is Variable`
	- Change the Text to `Final Score: `
- Change the first button's name to `BTN_PlayAgain`
	- Check `Is Variable`
	- Change the text to `Play Again`
- Change the second button's name to `BTN_Quit`
	- Check `Is Variable`
	- Change the text to `Quit` or `Exit`

- Set all fonts to 48, and center align them.  
![[Pasted image 20260727080223.png]]  

- Build the same `Event Construct` logic that we used for `WBP_Menu`  
![[Pasted image 20260726202715.png]]  

- Then for the last two buttons, make this logic:  
![[Pasted image 20260727080759.png]]  

- Finally, go back to the `BP_Manager` blueprint.
	- In the `UpdateTimer` Event, change the `True` logic to instead open `WBP_GameOver`.  
![[Pasted image 20260727081459.png]]  

![[Pasted image 20260727081855.png]]  

End of Checkpoint 4


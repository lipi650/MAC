# M.A.C.
Mega Adventure Creator is a Graphical Text Adventure creator for the Mega65.
You can create a menu-driven text adventure with it and add colour graphics too.
It will use NCM (Nibble colour mode) to keep the size small but I might release an FCM (Fullcolor Character Mode) version later if there's demand for it.
The program is at useable state but there is still room for improvements (like adding weight to objects / UI improvements).

## The UI:
The upper status bar shows the available directions.
The player can navigate with the cursor arrows and U(up) D(down) keys.
RETURN opens the 3-level menu:
* 1st level is the available commands (Look, Examine, Use, etc...)
* 2nd level opens if the selected command can use an object
* 3rd level opens if the selected command uses 2 objects
The player can navigate up and down in the menu with the cursor arrows and go back one level with left arrow.
RETURN confirms the selected menu item.

## Importing the GFX (IFF2NCM.BAS):
Create a 320x200 IFF image with any 16 colours (4 bitplanes).
The first row should hold the palette (1 pixel of each colour from left to right)
The next 104 rows will be converted to 16x8 pixel sized NCM (Nibble Colour Mode) characters.
At the current state the tool only imports 24 images from 01PICS.D81 and saves the converted information in NCM format to the MAC.D81 disk.
Later I can improve it to import more and save to separate game disks if the size requires it.
Every picture can have different palette.
The plan is that the main program will use the first colour as background, the second colour as text and the third colour as menu highlight so you should make the palette order according to this when defining the colours in the first pixel row.

The naming convention is 01.IFF ... 24.IFF

## Verbs
You can set up 20 verbs.
The function of the first three verbs are hardcoded:
1. Look: (prints the actual room's description)
2. Inventory
3. Get object
4. Examine (prints object descriptions)

The other verbs can be freely configured with global/local rules.

## Message editor
Messages 0-11 are used for inventory and direction related texts.
The other message slots can be used freely.

## Rule editor
The interpreter checks the conditions of the rules until it finds one with no conditions set.<br>
Rules after the first empty rule are not checked (for optimizing performance).<br>
When a rule has no Verb condition set then that rule is evaluated immediately after showing a room's description.<br>
When a rule has a Verb condition set then it is evaluated after a command is selected from the menu system.<br>
When a combination of conditions is met then several actions can be executed by the rule (piciking up / dropping an object, displaying a message / opening a path to a near room / setting a flag etc...)
You should set an empty rule vith verb=1 for Look and an other one with verb=2 for Inventory.

## Support
If you enjoy this project or create a game with it, you can buy me a coffee me on [Ko-fi](https://ko-fi.com/lipi650).

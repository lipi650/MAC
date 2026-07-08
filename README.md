# M.A.C.
Mega Adventure Creator is a Graphical Text Adventure creator for the Mega65.
You can create a menu-driven text adventure with it and add colour graphics too.
It will use NCM (Nibble colour mode) to keep the size small but I might release an FCM (Fullcolor Character Mode) version later if there's demand for it.
The program is still under development.

## The UI:
The upper status bar shows the available directions.
The player can navigate with the cursor arrows and U(up) D(down) keys.
RETURN opens the 3-level menu:
* 1st level is the available commands (Look, Examine, Use, etc...)
* 2nd level opens if the selected command can use an object
* 3rd level opens if the selected command uses 2 objects
The player can navigate up and down in the menu with the cursor arrows and go back one level with left arrow.
RETURN confirms the selected menu item.

## Importing the GFX:
Create a 320x200 IFF image.
The first row should hold the palette (1 pixel of each color from left to right)
The next 104 rows will be converted to 16x8 pixel sized NCM (Nibble Colour Mode) characters.
At the current state the tool only imports 24 images from 01PICS.D81 and saves the converted information in NCM format to the MAC.D81 disk.
Later I can improve it to import more and save to separate game disks if the size requires it.
Every picture can have different palette.
The plan is that the main program will use the first colour as background, the second color as text and the third color as menu highlight so you should make the palette order according to this when defining the colors in the first pixel row.

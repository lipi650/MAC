# M.A.C.
Mega Adventure Creator is a Graphical Text Adventure creator for the Mega65.
You can create a menu-driven text adventure with it and add colour graphics too.
It will use NCM (Nibble colour mode) to keep the size small but I might release an FCM (Fullcolor Character Mode) version later if there's demand for it.
The program is still under development.

## Importing the GFX:
Create a 320x200 IFF image.
The first row should hold the palette (1 pixel of each color from left to right)
The next 104 rows will be converted to 16x8 pixel sized NCM (Nibble Colour Mode) characters.
At the current state the tool only imports 24 images from 01PICS.D81 and saves the converted information in NCM format to the MAC.D81 disk.
Later I can improve it to import more and save to separate game disks if the size requires it.
Every picture can have different palette.
The plan is that the main program will use the first colour as background, the second color as text and the third color as menu highlight so you should make the palette order according to this when defining the colors in the first pixel row.

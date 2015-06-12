# C64-Utils
Commodore-64 stuff.  Mostly subroutines to learn 6502 assembly language programming techniques.

This is my first github repo. The first set of files is a collection of small subroutines to handle certain string functions. The main subroutine, "pwrap.sub", was written to print CBM screen codes directly to video RAM, instead of using the Kernal print routines. Optionally, pwrap prints strings with word wrap at the 40th column. 

I also wrote a program to test pwrap.sub, called "ptest.a".  This program basically sets up the relevant variables and prints a test string twice on the C64 screen- first without word wrap, then with word wrap. "ptest.a" is the only file in the collection with a ".pc" (program counter) directive. This is the file you can assemble and run "out of the box" to see the functionality of the pwrap subroutine.  

In the interest of code modularity and readability, I created several small subroutines, which are called from pwrap.sub, and which are necessary to its operation:

bt.sub -- "bt" = "Build Table". Builds a table of screen addresses in RAM, of the column zero address for each line on the C-64 screen, 0-24.

cls.sub -- Clears the screen with space characters (#$20)

getlen.sub -- Used by the pwrap function to wrap words to the next line, if they would cross the 40th-column on the screen. Finds the length of the current string segment up to the next space character.

newline.sub -- Prints a newline. 

I am interested in comments and suggestions from other programmers, especially those experienced in assembly language on the C-64, and others experienced in 6502 assembly in general. Is my code source readable?  Are the comments clear? Does my code make sense, and how can it be improved?  

Also, please feel free to download, or fork and modify my code.  I'd be interested to see what others might do with these routines. 
My current setup:  current versions of Sublime Text, Kick Assembler, and VICE, running on two different laptops- Windows 7 on one, and Lubuntu Linux 15.04 on the other. I don't have any C-64 hardware now, so I'd be interested to learn if these routines run okay on actual hardware.  They run okay in VICE.  

--Doug Brunelle -- 
San Diego, CA

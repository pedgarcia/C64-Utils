# C64-Utils
Commodore-64 stuff.  Mostly subroutines to learn 6502 assembly language programming techniques.

My first set of files here is a collection of small subroutines to handle certain string functions, and in particular, "pwrap.sub" was written to print CBM screen codes directly to video RAM, bypassing the Kernal print routines, optionally with word wrap at the 40th column. 

Wrote a program to test pwrap.sub, called "ptest.a".  This program sets up the relevant variables and defines various registers and zero-page pointers.  "ptest.a" is the only file in the collection with a ".pc" (program counter) directive. This is the program you can assemble and run "out of the box" to see the functionality of the pwrap subroutine.  

In the interest of modularity and code readability, I created several small subroutines called from pwrap.sub which are necessary to its operation:

bt.sub -- "bt" = "Build Table". Builds a table of screen addresses in RAM, of the column zero address for each line on the C-64 screen, 0-24.

cls.sub -- Clears the screen with space characters (#$20)

getlen.sub -- Used by the pwrap function to wrap words to the next line, if they would cross the 40th-column on the screen. Finds the length of the current string segment up to the next space character.

newline.sub -- Prints a newline. 

I would be interested in comments and suggestions from other programmers, especially those experienced in assembly language on the C-64. Is my code readable?  Are the comments clear?  Do my techniques make sense, and how can they be improved?  Also, please feel free to fork and modify my code.  I'd be interested to see what others might do with these routines.  

My current setup:  current versions of Sublime Text, Kick Assembler, and VICE, running on two different laptops- Windows 7 on one, and Lubuntu Linux 15.04 on the other. I don't have any C-64 hardware now, so I'd be interested to learn if these routines run okay on actual hardware.  They run okay in VICE.  

--Doug Brunelle -- 
San Diego, CA

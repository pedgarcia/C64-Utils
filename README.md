# C64-Utils
Commodore-64 stuff.  Mostly subroutines for experimentation, as I learn 6502/6510 assembly language programming techniques.

Latest updates at GitHub: https://github.com/DougBrunelle/C64-Utils

This is my first github repo. This set of files is a collection of small subroutines to handle certain text string functions. 

The main subroutine, "pwrap.sub", was designed to write CBM screen codes directly to video RAM, instead of using the Kernal print routines. Optionally, pwrap prints strings with word wrap at the 40th column. 

I also wrote a program to test pwrap.sub, called "ptest.a".  This program basically sets up the relevant variables and prints a test string twice on the C64 screen- first without word wrap, then with word wrap, so that the two printings can be compared visually. "ptest.a" is the only file in the collection with a ".pc" (program counter) directive. This is the file you can assemble and run "out of the box" to see the functionality of the pwrap subroutine.  

In the interest of code modularity and readability, I created several small subroutines, which are called from pwrap.sub, and which are necessary to its operation:

bt.sub -- "bt" = "Build Table". Builds a table of screen addresses in RAM, of the column zero address for each line on the C-64 screen, 0-24.

cls.sub -- Clears the screen with space characters (#$20)

newline.sub -- Prints a newline. Also synchronizes the zero-page string pointer (strp) and screen pointer (scnp) so that both of them can be addressed with the 'y' register.

back_spc.sub -- if word wrap is selected, this (very small) subroutine simply back-tracks through the text string looking for the previous space character. Used by pwrap.sub to wrap lines at the last screen column. 

I am interested in comments and suggestions from other programmers, especially those experienced in assembly language on the C-64, and others experienced in 6502 assembly in general. Is my source code readable?  Are the comments clear? Does my code make sense, and how can it be improved?  

Also, please feel free to download and hack my code.  I'd be interested to see what others might do with these routines. I will look at pull requests and merge your work into the repository, if I think your mods/improvements are useful. If you do so, please be generous with the comments in your code.

My current setup:  Atom editor, Kick Assembler, and VICE Commodore emulator, running on two different laptops- Windows 7 on one, and Lubuntu Linux 15.04 on the other. I don't have any C-64 hardware at this time, so I'd be interested to learn how these routines run on actual hardware.  They run okay in VICE (when I'm not busy breaking them to make them better! :-).  

--Doug Brunelle -- 
San Diego, CA

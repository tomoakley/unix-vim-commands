Unix/vi commands

## Unix commands:

cd - change directory. To go up to the parent, type cd ../. Without any paramaters (e.g cd path/to/directory) cd will just default to the home directory.
rm - delete directory
rm -rf - delete file
touch - create file
mkdir - create directory
ls - list current directory contents
pwd - list current working directory
ant - the servers have some build automation software installed called ant. Run this in the ~/Jetty directory and it will build your java files for you. If the java files have errors, the build will fail. If successful, ant will start Jetty, which is software to start a webserver.

Unix has autocomplete, so e.g in the ~/Jetty directory type cd s, press tab and it will autocomplete to src (if src exists in the current directory). If srd also existed in that directory, Unix will automcplete it to 'sr' as it doesn't know if you want src or srd.
If there is only directory in the current directory type cd and press tab and it will automatically autocomplete the path.
Combining these two things, in ~/Jetty, type cd s, and press tab 3 times. This 1) autocompletes s to src 2) works out that src only has one child directory (ubiserv), and ubiserv only has one directory (simple). So cd s<tab><tab><tab> autocompletes to cd src/ubiserv/simple, where the Java files reside. Shortcuts, ftw!

Software installed on the server:
mysql - database software
vi - text editor
ant - build tool
jetty - web server

## vi commands

vi is one of the default Unix text editors. It was created in 1976 (i.e before mice had been invented), hence why mice cannot be used to navigate it.

vi has two modes: command mode and insert mode. In command mode, you can move around, delete lines, etc. In insert mode, you can insert, and ONLY insert (no deletion, etc).

vi will create .swp files and will warn you of the existance of these when you start vi and a .swp file exists for the file you want to edit. Quit vi (:q), type rm -rf .filename.swp, enter, and then start vi again.

vi Command mode commands 

x - delete character
dd - delete line
i - enter insert mode and insert at that character
a - enter insert mode and insert after that character
$ (shift 4) - end of line
^ (shift 6) - start of line
w - move to next word
b - move to previous word
up/down/left/right - move cursor

(append a number to above commands to ____ multiple lines/characters) e.g 10x will delete the next 10 characters

:q - quit (:q! if you've made changes and don't want to save)
:w - save
:wq - save and quit

vi Insert mode:
esc - exit insert mode
backspace will not work in insert mode, until you exit insert mode. If you backspace, it will go back a character, where you can overwrite that character.


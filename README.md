# Brunel University CS2001 Help Sheet

Accessing the server can be done with any Terminal or Command Prompt. The lab sheets instruct you to use Putty if you are on Windows, as the default Windows Command Prompt doesn't work as well. To connect to the server, use this command:

    ssh l2grp@134.83.83.25 -p47263

Change the port number to 472 + your group number, e.g 47263 for group 13. The password is by default l2grp and your group number, e.g l2grp13. To connect to the server, you must either be on Brunel's campus and connected to the wifi, or connect to Brunel's network though a VPN (see http://connect.brunel.ac.uk for more details).  

ssh is the standard protocol for connecting to a server; it is abbreviated from Secure Shell (a shell is another name for a command line).

## Unix

Unix is an architecture for Operating Systems. It is used to run many Operating Systems, including Linux and Mac OS X. iOS and Android are also built on a Unix backbone. The server's we are using have been installed with Ubuntu, a distribution of Linux. Windows does not run on Unix - this is one reason some people dislike Windows; most of the world's servers run on Unix so if you know the various commands for using it, it can be very useful for interacting with servers.

## Unix Commands

- **cd** - change directory. To go up to the parent, type cd ../. Without any paramaters, cd will just default to the home directory.
- **rm** - delete directory
- **rm -rf** - delete file
- **touch** - create file
- **mkdir** - create directory
- **mv** - move or rename file/directory. Type the name of the file you want to move, and then the new path where you want to name it to. e.g mv filename.txt directory/filename.txt. To rename, just change the filename, e.g mv filename.txt newfilename.txt
- **cp** - copy and paste file/directory
- **ls** - list current directory contents
- **pwd** - list current working directory
- **ant** - the servers have some build automation software installed called ant. Run this in the ~/Jetty directory and it will build your java files for you. If the java files have errors, the build will fail. If successful, ant will start Jetty, which is software to start a webserver.

Unix has autocomplete, so for example in the ~/Jetty directory type cd s, press tab and it will autocomplete to src (if src exists in the current directory). If srd also existed in that directory, Unix will automcplete it to 'sr' as it doesn't know if you want src or srd.  
If there is only one directory in the current directory type cd and press tab and it will automatically autocomplete the path.  
Combining these two things, in ~/Jetty, type cd s, and press tab 3 times. This 1) autocompletes s to src 2) works out that src only has one child directory (ubiserv), and ubiserv only has one directory (simple). So cd s and tab three times, which will autocomplete to cd src/ubiserv/simple, where the Java files reside. Shortcuts, ftw!  

### Software installed on the server which we're required to use:
- **mysql** - database software
- **vi** - text editor
- **ant** - build tool
- **jetty** - web server
- **java** - programming language we're using

## vi

vi is one of the default Unix text editors. It was created in 1976 (i.e before mice had been invented), hence why mice cannot be used to navigate it.  

vi has two modes: command mode and insert mode. In command mode, you can move around, delete lines, etc. In insert mode, you can insert, and *ONLY* insert (no deletion, etc - although backspace can overwrite characters, see below).  

vi will create .swp files and will warn you of the existance of these when you start vi and a .swp file exists for the file you want to edit. Quit vi (:q), type rm -rf .filename.swp, enter, and then start vi again.

If you like to learn via a game, checkout [http://vim-adventures.com/]. Although this teaches Vim rather than Vi, it's a fork with pretty much the same standard as Vi just with some extras. (You can even enable mouse input). Vim can be installed by running `sudo apt-get install vim`.

### vi Command mode commands 

- **x** - delete character
- **dd** - delete line
- **i** - enter insert mode and insert at that character
- **a** - enter insert mode and insert after that character
- **$ (shift 4)** - end of line
- **^ (shift 6)** - start of line
- **w** - move to next word
- **b** - move to previous word
- **up/down/left/right** - move cursor

Append a number to above commands to carry out the chosen command on multiple lines/characters - e.g 10x will delete the next 10 characters

- **:q** - quit (:q! if you've made changes and don't want to save)
- **:w** - save
- **:wq** - save and quit

### vi Insert mode:
- **esc** - exit insert mode
- backspace will not work in insert mode, until you exit insert mode. If you backspace, it will go back a character, where you can overwrite that character.

## MySQL

MySQL is software to hold data in tables, which are held in databases. It uses a language called SQL (Structured Query Language), which is also used by other distributions of database software (SQLite, PostgreSQL). SQL is the language which MySQL uses to query the database. To access the databases, we need to first access MySQL. On the server, this is done with this command:

    mysql –ul2grp13 –p –h134.83.83.25 –P47100

Change the username (-u) to l2grp and your group number - the password is the same.

### Commands
- **show databases;** - this will output whatever databases are on the server
- **create dbName;** - create database with specified name. On our servers, you need to start the name with grp_ and your grp number, e.g grp_13_restofname
- **use database;** - select the database to run queries on
- **create table;** - create table with specified name

The other commands are queries (SELECT, UPDATE, INSERT, DELETE). I may add these to this help sheet at some point.

### JDBC
JDBC stands for Java Database Connection, which is what Java uses to connect to any database. It is not the database software (this is MySQL), but simply the driver which Java uses.

## Pull Requests
If you know how to use Git/Github (learn it, it's vital to software development and it's stupid we're not being taught it), feel free to make a pull request to change/add any information. Thanks! :D

## [bash guide](https://github.com/Idnan/bash-guide#2-basic-shell-programming)
### 1. Basic operation
1. **change download sources**:  
   ```
   
   sudo cp /etc/apt/sources.list /etc/apt/sources.backup.list
   sudo gedit /etc/apt/sources.list
   sudo apt-get update  
   ```
2. `export`   
  Display all environment variables
3. `whatis`  
  Show description for user commands,system calls,library function in manual pages
4. `whereis`  
  Search for exe ,source ,manual pages using a database
5. `which`  
  Search for exe in the dir specified by PATH  
6. `clear`  
  Clears contene on window
7.  `chmod`  
  > chmod -option filename
  > User (rwx) = 4+2+1 = 7  
Group(rx) = 4+1 = 5  
World (rx) = 4+1 = 5  
chmode mode = 0755
8.  `chown`  
  > chown -option user:group filename
9.  `find`  
  Find dir options pattern  
```
  $find /home/user1 -name '*.png'  
```
10.  `grep`
> grep pattern filename 


  Ignore word case by using `-i` option. `-r` can be used to search all files under dir
11. `bg`  
  Lists stopped or background jobs; resume a stopped job in the background.
12. `du`  
  Shows the disk usage of files or directories
13. `passed`  
  Allows the current logged user to change his password.
14. `scp`  
  Transfer files between a local host and a remote host or between two remote hosts.  
> scp -P port user@host:directory/source_file target_file
15. `top`  
  Displays your currently active processes.
16. [About etc/bashrc & etc/profil](http://bencane.com/2013/09/16/understanding-a-little-more-about-etcprofile-and-etcbashrc/)  
 
.profile or .bash_profile : set env items for a user shell,eg. PS1 or PATH
   
/etc/profile : set inital system wide environmental var for PATH or PS1 for all shell users of the system.

.bashrc  : setting command aliases and functions used by bash shell users.  
./etc/bash.bashrc:  system wide version of `.bashrc`

**Difference** :   
1) the /etc/profile is executed only for **interactive shells** and the /etc/bashrc is executed for both interactive and **non-interactive shells**(subprocess). In fact in Ubuntu the /etc/profile calls the /etc/bashrc directly.  
2)  /etc/bashrc include shell aliases and functions (not passed to other processes) read every time a shell starts up;
    /etc/profile contains system/global environment variables and startup program swhen the user initialy logs i.once a startup program is launched, there is no need to start it again  

17.``tree``  
  show dir with diagram tree , useful!  
18. ...

### 2. Basic Shell Programming

[**Book: Bash Guide for Beginners**](http://www.tldp.org/LDP/Bash-Beginners-Guide/html/)

　1. Saving your environment variables   

>  echo export FOO=BAR >> ~/.bash_profile  

　2. Accessing your scripts  
   append the code below in your ` ~/.bash_profile` file and after do source `~/.bash_profile`  

>     # set PATH so it includes user's private bin if it exists
    if [ -d "$HOME/bin" ] ; then
        PATH="$HOME/bin:$PATH"
    fi
    
　3. Debugging　scripts  
  passing different options to bash command. For example `-n` will not run commands and check for syntax errors only. `-v `echo commands before running them. `-x `echo commands after command-line processing.

> bash -n scriptname  
bash -v scriptname  
bash -x   scriptname

　4. ｀source`

　   source is a shell built-in that executes the content of the file passed as argument, **_in the current shell_**, It has a synonym in `.` (period).



　5. Be careful! `./` and `source` are not quite the same  
*  `./script` runs the script as an **executable** file, launching a new shell to run it
* ` source script` reads and executes commands(exe permission is not mandatory) from filename in the current shell environment
* Note: `./script` is not `. script`, but `. script` == `source script`
  
　6. 


  
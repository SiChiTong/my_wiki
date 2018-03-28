## Bash Scripts

### Readnotes of bash.academy
### Chapter
## 1. **The Bash Guide**  
 TL,DR 
## 2. **Inception**  
  > Bash is a shell program designed to listen to my commands and do what I tell it to.  
    A script is a pre-written series of commands  
    that runs either interactively or non-interactively
    

## 3. **Commands and Arguments** 
  > A bash command is the smallest unit of code that bash can independently execute    
    bash is not a strict interpreter  
    writing a bash script is similar to teaching your system how to do a task  
    Since bash is a lax interpreter, the responsibility of discipline lays with you  
    
  * **The gross part of all bugs in bash shell scripts are the direct result of their authors not properly understanding command arguments.**
  * You should use "double quotes" for any argument that contains expansions (such as \$variable or $(command) expansions) and 'single quotes' for any other arguments.
  * **The golden rule on quoting** is very simple:
If there is whitespace or a symbol in your argument, you must quote it.
If there isn't, quotes are usually optional, but you can still quote it to be safe.
  * Managing a command's input and output using redirection
    * hiding error messages: `ls -l a b >myfiles.ls 2>/dev/null`
    * duplicate file descriptors:`ls -l a b >myfiles.ls 2>&1`
    * File redirection: [x]>file, [x]<file
    * Appending file redirection: [x]>>file
    * exec can be used to create a new file descriptor ("plug") for you with that number.  
      ``` bash
         ping 127.0.0.1 >results 2>&1 
         
         exec 3>&1 >mylog; 
      ```
    * Redirecting standard output and standard error: `ping 127.0.0.1 &>results`
    * Here Strings: `<<<string`
    * Closing file descriptors: ` [x]>&y-, [x]<&y-`
    *  
    
## 4. **Variables and Expansions**  
  make our code a little more dynamic,a sort of template for doing a job that describes a way of executing our intent regardless of the specific situation we are currently in.
* Pathname Expansion
  * glob pattern: ` * ? [:classname:] $ ls ~/*/hello.txt` 
  * extended globs: `$ shopt -s extglob`
* Tilde Expansion  
  ```
  n-4th in ~/Documents 
  
 $ echo  'I live in : ' ~kevin

 I live in :  /home/kevin
  ```
* Command Substitution
  > **Value expansions ($...) must always be double-quoted.**
 
* Bash parameters  
  * Shell Variables  
    never put spaces around the = operator   
    ```
      $ name = lhunath  

     -bash: name: command not found
    ```
  * Parameter Expansion  
     * Remember that this operator only changes the value that is expanded; it does not change the original value that's sitting in your variable  `greeting+=" world  #append string` `%, # and // `
  
  * Environment Variables
     * environment variables exist at the process level
     
     > a process is as a piece of land you buy, You could put a `bash` house or a `grep` shack or a `firefox` tower on the land. Environment variables are variables stored on your process' land itself, while shell variables are stored inside the bash house built on your land. : D

      **The environment is something every process has, while the shell space is only available to bash processes.** 
     * It is a common misconception that the environment is a system-global pool of variables that all processes share.changing or creating new variables in the child will in no way affect the parent.
     *  "export" some of your shell variables into the shell's process environment,those child processes will in turn export their environment variables to their children.Your system uses environment variables for all sorts of things, mainly to provide **state information** and **default configurations** for certain processes.
     * Environment variables are generally only useful to those programs that know about and support them explicitly
  * Positional Parameters 
     *  bash command, there is a way to pass in positional parameters. our argument containing bash code is 'single-quoted'   
      ```bash
      
          $ bash -vc 'echo "1: $1, 2: $2, 4: $4"' -- \
     
          'New First Argument' Second Third 'Fourth Argument'
    
          echo "1: $1, 2: $2, 4: $4"
          
          1: New First Argument, 2: Second, 4: Fourth ArgumentAnd this is the result.
      ```
  
  * Shell Initialization  
     * ...
  
  * Shell Internal Variables
     * **RULES**: you should make all of your own shell variables lower-case. If you create an environment variable, give it an ALL-UPPERCASE name.
  
* Arrays
     * assignment operator: `=( )`  
         ```
           $ files=( myscript hello.txt "05 Between Angels and Insects.ogg" )
        
            $ rm -v "${files[@]}"
        
          ```
        
    If there is whitespace or a symbol in your argument, you **MUST** quote it !  
    e.g 
    * `+=( )`:append a list of items to the end of an array. e.g `files+=( selfie.png )`
    * `unset`: To remove a specific item from the array. e.g `unset "files[3]"`

* 
  

  
## 5. **Tests and Conditions**  





  
## 6. **Loops and Functions**  





  
## 7. **Asynchronous Commands**   









### keynotes
1. ` DIR="$( cd "$( dirname "${BASH_SOURCE[0]}" )" && pwd )"`   
   **return the (effectively) full path of the script**  
  `${}` acts as a kind of quoting for variables.

  `$()` acts as a kind of quoting for commands but they're run in their own context.
  
  `dirname` gives you the path portion of the provided argument.
  
  `cd` changes the current directory.
  
  `pwd`gives the current path.

  `&&` is a logical and but is used in this instance for its side effect of running commands one after another.  
   
2. 
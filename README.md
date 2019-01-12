Myshell is a simple implementation of ***Linux terminal***. It takes *commands* and *arguments* and execute them if they are available. 
When it starts, it takes your PC's *path* details and search the ***executable*** in these areas, 
if successful it runs it with the given arguments.  
Also it allows ***background processes***. If you put a "&" sign at the end of line (like Unix), it runs the program in the background. 
But its log is still in *main process*. Whenever you type "fg" it brings all background processes to the foreground.  

Also there are some ***commands*** built-in:  

  1 -) **alias/unalias**  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;- If you want your long string of executable string shrink into a smaller string, you can use alias.  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Ex: `alias "ls -l" list`  --- Whenever you type list, myshell will run "ls -l"  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;- You can see all aliases recorded.  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; `alias -l`  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;- Also you can unalias your aliases by using unalias.  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Ex: `unalias list`  
  2 -) If you press **^z** while a foreground process is running, that process will go to the background.  
  3 -) **clr** - this command does the same thing with the "clear" command.  
  4 -) **fg**  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;- This command brings all background processes to the foreground one by one.  
  5 -) **exit**  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;- This command is the only way to exit the program safely. But it won't let you exit if there are any background processes.  

Another feature of this shell is ***input/output redirection***. There are a few ways to accomplish this:  
  - `myprog [args] > file.out`    // myprog's standard output is redirected to the file.out. Overwrites the file if exists.
  - `myprog [args] >> file.out`   // myprog's standard output is appended to the file.out.
  - `myprog [args] < file.in`     // uses file.in as the standard input of myprog.
  - `myprog [args] 2> file.out`   // myprog's standard error channel is redirected to the file.out.
  
  ** Also you can use input and output in one line interchangeably.
  - `myprog [args] < file.in > file.out`  // uses file.in as the standard input of myprog and myprog's standard output is redirected to the file.out.

This is a ***multiprocess program***. Whenever an executable is wanted, it *forks a child* and executes the program in that process.

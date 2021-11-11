# C & linux interview questions
## How does system call works in linux ?
- system call is a interface between priviledge (kernel mode) and non-priviledge(user mode )
- It is sequence set of instruction to be executed by kernel upon user request </br>
&#8594;woking </br>
  * it is initiated as software interrupt handle by the wrapper function(holds the address of appropriate handler function) as function pointer  
  * It passes the arguments by pushing on to stack then invoke a mostly glibc or libc.a wrapper func located unistd.h the wrapper func copies syscall number to specific register(arhitecture dependent rax in case x86) and also copies arguments to specific register given below
  * 
  identify system call number and store in cpu register 
  * ABI
![transition](system_call.png "Title")
In some 
cases, however, there may be more parameters than registers. In these cases, 
the parameters are generally stored in a block, or table, in memory, and the 
address of the block is passed as a parameter in a register
<pre> 
NR 		%rax	arg0 (%rdi)	    arg1 (%rsi)	     arg2 (%rdx)	         arg3 (%r10) arg4 (%r8) arg5 (%r9)
0	read	0x00	unsigned int  fd	char *buf	      size_t count	     -       -         -
1	write	0x01	unsigned int fd	const char *buf 	size_t count                   -       -         -
</pre>
<br/>

## 2.Process and thread and why there is need of process if thread can do better ? 
## 3.Explain all about objdump ?
## 4.All about debugging concept using valgrind ?
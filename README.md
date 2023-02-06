# Lab 2
[Fork](https://docs.github.com/en/get-started/quickstart/fork-a-repo) this repo and clone it to your machine to get started!

## Team Members
- Grace True
- Caraline Baker

## Lab Question Answers

Answer for Question 1: How did the reliability of UDP change when you added 50% loss to your local environment? Why did this occur?

The reliability was diminished by about 50% when a 50% loss was added to the environment because UDP does not provide flow control meaning it cannot detect data or packets that get lost. 

Answer for Question 2: How did the reliability of TCP change? Why did this occur?

The TCP reliability did not change in a loss environment because TCP protocols ensure data is not lost, damaged, duplicated, etc making TCP a more secure data method than UDP.

Answer for Question 3: How did the speed of the TCP response change? Why might this happen?

The TCP response was slower when the loss occured due to latency. Generally, TCP is regarded as slower than UDP but TCP is regarded as more relaible than UDP since the data is gaurantueed to get to the destination. 

## Server Code Questions

1. What is argc and *argv[]?
argc is an integer input into the server indicating the number of arguements passed along the command line. The value will be at least 1. 

*argv[] is a pointer to a character array which are used to point to the arguements needed in the command line.

Sources: https://www.tutorialspoint.com/cprogramming/c_command_line_arguments.htm

2. What is a UNIX file descriptor and file descriptor table?
The UNIX file descriptor is a way of describing the open connection to a file as well as where in the file you are by indicating  "connection you want to read the next byte from" 

The file descriptor table connects the file descriptor and the data structures representing the actual file and connection.

Source: https://www.usna.edu/Users/cs/wcbrown/courses/IC221/classes/L09/Class.html 

3. What is a struct? What's the structure of sockaddr_in?
A struct is short for a structure which takes multiple data points (ie. the name, id number and grade of a student) that are related and stores them together as a custom data type. 

sockaddr_in represents an internet address by specifying the address and the port number to be listening to. serv_addr is a 16 bit number representing the address while cli_addr is a 16 bit numebr specifying the port.

Source: https://pubs.opengroup.org/onlinepubs/9699919799/functions/socket.html 

4. What are the input parameters and return value of socket()
INPUTS: socket(AF_INET, SOCK_STREAM, 0)
-> AF_INET is one input which is a constant defined in the header. Its value is normally 2 and tells the server that it is an IPv4 address is a 32 bit number specifying the address of a device using Internet Protocol (IP) for communication. 
-> SOCK_STREAM is a type of socket which is used to provide a relaible data path endpoint for network communication. 
-> 0 is a constant 

Source: https://pubs.opengroup.org/onlinepubs/9699919799/functions/socket.html (same as Q3)

OUTPUTS: the output of socket() is a descriptor for the socket created by the function which is needed to identify the socket. It is a non-negative int

5. What are the input parameters of bind() and listen()?
The bind() function takes two parameters:
  -> a socket object (created using socket.socket())
  -> a tuple containing the address and port number to which the socket will be bound.
  
The listen() function takes one parameter:
  -> a socket object that was previously bound using bind()

6. Why use while(1)? Based on the code below, what problems might occur if there are multiple simultaneous connections to handle?

If there are multiple simultaneous connections to handle, the program may run into problems if it is not designed to handle multiple connections at the same time. This is because the program may only be able to handle one connection at a time, and any new incoming connections may have to wait until the current connection is processed.

In our code, with the accept() command, new incoming data is blocked when data is already being accepted causing performance issues. These can be resolved by using different system commands (see Q7). 

Source: https://stackoverflow.com/questions/3329641/how-do-multiple-clients-connect-simultaneously-to-one-port-say-80-on-a-server

7. Research how the command fork() works. How can it be applied here to better handle multiple connections?
fork() works by creating a new process (a child to the parent process), which is identical to the copied process, for each incoming data package which allows it to handle multiple connections well since each data package has its own path/process and mulitple packages are not being sent on one process.

this is better than the accept() system call used currently because the accept call blocks other data from being read when there is already data being accepted. 

Source: https://www.geeksforgeeks.org/design-a-concurrent-server-for-handling-multiple-clients-using-fork/ 

8. This program makes several system calls such as 'bind', and 'listen.' What exactly is a system call?
A system calls are how a user level program and the system kernel interact. Unlike user level calls, system calls allow the kernel to temporarily take 'control' of the hardware allowing more complex tasks to be performed before returning 'conrol' to the user program

Source: http://pubs.opengroup.org/onlinepubs/9699919799/functions/index.html


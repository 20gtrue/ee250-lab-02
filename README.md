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
A struct is short for a structure which takes multiple data points (ie. the name, id number and grade of a student)that are related and stores them together. 

The structure of sockaddr_in is 

4. What are the input parameters and return value of socket()

5. What are the input parameters of bind() and listen()?

6.  Why use while(1)? Based on the code below, what problems might occur if there are multiple simultaneous connections to handle?

7. Research how the command fork() works. How can it be applied here to better handle multiple connections?

8. This program makes several system calls such as 'bind', and 'listen.' What exactly is a system call?



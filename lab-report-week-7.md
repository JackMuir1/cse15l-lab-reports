# Lab Report Week 7

The task my group chose to optimize with vim commands was the following:

In DocSearchServer.java, add a new line right before File[] paths = f.listFiles(); that prints out the toString of f and a message saying it’s a directory.

## Part 1- Commands
` /if <Enter> `

![first cmd](https://user-images.githubusercontent.com/70072541/201260888-4b60cfc1-cbbb-47ba-a951-af67d7beede4.png)

` <shift> a `
` <Enter> `


![move-to-newline](https://user-images.githubusercontent.com/70072541/201260913-37f67a78-5771-47c3-a7a6-ec2094854334.png)

` System.out.println(f.toString() + " is a directory"); `


![typed-line](https://user-images.githubusercontent.com/70072541/201260872-13d597c7-504e-45ce-bea5-56f2464e1d3c.png)

` <Escape> `
` :x `
` <Enter> `
` sh st <tab> `


![exited-vim](https://user-images.githubusercontent.com/70072541/201260855-c06226b5-f810-47fb-a7ae-62b3eed8ea12.png)


## Part 2- Running Remotely

### Method 1- Send the file to the remote server using scp
Time to complete- 1:41

### Method 2- Log in and edit remotely
Time to complete- 0:58

### Questions
* Which of these two styles would you prefer using if you had to work on a program that you were running remotely, and why? *

I prefer to log in to the remote server using ssh. When editing a file, especially with Vim, it is simpler to work with the files in their intended location, instead of moving them after every edit.

* What about the project or task might factor into your decision one way or another? (If nothing would affect your decision, say so and why!) *

Being that I simplified the task is a proceedural set of commands, I made less mistakes and did not need to memorize all the commands. In a real world scenario such as a job, I will have to edit files and create solutions on the fly, which would require me to know the commands and navigate the file systems of the given scenario. This would change my preference of remote editing.

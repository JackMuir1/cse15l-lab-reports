# Week 1 Lab: Remote Access and the Filesystem

## Installing VSCode

You can download VSCode at [this link here](https://code.visualstudio.com/)
Once you install visual studio, open the program. It should look like the following:

![VSCODe](https://user-images.githubusercontent.com/70072541/193163789-5cbcc03f-fe1d-40e9-8e77-20d6f78be52d.png)


## Remotely Connecting
Next, you'll need to connect to the remote computers ucsd has. By connecting to remote computers, you can has access to more powerful processing, more storage, and even a different operating system. 

You'll need a personal login and passwords to the computer, which you can find on [this link](https://sdacs.ucsd.edu/~icc/index.php)
From the site, you will get the two letters needed in theblanks for the log in address ` cs15lfa22__@ieng6.ucsd.edu `

You be using the terminal do communicate with the remote computer, so open a terminal in visual studio by going to Terminal -> New Terminal. Then type in the following command:
`ssh cs15lfa22__@ieng6.ucsd.edu`
Then enter your password

This will connect you to the remote server. You will get a display like the following:

![LoginScreen](https://user-images.githubusercontent.com/70072541/193162528-4090aa3c-eb2a-4d82-b5e8-03ebee012659.png)


## Trying Some Commands
Now you can use commands to navigate the remote computer. Here are some examples of commands you can use:
```
Move around the directory: cd 
List files in the directory: ls 
Copy the path: cp
Display contents of file: cat
```
Here's what the terminal looks like with some commands:

![Command Example](https://user-images.githubusercontent.com/70072541/193162503-adf5873e-6c62-4905-99c8-11d8650a20fa.png)

## Moving Files with scp
A benefit of having a remote computer is that you can transfer files from your home computer!
The command `scp <file> cs15lfa22__@ieng6.ucsd.edu` will send your file to the remote computer after entering your password.

In this example, I created a java file, WhereAmI.java, which displays the system of the computer the file is run on. When run remotely, you get the following text:
  
![running java ](https://user-images.githubusercontent.com/70072541/193162584-25d5004a-6f57-4d49-bb39-759f4d9ba32a.png)
  
## Setting an SSH Key
If you do not want to enter your password after every file change, you can create a ssh key by using `ssh-keygen` . This creates two files, your public and private key. You can send the private key to the remote server using 'scp' and have it saved so that your login will be saved.
  
Here is what the sending process of the public key looks like:
  
![Sending Key](https://user-images.githubusercontent.com/70072541/193162565-009608c0-35ee-47d8-991f-0b93a67f5d2d.png)

## Optimizing Remote Running
Now that you do not have to enter your password every time you want to upload or overrite a file, you can stremline the process of file transfer. An easy way to optimize is to have multiple terminals open, one on the client and one remote. Then you can navigate both computers without logging in and out.
  
  Note: When you update a file using `scp` , it automatically overrites files of the same name in the directory you are sending it to.
  
  Here's an updated version of the WhereAmi script with an extra line printed, uploaded to the remoate computer:
  
![Updated whereami](https://user-images.githubusercontent.com/70072541/193162592-f45c3a2b-340d-4f02-98ce-9a47b8bf3aaf.png)

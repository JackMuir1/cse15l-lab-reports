# Lab Report Week 7

The task my group chose to optimize with vim commands was the following:

In DocSearchServer.java, add a new line right before File[] paths = f.listFiles(); that prints out the toString of f and a message saying it’s a directory.

## Commands
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

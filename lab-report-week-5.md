# Week 5 Lab Report

In this lab report, we will be exploring 3 command line options for the **find** command through some examples in `./technical`

## First Option: -newer
The -newer option outputs files that were created or modified after the file to find. This is important because when navigating a file system, you may want to see what the most recent additions are. For example, if you were to host a competition to see who could write an essay the fastest, you can find the places of the winners based on the order of file additions.

### Example 1

```
Owner@DESKTOP-VPMBE6R MINGW64 ~/Desktop/CSE 15L/docsearch/technical (main)
$ find . -newer ./911report/chapter-1.txt
.
./911report
./911report/chapter-10.txt
./911report/chapter-11.txt
./911report/chapter-12.txt
./911report/chapter-13.1.txt
./911report/chapter-13.2.txt
./911report/chapter-13.3.txt
./911report/chapter-13.4.txt
./911report/chapter-13.5.txt
./911report/chapter-2.txt
./911report/chapter-3.txt
./911report/chapter-5.txt
./911report/chapter-6.txt
./911report/chapter-7.txt
./911report/chapter-8.txt
./911report/chapter-9.txt
./911report/preface.txt
./biomed
./biomed/1468-6708-3-1.txt
./biomed/1468-6708-3-10.txt
./biomed/1468-6708-3-3.txt
...EVERY SINGLE FILE LISTED
```

When finding for newer files created after `./911report/chapter-1.txt`, we can see that every single directory and file is listed. This shows that `./911report/chapter-1.txt`is the oldest file in the directory

### Example 2
```
Owner@DESKTOP-VPMBE6R MINGW64 ~/Desktop/CSE 15L/docsearch/technical (main)
$ find . -newer ./plos/pmed.0020278.txt
./plos
./plos/pmed.0020281.txt
```

When finding for newer files created after `./plos/pmed.0020278.txt`, we can see that only the `./plos` directory and `./plos/pmed.0020281.txt` are listed. This shows that `./plos/pmed.0020278.txt`is the second newest file in the directory, with `./plos/pmed.0020281.txt` being the newest.

### Example 3
```
Owner@DESKTOP-VPMBE6R MINGW64 ~/Desktop/CSE 15L/docsearch/technical (main)
$ find ./government/Alcohol_Problems -newer ./government/Alcohol_Problems/DraftRecom-PDF.txt
./government/Alcohol_Problems
./government/Alcohol_Problems/Session2-PDF.txt
./government/Alcohol_Problems/Session3-PDF.txt
./government/Alcohol_Problems/Session4-PDF.txt
```

By finding in the `./government/Alcohol_Problems` directory specifically, we see that `./government/Alcohol_Problems/DraftRecom-PDF.txt` is the oldest file, because every file is listed after the find command.

## Second Option: -empty
The -empty option will output the any files or directories that are empty. This is useful when looking for unused directories in a large file system. This helps with organization of file systems.


### Example 1
```
Owner@DESKTOP-VPMBE6R MINGW64 ~/Desktop/CSE 15L/docsearch/technical (main)
$ find . -empty

```
There are no empty directories or files in `/technical`, so no files are outputted.

### Example 2
```
Owner@DESKTOP-VPMBE6R MINGW64 ~/Desktop/CSE 15L/docsearch/technical (main)
$ mkdir emptyfile

Owner@DESKTOP-VPMBE6R MINGW64 ~/Desktop/CSE 15L/docsearch/technical (main)
$ find . -empty
./emptyfile
```
After creating an empty directory called `emptyfile` in `/technical` using `mkdir`, we can see that it is returned in the empty search.

### Example 3
```
Owner@DESKTOP-VPMBE6R MINGW64 ~/Desktop/CSE 15L/docsearch/technical (main)
$ cd government/Media

Owner@DESKTOP-VPMBE6R MINGW64 ~/Desktop/CSE 15L/docsearch/technical/government/Media (main)
$ mkdir emptyfile-Media

Owner@DESKTOP-VPMBE6R MINGW64 ~/Desktop/CSE 15L/docsearch/technical/government/Media (main)
$ find . -empty
./emptyfile-Media

Owner@DESKTOP-VPMBE6R MINGW64 ~/Desktop/CSE 15L/docsearch/technical/government/Media (main)
$ cd ../..

Owner@DESKTOP-VPMBE6R MINGW64 ~/Desktop/CSE 15L/docsearch/technical (main)
$ find . -empty
./emptyfile
./government/Media/emptyfile-Media
```
We create a second empty directory in the `government/Media` and run the search again. We see that it finds the empty file both in the working directory and recursively when searched from a parent directory.

## Third Option: -user
The -user option will output all the files that owned by the user specified after the option. This is important when you have a file system with a lot of contributors. For example, you could find all the files you created in a group project, so you can weigh your contribution.

### Example 1
```
Owner@DESKTOP-VPMBE6R MINGW64 ~/Desktop/CSE 15L/docsearch/technical (main)
$ find . -user Owner
.
./911report
./911report/chapter-1.txt
./911report/chapter-10.txt
./911report/chapter-11.txt
./911report/chapter-12.txt
./911report/chapter-13.1.txt
./911report/chapter-13.2.txt
./911report/chapter-13.3.txt
./911report/chapter-13.4.txt
./911report/chapter-13.5.txt
./911report/chapter-2.txt
./911report/chapter-3.txt
./911report/chapter-5.txt
./911report/chapter-6.txt
./911report/chapter-7.txt
./911report/chapter-8.txt
./911report/chapter-9.txt
./911report/preface.txt
./biomed
./biomed/1468-6708-3-1.txt
./biomed/1468-6708-3-10.txt
...ALL FILES LISTED
```
My username on my computer is Owner (never bothered to change it to my name).  When searching for files under the username Owner, we can see that all the files are outputted, showing that every files is owned by my machine. 

### Example 2
```
Owner@DESKTOP-VPMBE6R MINGW64 ~/Desktop/CSE 15L/docsearch/technical (main)
$ find . -user JackMuir
find: ‘JackMuir’ is not the name of a known user
```
We can see that I am too lazy to change my username on my computer because my name is not a known user. On a computer with multiple users, one could search for files owned by any user.

### Example 3
```
Owner@DESKTOP-VPMBE6R MINGW64 ~/Desktop/CSE 15L/docsearch/technical (main)
$ ssh cs15lfa22ka@ieng6.ucsd.edu
Last login: Thu Oct 27 11:21:57 2022 from 100.81.33.235
Hello cs15lfa22ka, you are currently logged into ieng6-203.ucsd.edu

You are using 0% CPU on this system

Cluster Status
Hostname     Time    #Users  Load  Averages
ieng6-201   13:45:01   13  0.34,  0.24,  0.23
ieng6-202   13:45:01   27  0.14,  0.19,  0.17
ieng6-203   13:45:01   17  1.24,  1.22,  1.23


Thu Oct 27, 2022  1:46pm - Prepping cs15lfa22
[cs15lfa22ka@ieng6-203]:~:82$ git clone https://github.com/ucsd-cse15l-f22/docsearch.git
Cloning into 'docsearch'...
remote: Enumerating objects: 1451, done.
remote: Counting objects: 100% (38/38), done.
remote: Compressing objects: 100% (22/22), done.
remote: Total 1451 (delta 25), reused 23 (delta 16), pack-reused 1413
Receiving objects: 100% (1451/1451), 12.21 MiB | 13.21 MiB/s, done.
Resolving deltas: 100% (26/26), done.
Updating files: 100% (1399/1399), done.
[cs15lfa22ka@ieng6-203]:~:83$ find ./docsearch/technical -user Owner
find: 'Owner' is not the name of a known user
[cs15lfa22ka@ieng6-203]:~:84$ find ./docsearch/technical -user cs15lfa22ka
./docsearch/technical
./docsearch/technical/911report
./docsearch/technical/911report/chapter-1.txt
./docsearch/technical/911report/chapter-10.txt
./docsearch/technical/911report/chapter-11.txt
./docsearch/technical/911report/chapter-12.txt
./docsearch/technical/911report/chapter-13.1.txt
... ALL FILES LISTED
```
Here I logged into the remote computer to test the repository with a different owner. I cloned the repository into the remote computer, and searched for the files owned by by local machine. Nothing returned, as I was on the remote computer, but when finding files owned by my cs15lfa22ka username, the files in `/technical` returned.

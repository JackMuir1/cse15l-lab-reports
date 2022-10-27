# Week 5 Lab Report

In this lab report, we will be exploring 3 command line options for the **find** command through some examples in `./technical`

## First Option: -newer
The -newer option outputs files that were created or modified after the file to find

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
The -empty option will output the any files or directories that are empty


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

## Third Option: -v
The -v option will output all the lines that do **not** match

### Example 1
`

`
Sentance

### Example 2
`

`
Sentance

### Example 3
`

`
Sentance

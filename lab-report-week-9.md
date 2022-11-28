# Lab Report 5

## My grade.sh script
```
#set -e
TESTJAVA=".;../lib/hamcrest-core-1.3.jar;../lib/junit-4.13.2.jar *.java"
TESTJAR=".;../lib/junit-4.13.2.jar;../lib/hamcrest-core-1.3.jar"

rm -rf student-submission
git clone $1 student-submission


cp TestListExamples.java student-submission
cd student-submission/

if [[ -f "ListExamples.java" ]]
then 
    javac -cp $TESTJAVA 
    if [[ $? -eq 0 ]]
    then
        echo "Compiled successfully"
    else 
        echo "Did not compile"
        echo "0 points"
        exit 1
    fi
    java -cp $TESTJAR org.junit.runner.JUnitCore TestListExamples > test_result.txt

    RESULT=$(grep "Tests run" test_result.txt)
    echo $RESULT

    if [[ -z $RESULT ]]
    then
        echo "You passed all the tests!"
        echo "100 Points"
        exit 1
    else
        echo "-10 points for every failure"
        exit 1
    fi

else
    echo "ListExamples file not found"
    echo "0 points"
     exit 1
fi
```

## Student Submissions

### Submission 1- list-lethods-corrected
![Prompt1](https://user-images.githubusercontent.com/70072541/204251294-bbbf0324-1b9a-4a3e-a80b-51f1d4b92fa1.png)

The implementation was perfect, so the grader gave a perfect score
### Submission 2- 
![Prompt2](https://user-images.githubusercontent.com/70072541/204251370-de2f7026-a0be-4452-ad1a-c00b964fd900.png)

The code did not compile, so the grader gave a 0
### Submission 3- 
![Prompt3](https://user-images.githubusercontent.com/70072541/204251411-19a84ce2-bf92-4d50-8d1e-c78f7a4146eb.png)

The code compiled but did not pass all the tests, so the code displays the number of failures and takes 10 points off for every failure

## Trace of grade.sh
I will be using **Submission 1** for my trace. I will be going line by line, with each line number explained below:
1.  dog
2. cat
3.
4.
5.
6.
7.
8.
9.
10.
11.
12.
13.
14.
15.
16.
17.
18.
19.
20.
21.
22.
23.
24.
25.
26.
27.
28.
29.
30.
31.
32.
33.
34.
35.
36.
37.
38.
39.
40.
41.
42.

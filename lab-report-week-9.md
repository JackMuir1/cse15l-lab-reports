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
I will be using **Submission 1- Perfect Run** for my trace. I will be going line by line, with each line number explained below:
1. Comment, no effect on program
2. Variable Assign- Stdout: nothing Stderr: nothing Exit Code: 0
3. Variable Assign- Stdout: nothing Stderr: nothing Exit Code: 0
4. Blank Line
5. Remove- Stdout: nothing Stderr: nothing Exit Code: 0
6. Clone- Stdout: Cloning into 'student-submission'... Stderr: nothing Exit Code: 0
7. Blank Line
8. Blank Line
9. Copy Path- Stdout: nothing Stderr: nothing Exit Code: 0
10. Change Directory- Stdout: nothing Stderr: nothing Exit Code: 0
11. Blank Line
12. If Statement- checks if the file "ListExamples.java" exists- true, as the file of such name exists in student-submission
13. Then- applies to above if statement
14. javac- Stdout: nothing Stderr: nothing Exit Code: 0
15. If Statement- checks if exit code above is 0- returns true, as previous line returns 0
16. Then- applies to above if statement
17. echo- Stdout: Compiled successfully Stderr: nothing Exit Code: 0
18. Else- applies to above if statement
19. Does not run- if statement does not reach the branch with this line in this run
20. Does not run- if statement does not reach the branch with this line in this run
21. Does not run- if statement does not reach the branch with this line in this run
22. fi- applies to if statement
23. java- Stdout: 
```
JUnit version 4.13.2
.....
Time: 0.013

OK (5 tests) 
Stderr: nothing Exit Code: 0
```
24. Blank 


25. Variable Assignment off of grep- Stdout: empty string Stderr: nothing Exit Code: 1 (grep returned empty string, no instances of failed tests)


26. echo- Stdout: empty string Stderr: nothing Exit Code: 0


27. Blank


32. If Statement- checks if reult variable is empty- returns true, as grep returned no lines to store in result
33. then- apllies to if statement
34. echo- Stdout: You passed all the tests! Stderr: nothing Exit Code: 0
35. echo- Stdout: 100 Points Stderr: nothing Exit Code: 0
36. exit 1- Stdout: nothing Stderr: nothing Exit Code: 1
37. else- applies to if statement
38. Does not run- if statement does not reach the branch with this line in this run
39. Does not run- if statement does not reach the branch with this line in this run
40. fi- applies to if statement
41. Blank
42. else- applies to if statement
43. Does not run- if statement does not reach the branch with this line in this run
44. Does not run- if statement does not reach the branch with this line in this run
45. Does not run- if statement does not reach the branch with this line in this run
46. fi- applies to if statement

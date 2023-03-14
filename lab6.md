#Lab 6
**This is my grade.sh file!** 
```
CPATH='.:../lib/hamcrest-core-1.3.jar:../lib/junit-4.13.2.jar'
CTEST='.:../lib/hamcrest-core-1.3.jar:../lib/junit-4.13.2.jar org.junit.runner.JUnitCore'
FILE='TestListExamples.java'

totalTests=2
score=2


rm -rf student-submission
git clone $1 student-submission
echo 'Finished cloning'
cp TestListExamples.java student-submission
#cp $CPATH student-submission
#cp $CTEST student-submission

if [[ -f $FILE ]]
then
    echo "TestListExamples found in the student-submission folder"
else
    exit 1
fi

cd student-submission

javac -cp $CPATH *.java
# echo $?
if [[ $? -eq 0 ]] #checks to see if the last command in the shell ran successfully
then 
    echo "Compiled successfully"
else
    echo "Did not compile"
    exit 1
fi

java -cp $CTEST TestListExamples > results.txt
cat results.txt

grep "testMergeRightEnd(TestListExamples)" results.txt 
if [ $? -eq 0 ]; then
    echo "1. test failure [0/1]"
    score=$((score-1))
else
    echo "1. test successful [1/1]"
fi

grep "filter(TestListExamples)" results.txt 
if [ $? -eq 0 ]; then
    echo "2. test failure [0/1]"
    score=$((score-1))
else
    echo "2. test successful [1/1]"
fi

echo "Total Score:" $score/2
```  
***Case 1***  
```bash grade.sh https://github.com/ucsd-cse15l-f22/list-methods-lab3```  
Output:  
Cloning into 'student-submission'...  
remote: Enumerating objects: 3, done.  
remote: Counting objects: 100% (3/3), done.  
remote: Compressing objects: 100% (2/2), done.  
remote: Total 3 (delta 0), reused 3 (delta 0), pack-reused 0. 
Receiving objects: 100% (3/3), done.   
Finished cloning. 
TestListExamples found in the student-submission folder. 
Compiled successfully.  
JUnit version 4.13.2.  
..E.  
Time: 0.586 
There was 1 failure:
1) testMergeRightEnd(TestListExamples)
org.junit.runners.model.TestTimedOutException: test timed out after 500 milliseconds
        at java.base@18/java.util.Arrays.copyOf(Arrays.java:3512)
        at java.base@18/java.util.Arrays.copyOf(Arrays.java:3481)
        at java.base@18/java.util.ArrayList.grow(ArrayList.java:237)
        at java.base@18/java.util.ArrayList.grow(ArrayList.java:244)
        at java.base@18/java.util.ArrayList.add(ArrayList.java:454)
        at java.base@18/java.util.ArrayList.add(ArrayList.java:467)
        at app//ListExamples.merge(ListExamples.java:42)
        at app//TestListExamples.testMergeRightEnd(TestListExamples.java:17)
        at java.base@18/java.lang.invoke.LambdaForm$DMH/0x0000000800c12400.invokeVirtual(LambdaForm$DMH)
        at java.base@18/java.lang.invoke.LambdaForm$MH/0x0000000800c13000.invoke(LambdaForm$MH)
        at java.base@18/java.lang.invoke.Invokers$Holder.invokeExact_MT(Invokers$Holder)

FAILURES!!!
Tests run: 2,  Failures: 1


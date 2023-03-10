# Lab Report 5 #
---------

I choose the option of doing my lab report based upon the lab report grading script.

### Grading Script ###

```
CPATH=".;lib/hamcrest-core-1.3.jar;lib/junit-4.13.2.jar"

rm -rf student-submission
git clone $1 student-submission
echo 'Finished cloning.'

cd student-submission
if [[ -f ListExamples.java ]]
then
    echo 'ListExamples found.'
else
    echo 'ListExamples missing, check files submitted.'
    exit 1
fi 

cp -r ../lib ./
cp ../TestListExamples.java ./

javac -cp $CPATH *.java
if [[ -f ListExamples.class ]]
then
    echo 'Compiled successfully.'
else
    echo 'Failed to compile.'
    exit 2
fi

java -cp $CPATH org.junit.runner.JUnitCore TestListExamples > error.txt
grep -v 'at ' error.txt > output.txt
grep -v 'JUnit' output.txt > error.txt
grep -v 'Time:' error.txt > output.txt
echo ''
cat output.txt


VAR=`grep -c ') ' output.txt`
echo $VAR
SCORE=$((((2-$VAR)/2)*100))
echo Score: $SCORE%
```
Written by Nathan Dowd (Lab Partner) and Aritra Dutta (me).



























## Examples of GradeScript running ##

### Example 1 ###




### Example 2 ###


### Example 3 ###

### Example 4 ###

### Example 5 ###








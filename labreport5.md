# Lab Report 5 #
---------

I choose the option of doing my lab report based upon the lab report grading script.

### Grading Script ###

```
CPATH=".:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar"

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
SCORE=$((((2-$VAR))*100)/2))
echo Score: $SCORE%
```
Writing this code, took my lab partner and I the entire period. We had to utilize all our knowledge from the lectures, and used some outside sources, such as the Tutors, and ChatGPT for help. We followed the base instructions given to us in the lab to create this script. We created CPATH with the junit paths, so we wouldnt have to keep on typing it out. Then we used if else statements to check whether ListExamples existed in the file, and whether or not it could compile. We returned the appropriate things terminating the program, if it could not compile or if file did not exist. Once our grade.sh file could run through listexamples, and check the tests, we could then create a more user friendly feedback interface. So we took out all the unnecessary information that filled up the output result. This resulted in the output primarily only showing the part that was essential in discovering what the errors were in the actual code. We also added a score on the bottom(based on a grep command finding a certain character that appears multiples times in failures), that results in what the student gets correct, so it would be easier for the grader to take from the output. 

## Examples of GradeScript running ##

### Example 1 ###

<img width="958" alt="Screen Shot 2023-03-10 at 3 47 50 AM" src="https://user-images.githubusercontent.com/112745073/224308339-1de9c455-65cb-465e-afdd-7db04e489c57.png">
Running the ListExamples.java that has no errors. 


### Example 2 ###
<img width="917" alt="Screen Shot 2023-03-10 at 3 56 29 AM" src="https://user-images.githubusercontent.com/112745073/224310051-64c67fa2-8507-4e1c-85b7-ce98780f5086.png">
Running ListExamples.java version with all errors. 

### Example 3 ###

<img width="983" alt="Screen Shot 2023-03-10 at 3 56 51 AM" src="https://user-images.githubusercontent.com/112745073/224310128-7457943e-c80a-4464-a997-c119185e2e62.png">
Failing to compile the ListExamples.java version

### Example 4 ###
<img width="951" alt="Screen Shot 2023-03-10 at 4 01 16 AM" src="https://user-images.githubusercontent.com/112745073/224310915-74e1291e-9d95-4c7b-bdc2-18ec829f874d.png">
Running ListExamples.java version with 1 error. 

### Example 5 ###

<img width="943" alt="Screen Shot 2023-03-10 at 4 03 23 AM" src="https://user-images.githubusercontent.com/112745073/224311348-c7f9cdae-37a2-4390-9e91-f281ff82bd1f.png">
Running ListExamples.java challenge version with 1 error. 







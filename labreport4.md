# *Ria Singhania*
# *A17331656* 

## 4
*Log into ieng6*
![Image](https://github.com/riasinghania/cse15l-lab-reports/blob/main/Step%204.png?raw=true)
```
<up> <up> <up> <up> <up> <enter>
ssh risinghani@ieng6.ucsd.edu
```
I ran these commands to get to the previous command I had used to log in. This is just the ssh login command. Using the <up> key I can access what I had previously used. 
## 5
*cloning repo*
![Image](https://github.com/riasinghania/cse15l-lab-reports/blob/main/step%205.png?raw=true)
```
<up> <up> <up> <up> <up> <enter>
git clone git@github.com:riasinghania/lab7.git
```
I ran these commands to get to the previous command I had used to log in. I wanted to get to the git clone command I was using to clone the forked repo using the SSH key.
## 6
*demonstrating the test fails*
![Image](https://github.com/riasinghania/cse15l-lab-reports/blob/main/step%206.png?raw=true)
```
<Ctrl-R> <up> <up> <up> <up> <enter>
<Ctrl-R> <up> <up> <up> <up> <enter>
javac -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar *.java
java -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar org.junit.runner.JUnitCore ...
```
I wanted to achieve the previous call I had made for java compile and running the tests. I used the <up> arrow to the previous time I ran these lines. 
## 7
*editing the code*
![Image](https://github.com/riasinghania/cse15l-lab-reports/blob/main/editing%20code.png?raw=true)
```
<: 44> <right arrow> <right arrow> <right arrow> <right arrow> <right arrow> <x> <a> <2> <esc> <:wq>
index2 += 1;
```
To edit the code I used vim. I firstly wanted to go to line 44 so I just did `:44` after that I needed to get to the `index1` variable and change it to `index2`. Then it was just a matter of getting out of append and saving and exiting. 
## 8
*running the tests again*

![Image](https://github.com/riasinghania/cse15l-lab-reports/blob/main/step%208.png?raw=true)
```
<Ctrl-R> <up> <up> <up> <up> <enter>
bash test.sh
```
I had previously used bash.sh to run the tests. Therefore using the <up> arrow I was able to get to this command. This is much more efficient then copying over the whole javac and java line for running a JUnit test. 
## 9
*committing the changes*

![Image](https://github.com/riasinghania/cse15l-lab-reports/blob/main/step%209.png?raw=true)
```
<Ctrl-R> <up> <up> <up> <up> <enter>
<Ctrl-R> <up> <up> <up> <up> <enter>
git add .
git push
```
Git add and git push are great ways to commit the changes. I had used these commands before, so it was just a matter of using <up> arrow to get there. Git add tracks the new file, git push commits the changes. 

*Discussion of all steps*
Working on the lab report taught me valuable lessons in efficiency when using command line tools alongside Vim. I found that utilizing the up arrow keystroke allowed me to quickly revisit previous commands, enhancing my workflow. By incorporating this method extensively, I improved my ability to navigate through files efficiently within Vim, ultimately boosting my productivity in the process.


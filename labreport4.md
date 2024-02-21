*Log into ieng6*
![Image](https://github.com/riasinghania/cse15l-lab-reports/blob/main/Step%204.png?raw=true)
```
<up> <up> <up> <up> <up> <enter>
ssh risinghani@ieng6.ucsd.edu
```

*cloning repo*
![Image](https://github.com/riasinghania/cse15l-lab-reports/blob/main/step%205.png?raw=true)
```
<up> <up> <up> <up> <up> <enter>
git clone git@github.com:riasinghania/lab7.git
```

*demonstrating the test fails*
![Image](https://github.com/riasinghania/cse15l-lab-reports/blob/main/step%206.png?raw=true)
```
<Ctrl-R> <up> <up> <up> <up> <enter>
<Ctrl-R> <up> <up> <up> <up> <enter>
javac -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar *.java
java -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar org.junit.runner.JUnitCore ...
```

*editing the code*
![Image](https://github.com/riasinghania/cse15l-lab-reports/blob/main/editing%20code.png?raw=true)
```
<: 44> <right arrow> <right arrow> <right arrow> <right arrow> <right arrow> <x> <a> <2> <esc> <:wq>
index2 += 1;
```

*running the tests again*

![Image](https://github.com/riasinghania/cse15l-lab-reports/blob/main/step%208.png?raw=true)
```
<Ctrl-R> <up> <up> <up> <up> <enter>
<Ctrl-R> <up> <up> <up> <up> <enter>
javac -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar *.java
java -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar org.junit.runner.JUnitCore ...
```

*committing the changes*

![Image](https://github.com/riasinghania/cse15l-lab-reports/blob/main/step%209.png?raw=true)
```
<Ctrl-R> <up> <up> <up> <up> <enter>
<Ctrl-R> <up> <up> <up> <up> <enter>
git add .
git push
```

*Original Post:* 

Student: I am trying to run the test.sh file to test out the ListExamples.java file. I am getting this bug but do not really know what it means or how to fix it? I assume that it has to do with something taking too long. How do I approach figuring out what to fix in ListExamples.java?

![Image](https://github.com/riasinghania/cse15l-lab-reports/blob/main/Screen%20Shot%202024-03-09%20at%201.58.13%20PM.png?raw=true)

TA response: You are on the right track with that thinking! If this the case of an infinite loop let’s say, from what type of loops could those occur and do you have any in ListExamples.java (hint: From the stack trace they gave us the line number 42 in the ListExamples class)

Student: I see that at line 42 it says get the value of index2 but then right below index2 is not incrementing. Therefore, the value will never change meaning the while loop condition will never fail out and the same index is always being taken from list2. I should probably change index1 to index2. 

![Image](http://url/a.png)


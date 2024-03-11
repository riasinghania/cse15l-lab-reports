# Ria Singhania A17331656 

# Original Post: 

Student: I am trying to run the test.sh file to test out the ListExamples.java file. I am getting this bug but do not really know what it means or how to fix it? I assume that it has to do with something taking too long. How do I approach figuring out what to fix in ListExamples.java?

![Image](https://github.com/riasinghania/cse15l-lab-reports/blob/main/Screen%20Shot%202024-03-09%20at%201.58.13%20PM.png?raw=true)

TA response: You are on the right track with that thinking! If this the case of an infinite loop let’s say, from what type of loops could those occur and do you have any in ListExamples.java (hint: From the stack trace they gave us the line number 42 in the ListExamples class)

Student: I see that at line 42 it says get the value of index2 but then right below index2 is not incrementing. Therefore, the value will never change meaning the while loop condition will never fail out and the same index is always being taken from list2. I should probably change index1 to index2. 

![Image](https://github.com/riasinghania/cse15l-lab-reports/blob/main/Screen%20Shot%202024-03-09%20at%202.30.01%20PM.png?raw=true)

# Information about setup

Directory/Files setup:
```
Lab7/
  lib/
    hamcrest-core-1.3.jar
    junit-4.13.2.jar
  ListExamples.class
  ListExamples.java
  ListExamplesTests.class
  ListeExamplesTests.java
  StringChecker.class
  test.sh
```

ListExamples.java content BEFORE:
```
import java.util.ArrayList;
import java.util.List;

interface StringChecker { boolean checkString(String s); }

class ListExamples {

  // Returns a new list that has all the elements of the input list for which
  // the StringChecker returns true, and not the elements that return false, in
  // the same order they appeared in the input list;
  static List<String> filter(List<String> list, StringChecker sc) {
    List<String> result = new ArrayList<>();
    for(String s: list) {
      if(sc.checkString(s)) {
        result.add(s);
      }
    }
    return result;
  }

  // Takes two sorted list of strings (so "a" appears before "b" and so on),
  // and return a new list that has all the strings in both list in sorted order.
  static List<String> merge(List<String> list1, List<String> list2) {
    List<String> result = new ArrayList<>();
    int index1 = 0, index2 = 0;
    while(index1 < list1.size() && index2 < list2.size()) {
      if(list1.get(index1).compareTo(list2.get(index2)) < 0) {
        result.add(list1.get(index1));
        index1 += 1;
      }
      else {
        result.add(list2.get(index2));
        index2 += 1;
      }
    }
    while(index1 < list1.size()) {
      result.add(list1.get(index1));
      index1 += 1;
    }
    while(index2 < list2.size()) {
      result.add(list2.get(index2));
      index1 += 1; 
    }
    return result;
  }
}
```

ListExamplesTests.java content BEFORE:
```
import static org.junit.Assert.*;
import org.junit.*;
import java.util.*;
import java.util.ArrayList;


public class ListExamplesTests {
	@Test(timeout = 500)
	public void testMerge1() {
    	List<String> l1 = new ArrayList<String>(Arrays.asList("x", "y"));
		List<String> l2 = new ArrayList<String>(Arrays.asList("a", "b"));
		assertArrayEquals(new String[]{ "a", "b", "x", "y"}, ListExamples.merge(l1, l2).toArray());
	}
	
	@Test(timeout = 500)
        public void testMerge2() {
		List<String> l1 = new ArrayList<String>(Arrays.asList("a", "b", "c"));
		List<String> l2 = new ArrayList<String>(Arrays.asList("c", "d", "e"));
		System.out.println(ListExamples.merge(l1, l2).toArray());
		assertArrayEquals(new String[]{ "a", "b", "c", "c", "d", "e" }, ListExamples.merge(l1, l2).toArray());
        }

}
```

test.sh content BEFORE:
```
javac -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar *.java
java -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar org.junit.runner.JUnitCore ListExamplesTests
```
# What triggered the bug?

Running `test.sh` which compiled and ran the tests within `ListExamplesTests.java` triggered the error. This is because there is a timeout requirement for each tests and `testMerge2` took longer than the time alotted. 
  Also, directly runnng `javac -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar *.java` and `java -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar org.junit.runner.JUnitCore ListExamplesTests` could cause they same error. 

# Fix

Changing line 42 in `ListExamples.java` fixed the bug. `index1` should have been `index2` to allow the resulting array to be consistently updated.

# Reflection
Reflecting on my CSE 15 lab course at UCSD, I gained learned about valuable terminal tools like 'vim' and 'jdb' as well as useful commands like 'cd', and 'ls'. These significantly boosted my programming efficiency and comfort with my machine. 'Vim' was particularly interesting because of its its cursor-free file editing, offering a quicker and more streamlined approach to fixing errors and navigating code. Mastering these tools not only sped up my coding but also deepened my understanding of terminal functionalities. I had a valuable time in CSE 15L an will defeiently use my knoweldge in future programming classes. 


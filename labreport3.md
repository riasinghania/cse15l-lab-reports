# *Ria Singhania*
# *A17331656* 

# Part 1: buggy program
I am choosing the buggy program of `reverse`

Failure Inducing Test
```
 @Test
  public void testReversedPersonal() { //element 0 was 0
    int[] input1 = {4, 5, 6, 7};
    assertArrayEquals(new int[]{7, 6, 5, 4 }, ArrayExamples.reversed(input1));
  }
```

Successful Inducing Test
```
@Test
  public void testReversed() {
    int[] input1 = { };
    assertArrayEquals(new int[]{ }, ArrayExamples.reversed(input1));
  }
```
These are the test output when I try the successful input.
![Image](https://github.com/riasinghania/cse15l-lab-reports/blob/main/Screen%20Shot%202024-02-07%20at%202.56.55%20PM.png?raw=true)
These are the test output, aka the failure of the tests when running the failure inducing input. 
![Image](https://github.com/riasinghania/cse15l-lab-reports/blob/main/Screen%20Shot%202024-02-07%20at%202.48.54%20PM.png?raw=true)

This the code before the fix:
```
static int[] reversed(int[] arr) {
    int[] newArray = new int[arr.length];
    for(int i = 0; i < arr.length; i += 1) {
      newArray[ i ] = arr[arr.length - i - 1];
    }
    return arr;
  }
```
This the code after the fix:
```
static int[] reversed(int[] arr) {
    int[] newArray = new int[arr.length];
    for(int i = 0; i < arr.length; i += 1) {
      newArray[ i ] = arr[arr.length - i - 1];
    }
    return newArray;
  }
```
The fix that I made was changing the return value to the new array. Before it was just `arr` which was the original array, no changes. `newArray` is the reversed array which is what should be returned. 

# Part 2: researching commands
I found alternatives for the `find` command
The alternatives I found via chatGPT:
1. case insensitive name search: `-iname <pattern>` 
2. search by type: `-type <f|d|l|...>`
3. search by size: `-size [+|-]<size>[c|k|M|G]`
4. name: `-name <pattern>`

**`-iname <pattern>`**
 ```
find ./technical -iname "*.txt"

./technical/plos/pmed.0020074.txt
./technical/plos/journal.pbio.0020146.txt
./technical/plos/pmed.0020114.txt
./technical/plos/pmed.0010028.txt
./technical/plos/journal.pbio.0020350.txt
./technical/plos/journal.pbio.0020190.txt
./technical/plos/pmed.0010029.txt
./technical/plos/pmed.0020115.txt
  ...so many more...
```
*this example is searching for all of the .txt files. It does not care whether they are capitalized or not.*
 ```
find ./technical -iname "biomed"

./technical/biomed
 ```
*this example is searching for all of the "biomed" files/directories within the "technical" directory. It does not care whether they are capitalized or not, however there is only one biomed directory directly under technical*

**`-type <f|d|l|...>`**
 ```
find ./technical -type f

./technical/plos/pmed.0020074.txt
./technical/plos/journal.pbio.0020146.txt
./technical/plos/pmed.0020114.txt
./technical/plos/pmed.0010028.txt
./technical/plos/journal.pbio.0020350.txt
./technical/plos/journal.pbio.0020190.txt
./technical/plos/pmed.0010029.txt
./technical/plos/pmed.0020115.txt
  ...so many more...
 ```
*this example is searching for all of the files within technical. The type f specifies that we are looking for files.*
 ```
 find ./technical -type d

 ./technical
./technical/government
./technical/government/About_LSC
./technical/government/Env_Prot_Agen
./technical/government/Alcohol_Problems
./technical/government/Gen_Account_Office
./technical/government/Post_Rate_Comm
./technical/government/Media
./technical/plos
./technical/biomed
./technical/911report
 ```
*this example is searching for all of the directories within technical. The type d specifies that we are looking for directories.*

**`-size [+|-]<size>[c|k|M|G]`**
 ```
./technical -size -100k

./technical/plos/pmed.0020074.txt
./technical/plos/journal.pbio.0020146.txt
./technical/plos/pmed.0020114.txt
./technical/plos/pmed.0010028.txt
./technical/plos/journal.pbio.0020350.txt
./technical/plos/journal.pbio.0020190.txt
./technical/plos/pmed.0010029.txt
./technical/plos/pmed.0020115.txt
  ...so many more...
 ```
*this example is searching for all of the files that are 100 kilobytes or less in size.*
 ```
./technical -size -500c

./technical
./technical/government
./technical/government/Alcohol_Problems
 ```
*this example is searching for all of the files that are 500 bytes or less in size.*

**`-name <pattern>`**
 ```
find ./technical -name "*.txt"

./technical/plos/pmed.0020115.txt
./technical/plos/journal.pbio.0020147.txt
./technical/plos/pmed.0020075.txt
./technical/plos/pmed.0020061.txt
./technical/plos/pmed.0020210.txt
./technical/plos/pmed.0020238.txt
./technical/plos/journal.pbio.0030051.txt
./technical/plos/journal.pbio.0020068.txt
./technical/plos/journal.pbio.0020054.txt
./technical/plos/journal.pbio.0020040.txt
./technical/plos/pmed.0010066.txt
./technical/plos/journal.pbio.0030131.txt
./technical/plos/journal.pbio.0020337.txt
  ...so many more...
 ```
*this example is searching for all of the files that have "txt" in the name. This is in a lot of files extensions so a lot are returned.*
 ```
find ./technical -name "*1.txt"

./technical/government/Env_Prot_Agen/1-3_meth_901.txt
./technical/government/Env_Prot_Agen/nov1.txt
./technical/government/Gen_Account_Office/og96011.txt
./technical/government/Gen_Account_Office/og97051.txt
./technical/government/Gen_Account_Office/og97041.txt
./technical/government/Gen_Account_Office/og96031.txt
./technical/government/Gen_Account_Office/og96021.txt
./technical/government/Gen_Account_Office/og98041.txt
./technical/government/Gen_Account_Office/og97011.txt
./technical/government/Gen_Account_Office/og96041.txt
./technical/government/Gen_Account_Office/d02701.txt
./technical/government/Gen_Account_Office/og97001.txt
...so many more...
 ```
*this example is searching for all of the files that have "1.txt" in the name. This means the txt file must have 1 in the name somwhere.*

# citing sources
I used chatGPT and here are my prompts and outputs 
 ```
provide command-line options for find
 ```
output: 
![Image](https://github.com/riasinghania/cse15l-lab-reports/blob/main/Screen%20Shot%202024-02-13%20at%2010.06.30%20AM.png?raw=true)
![Image](https://github.com/riasinghania/cse15l-lab-reports/blob/main/Screen%20Shot%202024-02-13%20at%2010.06.40%20AM.png?raw=true)
![Image](https://github.com/riasinghania/cse15l-lab-reports/blob/main/Screen%20Shot%202024-02-13%20at%2010.06.50%20AM.png?raw=true)
 I changed this by picking the specific examples of `iname, type, size, and name`. 


 
 ```
Can you show an example of using the search by size search in the command line
 ```
output
![Image](https://github.com/riasinghania/cse15l-lab-reports/blob/main/Screen%20Shot%202024-02-13%20at%2010.12.56%20AM.png?raw=true)
 I changed this by picking the specific examples of putting the path I wanted to use as`./technical`. 

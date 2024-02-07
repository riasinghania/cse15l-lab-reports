
# Part 2: buggy program
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
4. access time: `-atime <n>`

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
 ```
find ./technical -iname "biomed"

./technical/biomed
 ```

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

 ```
./technical -size -500c

./technical
./technical/government
./technical/government/Alcohol_Problems
 ```

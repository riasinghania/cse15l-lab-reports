
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
![Image](https://github.com/riasinghania/cse15l-lab-reports/blob/main/Screen%20Shot%202024-02-07%20at%202.48.54%20PM.png?raw=true)
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

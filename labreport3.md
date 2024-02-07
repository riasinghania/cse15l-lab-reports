
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

Kevin Yu
CSE 15L Lab 2
1/30/23

> Part 1









> Part 2

The code I am choosing to work with is the code with testReversed2:
The failure inducing code for the program is: 
```
public void testReverse2() {
int input1 = {1,2,3,4,5}
assertArrayEquals(new int[]{5,4,3,2,1, ArrayExamples.reversed(input1)}
```

The code that runs without failure is:
```
public void testReverse2() {
int input1 = {1,2,3,4,5}
assertArrayEquals(new int[]{5,4,3,2,1, ArrayExamples.reversed(input1)}
```

The symptom upon running the tests is:
![image](https://user-images.githubusercontent.com/122575342/215650120-e4a13052-df9e-4992-98fa-b4472149398b.png)

before:
```
static int[] reversed(int[] arr) {
    int[] newArray = new int[arr.length];
    for(int i = 0; i < arr.length; i += 1) {
      arr[i] = newArray[arr.length - i - 1];
    }
    return arr;
  }
 ```
after:
```
static int[] reversed(int[] arr) {
    int[] newArray = new int[arr.length];
    for(int i = 0; i < arr.length; i += 1) {
      newArray[i] = arr[arr.length - i - 1];
    }
    return arr;
  }
  ```
  The reason the correction above fixes the issue is that in the previous version, you can see that a newArray is intialized for the reversion process, however, the assignment of new variables is set up in a way that the for loop assings the original array to the empty index locations of the newArray. To fix this, we simply switch 
`arr[i] = newArray[arr.length - i - 1];` and `newArray[i] = arr[arr.length - i - 1];` and this will start assinging the empty newArray with the reversed positions of the old arr.

> Part 3

Something new I learned during the course in week 2 was the utility of working on code while connected to a remote server. As shown in the lab, users were able to connect and visit the work of whoever is connected. This could prove extremely useful in giving feedback on a peers code in real time as they can make updates to their code and anyone connected is able to then see these changes and provide feedback if there were something they wanted to adress. 





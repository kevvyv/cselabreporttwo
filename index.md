Kevin Yu
CSE 15L Lab 2
1/30/23

> Part 1

![image](https://user-images.githubusercontent.com/122575342/215654697-5080924c-2129-443b-a1c5-5eb69f313585.png)

When `/add-message?s` is called, the HandleString method is called. The relevant argument to this method is that a url must be passed in and the method will look for
the sequence of `/add-message?s` within the URL and if it is detected, the InputString variable is updated to also include the string that is provided after the
`/add-message?s`. Firstly, an inputString is initialized as this will be the string that gets continually added to each time the add-message is called. Then, 'url.getpath' is called and the method checks if the path contains 'add-message'. If so, then the method will call 'url.getQuery()' and split by the equals sign which ensures the string from the url is obtain, and then add this obtained string to the current inputString. The method will finally print a message contatining all the strings in InputString.




> Part 2

The code I am choosing to work with is the code with testReversed2:
The failure inducing code for the program is: 
```
public void testReverse2() {
int input1 = {1,2,3,4,5}
assertArrayEquals(new int[]{5,4,3,2,1}, ArrayExamples.reversed(input1)}
```

The code that runs without failure is:
```
public void testReverse2() {
int input2 = {1,8,9}
assertArrayEquals(new int[]{9,8,1} ArrayExamples.reversed(input2)}
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
    return newArray;
  }
  ```
  The reason the correction above fixes the issue is that in the previous version, you can see that a newArray is intialized for the reversion process, however, the assignment of new variables is set up in a way that the for loop assings the original array to the empty index locations of the newArray. To fix this, we simply switch 
`arr[i] = newArray[arr.length - i - 1];` and `newArray[i] = arr[arr.length - i - 1];` and this will start assinging the empty newArray with the reversed positions of the old arr.

> Part 3

Something new I learned during the course in week 2 was the utility of working on code while connected to a remote server. As shown in the lab, users were able to connect and visit the work of whoever is connected. This could prove extremely useful in giving feedback on a peers code in real time as they can make updates to their code and anyone connected is able to then see these changes and provide feedback if there were something they wanted to adress. 





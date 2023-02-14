
**Lab 2**  
###Part 1
***StringServer***

![StringServerCode](StringServer.png)





![Hello.png](Hello.png)  
* getPath(),getQuery() add() 
* The parameters changed to string objects.


![Hello+HowAreYou.png](Hello+HowAreYou.png)
* getPath(),getQuery() add() 
* The parameters changed to string objects
* The arraylist contains Hello /n How are you


1.  
```
public void testReverse2InPlace(){

    int[]input1 = {1,2,3,4,5};
    ArrayExamples.reverseInPlace(input1);
    assertArrayEquals(new int[]{5,4,3,2,1}, input1);


 }
```
 
 
2.  
```
public void testReverse2InPlace(){

    int[]input1 = {3};
    ArrayExamples.reverseInPlace(input1);
    assertArrayEquals(new int[]{5,4,3,2,1}, input1);


 }
```
Symptoms
![junitoutput](junitoutputs.png)

Code Before:
```
static void reverseInPlace(int[] arr) {

    for(int i = 0; i < arr.length; i += 1) {
      arr[i] = arr[arr.length - i - 1];
    }  
}
```

Code After:
```
static void reverseInPlace(int[] arr) {

    int newArr[] = new int [arr.length];
    int j = arr.length;
    for(int i = 0; i < arr.length; i += 1) {
      newArr[j-1] = arr[i];
      j--;
    }
    
    for(int i = 0; i<arr.length; i++){
      arr[i]=newArr[i];

    }
}
```
###Part 2

Creates a separate array to store the contents of the reversed array into a new array. Then uses a forloop to assign supplied array with the reversed contents of the array by the index starting from 0 until the end of the array. 

###Part 3

From Week 2 I learned what you could do on the remote server and understood that If I wanted to make changes to that server I would first need to get a copy of the remote server onto my local machine. For nay changes I make on my local directory I would need to commit by either using the Github desktop application or the command to update the server. 



# Lab_Report_2
## Part 1:

First extension:
<img width="1440" alt="Screen Shot 2023-04-24 at 11 01 02 PM" src="https://user-images.githubusercontent.com/130112383/234188014-7579cc9d-8778-4696-ac18-0c98edbb574d.png">
- In this image I added apple into the list

Second extension:
<img width="1440" alt="Screen Shot 2023-04-24 at 11 01 22 PM" src="https://user-images.githubusercontent.com/130112383/234188066-6abdf5fa-5f4b-4501-9ee4-5d6d7ba21fbf.png">
- In this second image I added orange after apple
Code:
<img width="1440" alt="Screen Shot 2023-04-24 at 11 03 10 PM" src="https://user-images.githubusercontent.com/130112383/234188103-09a42b3a-8b80-4276-bb42-2e0ace03d7ff.png">

Description of Code and Screenshots:
1. The method that is being called is handleRequest.
2. The first extension that was added is `add-message?s=Apple`. In the if statement it checks if it contains `add-message` and then splits between the equal sign to get the string `Apple`. It then adds that new message into an arraylist and returns it.
3. The second extension does the same thing, `Orange` gets added after `Apple`.

## Part 2:

Failure Inducing Input:

```
@Test 
	public void testReverseInPlace() {
    int[] input1 = { 1, 2, 3, 4, 5};
    ArrayExamples.reverseInPlace(input1);
    assertArrayEquals(new int[]{ 5, 4, 3, 2, 1 }, input1);
	}


  @Test
  public void testReversed() {
    int[] input1 = { 1, 2, 3, 4, 5 };
    assertArrayEquals(new int[]{ 5, 4, 3, 2, 1 }, ArrayExamples.reversed(input1));
  }
```

An Input that doesn't induce a failure:

The Symptom:
<img width="1440" alt="Screen Shot 2023-04-20 at 4 36 46 PM" src="https://user-images.githubusercontent.com/130112383/234190326-06d266ab-153e-4dc5-8269-2107663e23d0.png">

The bug before and after:
Before:
<img width="1396" alt="Screen Shot 2023-04-24 at 11 23 48 PM" src="https://user-images.githubusercontent.com/130112383/234191793-169ac6a7-58de-4719-8579-79f101889a95.png">
After:
```
static void reverseInPlace(int[] arr) {
    for(int i = 0; i < arr.length/2; i += 1) {
      int var = arr[i];
      arr[i] = arr[arr.length - i - 1];
      arr[arr.length - i - 1] = var;
    }
  }
 ```
 ```
 static int[] reversed(int[] arr) {
    int[] newArray = new int[arr.length];
    for(int i = 0; i < arr.length; i += 1) {
      newArray[i] = arr[arr.length - i - 1];
    }
    return newArray;
  }
```

Fix Explanation:
This fix worked because for testReverseInPlace instead of making a whole for loop, only loop half and assign a new variable. For reversed, it was returning the wrong array.


## Part 3:

Something new I learned during week 2 and week 3 consists of creating a new server and learning how to debug a program efficiently. I have never created a new server and I didn't know you could add extensions at the end of the url and have it performed on the page. 

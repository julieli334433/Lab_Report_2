# Lab_Report_2
In this lab, it shows what I have learned over the past weeks about servers and bugs.
## Part 1:
For part 1, I created a new server called StringServer by copying the code from NumberServer in the wavelet folder into a new file. After that I have made some adjustments to the code such as changing the class name to StringServer and changing to how the server is suppose to behave. I changed the if statement so that you can add multiple strings and have it displayed on the page.

Here is my Code for the implementation:
<img width="1440" alt="Screen Shot 2023-04-24 at 11 03 10 PM" src="https://user-images.githubusercontent.com/130112383/234188103-09a42b3a-8b80-4276-bb42-2e0ace03d7ff.png">

**How I implemented this:**
1. I first created a string `s` with nothing stored in it. 
2. Then I added an if statement with `url.getPath().contains("add-message")`. This means that this checks if the extension added will contain "add-message".
3. Next I created an array called parameters split with the `=` sign by using the `url.getQuery().split('=')`. This works by just getting the query part of the path being `s=<string>`. This splits between the `=` and creates 2 parts which is `s` and `<string>`. With these 2 parts they are stored inside the array. 
4. I then created another if statement to check if the first part of parameters is equal to s, if it is, then proceed with the next step.
5. Then I update the the string `s` in the beginning, and I concatenated the second part of the query and added `\n` meaning add a line, so when you add a second string, it will go down to next line. 
6. Last step is to return the string shown here at the first extension.

**First extension:**
- In this image I added Apple into the list using `add-message?s=Apple` to the url. So first this get checked if it contains `add-message`, if it does then it gets updated and concatenates the string `Apple` into the array. 

<img width="1440" alt="Screen Shot 2023-04-24 at 11 01 02 PM" src="https://user-images.githubusercontent.com/130112383/234188014-7579cc9d-8778-4696-ac18-0c98edbb574d.png">

**Second extension:**
- In this second image I added `Orange` after `Apple` using `add-message?s=Orange` to the url. This gets checked if it contains `add-message`, if it does then it gets updated and concatenates the string `Orange` with `Apple` into the array. 
- How this works is due to the implementation explained above. So first `Apple` is added, then it concatenates with `Orange` moving it to the next line, that is why `Orange` is below `Apple`.

<img width="1440" alt="Screen Shot 2023-04-24 at 11 01 22 PM" src="https://user-images.githubusercontent.com/130112383/234188066-6abdf5fa-5f4b-4501-9ee4-5d6d7ba21fbf.png">


## Part 2:
- In part 2, this will be addressesing the bug in the program.

**Failure Inducing Input:**

```
@Test 
	public void testReverseInPlace() {
    int[] input1 = { 1, 2, 3, 4, 5};
    ArrayExamples.reverseInPlace(input1);
    assertArrayEquals(new int[]{ 5, 4, 3, 2, 1 }, input1);
	}
```

**An Input that doesn't induce a failure:**

```
public void testReverseInPlace() {
    int[] input1 = { 3 };
    ArrayExamples.reverseInPlace(input1);
    assertArrayEquals(new int[]{ 3 }, input1);
  }
```

**The Symptom:**
- In this screenshot, it shows the symptom of the code, showing 2 failures. 
<img width="1440" alt="Screen Shot 2023-04-20 at 4 36 46 PM" src="https://user-images.githubusercontent.com/130112383/234190326-06d266ab-153e-4dc5-8269-2107663e23d0.png">

**The bug before and after:**

**Before:**
Why it doesn't work?
- This code does not work because reverseInPlace method switches the elements around in the array but it changes the first half of the elements before changing the second half of the elements so the second half remains the same.


<img width="1396" alt="Screen Shot 2023-04-24 at 11 23 48 PM" src="https://user-images.githubusercontent.com/130112383/234191793-169ac6a7-58de-4719-8579-79f101889a95.png">

**After:**
```
static void reverseInPlace(int[] arr) {
    for(int i = 0; i < arr.length/2; i += 1) {
      int var = arr[i];
      arr[i] = arr[arr.length - i - 1];
      arr[arr.length - i - 1] = var;
    }
  }
 ```

Fix Explanation:
This fix worked because for testReverseInPlace instead of making a whole for loop, only loop half and assign a new variable. The new variable would be called `var` storing the element before it gets changed. Then I changed the second half of the array at the specific index to become the `var` value. Now the first half of the elements will not get replaced by the back half, before storing the values of the first half of the array. Now the first and last element will be changed simultaneously.


## Part 3:

Something new I learned during week 2 and week 3 consists of creating a new server and learning how to debug a program efficiently. I have learned the code and steps to take when creating a new server. I have never created a new server and I didn't know you could add extensions at the end of the url and have it performed on the page. I didn't know you can check the path of the url and add strings or search up strings using the server. This was really suprising and cool, and I can definitely use this in other projects. 

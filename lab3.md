# LAB REPORT 3

## PART 1

Provide:

+ A failure-inducing input for the buggy program, as a JUnit test and any associated code (write it as a code block in Markdown).
 - `int[] input = [1, 2, 3];` (multiple elements in the list with different values each)

``@Test
  public void replaceInPlaceTest(){
    int[] input = {1};
    ArrayExamples.reverseInPlace(input);
    assertArrayEquals(new int[]{1}, input);
    }``
    
+ An input that doesn't induce a failure, as a JUnit test and any associated code (write it as a code block in Markdown).
  - `int[] input = {1};` (when there is only one element in the input list) or when all the elements are the same value

`  @Test
  public void replaceInPlaceTest2(){
    int[] input = {1,2,3};
    ArrayExamples.reverseInPlace(input);
    assertArrayEquals(new int[]{3,2,1}, input);
  }`
+ The symptom, as the output of running the two tests above (provide it as a screenshot -- one test should pass, one test should fail).
  - <img width="355" alt="image" src="https://github.com/ebyildiz/cse15l-lab-reports/assets/131305803/5a4972e6-b9a9-4253-a76a-88a3cf505de3">
  - <img width="359" alt="image" src="https://github.com/ebyildiz/cse15l-lab-reports/assets/131305803/45df4957-a64a-401f-a9dd-04f2b858f4af">
  - As you can see, replaceInPlaceTest2 fails, but replaceInPlaceTest passes
+ The bug, as the before-and-after code change required to fix it (as two code blocks in Markdown).
  - The bug is right here: `arr[i] = arr[arr.length - i - 1];` in each turn in the loop, we are assigning the element at index i to element at index arr.length - i - 1. So for example, if i=0, then arr[0] gets assigned to the last element. And arr[1] gets assigned to the element before that:
  `static void reverseInPlace(int[] arr) {
    for(int i = 0; i < arr.length; i += 1) {
      arr[i] = arr[arr.length - i - 1];
    }
  }`
  - The problem with this approach is that we don't assign the last element back to the first one. So if we have an array like {1,2,3,4} it will end up being {4,3,3,4} because we did not assign the fourth element to 1 and third element to 2. To fix this issue, we need to first save the value at index i to not lose it when we reassign it to something else. And then we can assign the value at index arr.length -i -1 to the value that we saved. Here's the fixed code:
    `  static void reverseInPlace(int[] arr) {
    for(int i = 0; i < arr.length/2; i += 1) {
      int saved = arr[i];
      arr[i] = arr[arr.length - i - 1];
      arr[arr.length - i - 1] = saved;
    }
  }`
+ Briefly describe (2-3 sentences) why the fix addresses the issue.
 - I already said it in my explanation, but the fix addresses the issue since it also assigns the element at index arr.length - i - 1 to the element used to be in index i. This way that actually replaces places, when before, it was only copying the elements at the end of the list to the beginning of the list and not reversing the items.

## PART 2
### I chose `grep` for part 2. 
+ The first useful feature of this command it to find files or directories that contains a specific string by using `-w`. It's useful for checking if the information we are looking for is in a file especially if it has long text. Here are the two examples where my pwd is ~/technical and then ~/technical/biomed
  - <img width="332" alt="image" src="https://github.com/ebyildiz/cse15l-lab-reports/assets/131305803/58c857b6-35a3-44ce-8fc2-9814a476f5c9">
  - <img width="468" alt="image" src="https://github.com/ebyildiz/cse15l-lab-reports/assets/131305803/803efda9-b120-41ab-953b-4238f2f4f17c">

+ The second interesting feature is that you can make the files display only the parts where the specific string appears with option `-o`. And the other parts won't be displayed. I think it's a good way of seeing how often a specific text appears in a file if we want to see if the file contains enough information about what we are looking for and is worth to look at. Here are the examples where my pwd is ~/technical/biomed:
 - <img width="361" alt="image" src="https://github.com/ebyildiz/cse15l-lab-reports/assets/131305803/7f33a7ee-bc57-4292-80a1-561c14a6708e">
 - <img width="388" alt="image" src="https://github.com/ebyildiz/cse15l-lab-reports/assets/131305803/134d61bb-3e23-4ad0-b9f6-621cd56251f2">

+ The third option is `-n` which allows you to get the line index of a file where the line is matched. That way the specific lines can be found more easily when we are looking at the file. Here are the examples (my pwd is still the same):
  - <img width="466" alt="image" src="https://github.com/ebyildiz/cse15l-lab-reports/assets/131305803/1f749e43-bf7a-4bdc-b29c-8c024a27f48e">
  - <img width="440" alt="image" src="https://github.com/ebyildiz/cse15l-lab-reports/assets/131305803/cd8a0298-dee3-4a89-a4ec-4cfa02fe4040">

+ The last option I chose is `-v` which helps you to only show the lines of a file where the string specified is not matching. It is useful when we have a file that is repeating itself with information that is not useful for us, so we can exclude it. Here are the examples where my pwd is the same:
  - <img width="442" alt="image" src="https://github.com/ebyildiz/cse15l-lab-reports/assets/131305803/056b4376-35a9-4319-b94e-db534c08dd41">
  - <img width="478" alt="image" src="https://github.com/ebyildiz/cse15l-lab-reports/assets/131305803/864053c8-d6ec-4d91-8a2e-76301237c23d">

### [sources used] (https://www.geeksforgeeks.org/grep-command-in-unixlinux/)

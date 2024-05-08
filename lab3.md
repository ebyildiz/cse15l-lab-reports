# LAB REPORT 3

## PART 1

Provide:

+ A failure-inducing input for the buggy program, as a JUnit test and any associated code (write it as a code block in Markdown).
 - `int[] input = [1, 2, 3];` (multiple elements in the list with different values each)
`   @Test
  public void replaceInPlaceTest(){
    int[] input = {1};
    ArrayExamples.reverseInPlace(input);
    assertArrayEquals(new int[]{1}, input);
    }`
+ An input that doesn't induce a failure, as a JUnit test and any associated code (write it as a code block in Markdown).
  - `int[] input = {1};` (when there is only one element in the input list) or when all the elements are the same value
  - `  @Test
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


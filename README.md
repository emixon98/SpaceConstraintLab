# SpaceConstraintLab
Lab for CISC 187 on space complextiy
### Task 1: Decrible the "Word Builder" Algorithm in terms of Big O space complexity

This function is creating an array called collection, in which we iterate through all elements of an array and attempt to find combinations in which two elements are not the same. In this case the space complexity would in worst case each element has no other repeat cases which would lead to a pairing with each other element but itself or (n * (n-1)) cases providing an O(n^2) space complexity.

### Task 2: Describe the reversed array function in terms of Big O space complexity

This function merely takes an array and begins inserting its elements into a new array descending from the last element to the first. In which case we have alloted memory for an array that is n elements, where n is the amount of elements in the first array, giving a space complexity of O(n). 

### Task 3: Create a new function to reverse an array that takes up O(1) extra space

Using C++ we can create a function that passes in the array by reference, allowing us to directly alter it and not a copy. We can also achieve the reversal through only allocating memory for a few variables, temp, left, and right in the case of this problem. We allocate memory for 3 variables which is O(3), and since constants drop in big O notation it simplifies to O(1). Our left and right variables are assigned to the first and last index of the array, we can increment left and decrement right to ensure we are slowly "walking" the array from both ends and reordering/swapping in our loop.

ex) array = [1, 2, 3, 4]
1 pass: array=[4,2,3,1]
2 pass: array = [4,3,2,1]

```cpp
void revArr(vector<int>& arr){
    int left = 0;
    int right = arr.size() - 1;

    while(left < right){
        int temp = arr[left];
        arr[left] = arr[right];
        arr[right] = temp;
        left++;
        right--;
    }
}
```

### Task 4: Fill in the table to describe the efficiency of the three functions that multiply an arrays elements by 2
Version 1: Time Complexity: O(n) 
Version 1: Space Complexity: O(n) - We create an array newArray of n size
Version 2: Time Complexity: O(n) 
Version 2: Space Complexity: O(1) - we modify the original array and create no new memory
Version 3: Time Complexity: O(n) 
Version 3: Space Complexity: O(n) - each recursion adds a call to the stack which is an allocation in memory
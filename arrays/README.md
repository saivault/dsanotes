<h1>Arrays</h1>
An array is a collection of elements of the same type placed in contiguous memory locations. <br>

Ways to create an array in C++
```cpp
int arr[100];
int arr[100] = {0};
int arr[] = {1,2,3};
string snacks[2] = {"chocolate", "noodles"};
```

<br>
<h1>Maximum Element in an array</h1>


```cpp
int func(int arr[], int n) {
    int max = arr[0];
    for (int i = 1; i < n; i++) {
        if (max < arr[i]) max = arr[i];
    } 
    return max;
}
```

<h1>Fizz Buzz</h1>

Given an integer `n`, Write a function `fizzBuzz` that returns a vector `res` with the numbers from 1 to n with the following restrictions <br>
- res[i] == "FizzBuzz" if i is divisible by 3 and 5. <br>
- res[i] == "Fizz" if i is divisible by 3. <br>
- res[i] == "Buzz" if i is divisible by 5. <br>
- res[i] == i (as a string) if none of the above conditions are true. <br><br>


Click [here](https://leetcode.com/problems/fizz-buzz/) for the problem link <br><br><br>

```cpp
vector<string> fizzBuzz(int n) {
        vector<string> res;
        for (int i=1; i<=n; i++) {
            if ((i%15) == 0) res.push_back("FizzBuzz");
            else if ((i%3) == 0) res.push_back("Fizz");
            else if ((i%5) == 0) res.push_back("Buzz");
            else res.push_back(to_string(i));
        }
        return res;
}
```

<br><br>
<h1>Segregate 0s and 1s in an array</h1>
You are given an array of 0s and 1s in random order. Segregate 0s on left side and 1s on right side of the array [Basically you have to sort the array]. <br> Traverse array only once. 
<br><br>

```cpp
vector<int> segregate(vector<int> &arr) {
    int left=0, right=arr.size()-1;
    while (left < right) {
        if (arr[left] == 0) left++;
        else if (arr[right] == 1) right--;
        else {
            arr[left++] = 0;
            arr[right--] = 1;
        }
    }

    return arr;
}
```

<br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br>

<h1>Two Number Sum</h1>

Given an array of integers `arr` and an integer `target`, return the two numbers such that they add up to `target`.

You may assume that each input would have exactly one solution, and you may not use the same element twice.

You can return the answer in any order.

 

**Example 1:**<br>
Input: nums = [2,7,11,15], target = 9<br>
Output: [2,7]<br>

**Example 2:**<br>
Input: nums = [3,2,4], target = 6<br>
Output: [2,4]<br>

**Example 3:**<br>
Input: nums = [3,3], target = 6<br>
Output: [3,3]<br>
 

**Constraints:**<br>
2 <= nums.length <= 104<br>
-109 <= nums[i] <= 109<br>
-109 <= target <= 109<br>
Only one valid answer exists.<br>
 

**Follow-up:**<br>
Can you come up with an algorithm that is less than O(n<sup>2</sup>) time complexity ?

Click [here](https://leetcode.com/problems/two-sum/) for the problem link <br><br><br>


```cpp
vector<int> twoSum(vector<int>& arr, int target) {
    // Your code ...
}
```

<br><br><br><br><br><br><br><br><br><br><br><br><br><br>

## Sorting Approach

```cpp
vector<int> twoSum(vector<int>& arr, int target) {
    vector<int> res;
    sort(arr.begin(), arr.end())
    int left = 0, right = arr.size()-1;
    
    while (left < right){
        if (arr[left] + arr[right] > target) right--;
        else if (arr[left] + arr[right] < target) left++;
        else {
            res.push_back(arr[left]);
            res.push_back(arr[right]);
            break;
        }
    }
    
    return res;
}
```


## Hashing Approach

```cpp
vector<int> twoSum(vector<int>& arr, int target) {
    vector<int> res;
    unordered_set<int> s;
    
    for (int i=0; i<arr.size(); i++) {
        if (s.find(target-arr[i]) != s.end()){
            res.push_back(target-arr[i]);
            res.push_back(arr[i]);
            break;
        }
        s.insert(arr[i])
    }
        
    return res;
}
```

<br><br>
<div style="padding-left:110px;">
<table>
<tr><th>Approach</th><th>Time Complexity</th><th>Space Complexity</th></tr>
<tr><td>Sorting</td><td align="center">O(nlogn)</td><td align="center">O(1)</td></tr>
<tr><td>Hashing</td><td align="center">O(n)</td><td align="center">O(n)</td></tr>
</table>
</div>
<div style="padding-left:190px;">
The Space - Time tradeoff
</div>
<br>

<h1>Rotate Array</h1>

Given an array, rotate the array to the right by `k` steps, where `k` is non-negative.

**Example 1:**<br>
Input: nums = [1,2,3,4,5,6,7], k = 3<br>
Output: [5,6,7,1,2,3,4]<br>
Explanation:<br>
rotate 1 steps to the right: [7,1,2,3,4,5,6]<br>
rotate 2 steps to the right: [6,7,1,2,3,4,5]<br>
rotate 3 steps to the right: [5,6,7,1,2,3,4]<br>

**Example 2:**<br>
Input: nums = [-1,-100,3,99], k = 2<br>
Output: [3,99,-1,-100]<br>
Explanation: <br>
rotate 1 steps to the right: [99,-1,-100,3]<br>
rotate 2 steps to the right: [3,99,-1,-100]<br>
 

**Constraints:**<br>
1 <= nums.length <= 105<br>
-231 <= nums[i] <= 231 - 1<br>
0 <= k <= 105<br>
 

**Follow up:**<br>
Try to come up with as many solutions as you can. There are at least three different ways to solve this problem.<br>
Could you do it in-place with O(1) extra space? <br><br>

Click [here](https://leetcode.com/problems/rotate-array/) for the problem link <br><br><br>

```cpp
void rotateRight(vector<int>& arr, int k) {
    // Your code ...
}
```
<br><br><br><br><br><br><br><br><br><br><br><br><br><br>

## Using a copy array
```cpp
void rotateRight(vector<int>& arr, int k) {
        int n = arr.size();
        k %= n;
        vector<int> temp = arr;
        
        for (int i=0; i<n; i++) {
            arr[i] = temp[(n+i-k)%n];
        }
}
```

Incase of left rotate, use arr[i] = temp[(i+k)%n]; <br><br><br><br>
## Using Reversal Algorithm
```cpp
void rotateRight(vector<int>& arr, int k) {
        k %= arr.size();
        reverse(arr.begin(), arr.end() - k); // reversing first n-k elements
        reverse(arr.end() - k, arr.end());   // reversing last k elements
        reverse(arr.begin(), arr.end());     // reversing all elements
}
```

<br>

### How it works ? 

Input: nums = [1,2,3,4,5,6,7], k = 3<br>
Output: [5,6,7,1,2,3,4]<br><br>
The conversion we need to make for right rotation :<br>
[0,1,2,......,n-k-1,n-k,......,n-1] to [n-k,n-k+1,...,n-1,0,1,....n-k-1] <br><br>
Let AB are the two parts of the input array where A = arr[0..n-k-1] and B = arr[n-k..n-1]. The idea of the algorithm is : <br>
- Reverse A to get ArB, where Ar is reverse of A. <br>
- Reverse B to get ArBr, where Br is reverse of B. <br>
- Reverse all to get (ArBr) r = BA. 

<br><br><br><br><br><br><br>
<h1>Plus One</h1>

You are given a **large integer** represented as an integer array digits, where each `digits[i]` is the `i`<sup>th</sup> digit of the integer. The digits are ordered from most significant to least significant in left-to-right order. The large integer does not contain any leading `0`'s.

Increment the large integer by one and return the resulting array of digits.

**Example 1:**<br>
Input: digits = [1,2,3]<br>
Output: [1,2,4]<br>
Explanation: The array represents the integer 123.<br>
Incrementing by one gives 123 + 1 = 124.<br>
Thus, the result should be [1,2,4].<br>

**Example 2:**<br>
Input: digits = [9]<br>
Output: [1,0]<br>
Explanation: The array represents the integer 9.<br>
Incrementing by one gives 9 + 1 = 10.<br>
Thus, the result should be [1,0].<br>
 

**Constraints:**<br>
1 <= digits.length <= 100<br>
0 <= digits[i] <= 9<br>
digits does not contain any leading 0's.<br><br>

Click [here](https://leetcode.com/problems/plus-one/) for the problem link <br><br><br>

```cpp
vector<int> plusOne(vector<int>& arr) {
    // Your code ...
}
```
<br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br>
```cpp
vector<int> plusOne(vector<int>& arr) {
        vector<int> res;
        int carry = 1;
       
        // perform addition from the least significant digit 
        // to the most significant digit
        for (int i=arr.size()-1; i>=0; i--) {
            int temp = carry + arr[i];
            res.push_back(temp%10);
            carry = temp/10;
        }
        
        if (carry) {
            res.push_back(carry);
        }
        
        reverse(res.begin(), res.end());
        return res;
}
```

<br><br><br><br>
**Logic Used**
- To do the operation 'Plus One', we are making use of the variable `carry` by initially setting it to 1
- If in any iteration the sum enters into `double digits`, we are setting carry (to 1 ofcourse) and passing it on to next iterations


<br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br>

<h1>Remove Duplicates from Sorted Array</h1>

Given an integer array `nums` sorted in **non-decreasing order**, remove the duplicates in-place such that each unique element appears only once. The **relative order** of the elements should be kept the same.

Since it is impossible to change the length of the array in some languages, you must instead have the result be placed in the first part of the array `nums`. More formally, if there are `k` elements after removing the duplicates, then the first `k` elements of `nums` should hold the final result. It does not matter what you leave beyond the first `k` elements.

Return k after placing the final result in the first `k` slots of `nums`.

Do not allocate extra space for another array. You must do this by modifying the input array in-place with O(1) extra memory.

**Example 1:** <br>
Input: nums = [1,1,2]<br>
Output: 2, nums = [1,2,_]<br>
Explanation: Your function should return k = 2, with the first two elements of nums being 1 and 2 respectively.
It does not matter what you leave beyond the returned k (hence they are underscores).

**Example 2:**<br>
Input: nums = [0,0,1,1,1,2,2,3,3,4]<br>
Output: 5, nums = [0,1,2,3,4,_ ,_ ,_ ,_ ,_]<br>
Explanation: Your function should return k = 5, with the first five elements of nums being 0, 1, 2, 3, and 4 respectively.
It does not matter what you leave beyond the returned k (hence they are underscores).
 

**Constraints:** <br>
1 <= nums.length <= 3 * 104<br>
-100 <= nums[i] <= 100<br>
nums is sorted in non-decreasing order.<br><br>

Click [here](https://leetcode.com/problems/remove-duplicates-from-sorted-array/) for the problem link <br><br><br>

```cpp
int removeDuplicates(vector<int>& arr) {
    // Your code ...
}
```
<br><br><br><br><br><br><br><br><br>

```cpp
int removeDuplicates(vector<int>& arr) {
        int lastSetIndex = 0;
        // the first element in the result array is same as in the initial array
        
        for (int i=1; i<arr.size(); i++) {
            if (arr[i] != arr[lastSetIndex]){
                // if current element is not equal to the last set element, 
                // make it as the last set element
                arr[++lastSetIndex] = arr[i];
            }
        }
        
        return lastSetIndex+1;
}
```
<br><br><br><br>

**Logic Used**
- We need to modify the array in-place and the size of the final array would potentially be smaller than the size of the input array. So, we ought to use a two-pointer approach here. One, that would keep track of the current element in the original array and another one for just the unique elements.
- Essentially, once an element is encountered, you simply need to bypass its duplicates and move on to the next unique element.

<br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br>
<h1>Move Zeroes to the End</h1>

Given an integer array `arr`, move all `0`'s to the end of it while maintaining the relative order of the non-zero elements. <br>
Note that you must do this in-place without making a copy of the array. <br>

**Example 1:** <br>
Input: arr = [0,1,0,3,12] <br>
Output: [1,3,12,0,0] <br>

**Example 2:** <br>
Input: arr = [0] <br>
Output: [0] <br>

**Constraints:** <br>
1 <= arr.length <= 104 <br>
-231 <= arr[i] <= 231 - 1 <br>
 
**Follow up:** <br>
Could you minimize the total number of operations done? <br><br>

Click [here](https://leetcode.com/problems/move-zeroes/) for the problem link <br><br><br>

```cpp
void moveZeroes(vector<int>& arr) {
    // Your code ...
}
```
<br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br>

```cpp
void moveZeroes(vector<int>& arr) {
        int setIndex = 0;
        
        // maintaining all non-zero elements in relative order
        for (int i=0; i<arr.size(); i++) {
            if (arr[i] != 0) {
                arr[setIndex++] = arr[i];
            }
        }
        
        // moving zeroes to the end
        for (int i=setIndex; i<arr.size(); i++) {
            arr[i] = 0;
        }
}
```

<br><br>
Let's try to decrease the number of traversals<br><br>

```cpp
void moveZeroes(vector<int>& arr) {
        int setIndex = 0, temp;
        
        for (int i=0; i<arr.size(); i++) {
            if (arr[i] != 0) {
                temp = arr[i];
                arr[i] = 0;
                arr[setIndex++] = temp;   
            }
        }
}
```
<br><br>
**Logic Used**
- A <b>two-pointer</b> approach could be helpful here. The idea would be to have one pointer for iterating the array and another pointer(setIndex) that just works on the non-zero elements of the array.
- In the second method, since `i` >= `setIndex`, we can set `i` and `setIndex` in the same iteration.

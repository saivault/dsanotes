<div style="font-weight:900; font-size: 27px;">
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
Stacks
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
Queues
</div>
<br><br>
<p>
    &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
    <a href="#stack-concept" style="text-decoration:none">Concept</a>
    &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
    &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
    <a href="#queue-concept" style="text-decoration:none">Concept</a><br>
    &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
    <a href="#parenthesis" style="text-decoration:none">Balanced Parantheses!</a><br>
    &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
    <a href="#exp-eval" style="text-decoration:none">Expression Evaluation</a><br>
    &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
    <a href="#nge" style="text-decoration:none">Next Greater Element</a><br>
    &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
    <a href="#minstack" style="text-decoration:none">Min Stack</a><br>
    &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
    <a href="#rainwater" style="text-decoration:none">Trapping rain water</a><br>
    &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
    <a href="#largerectangle" style="text-decoration:none">Largest rectangle in histogram</a>
</p>
<br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br>
<div align="center">0</div>
<h1 id="stack-concept">Stacks</h1>
Everyone is familiar with the famous <b>undo option</b>, which exists in almost all popular applications. But have you ever wondered how that works? Well, store the previous states of your work (which are limited to a specific number) in the memory in such an order that the last one appears first. You can’t efficiently do this with simple arrays for reasons explored in the coming chapters. This is where the “stack” data structure comes in handy.<br><br>
Stacks follow the <b>Last in First Out (LIFO) ordering</b>. This means that the last element added is the element on the top, and the first element added is at the bottom.<br><br>
A real-life example of stack could be a stack of books. To get the book that’s somewhere in the middle, you will remove all the books placed at the top of it. Also, the last book you added to the stack of books is at the top!
<div align="center">
    <img src="https://raw.githubusercontent.com/saivault/dsanotes/main/store/stack.png" width=400 height=250><br>
</div>
<h2>What are stacks used for?</h2>
Despite the simple implementation, stacks can be used to solve very complex problems. <br><br>
There are many famous algorithms such as <i>depth first search</i> and the <i>expression evaluation algorithm</i>, which harness the functionality of stacks.<br> Stacks are used: <br>
- To backtrack to the previous task/state. For example, it backtracks in recursive code. <br>
- To store a partially completed task; for example, you are exploring two different paths on a graph from a point while figuring out the smallest path to the target.

<br><br><br><br><br><br>
<div align="center">1</div>
<h2>Implementation</h2>
C style array stack works in C++ as well. However, C++ provides a library implementation of stack as well. <br><br>
<h3>Creating a stack</h3>

```cpp
#include<stack>                // must inclue this header file
stack<int> st;                 // declares an empty stack
```


<br> The functions associated with stack are: <br>
- **empty()** – Returns whether the stack is empty <br>
- **size()** – Returns the size of the stack <br>
- **top()** – Returns a reference to the top most element of the stack <br>
- **push(ele)** – Adds the element ‘ele’ at the top of the stack <br> 
- **pop()** – Deletes the top most element of the stack <br>

All the above operations are of time complexity O(1)
<br><br><br>
<h1>Reverse a string using stack</h1>

```cpp
string reverseString(string A) {
    stack<char> st;
    for (int i=0; i<A.size(); i++) st.push(A[i]);

    string result = "";
    while (!st.empty()) {
        char topChar = st.top();
        result += topChar;
        st.pop();
    }

    return result;
}
```

<br><br><br><br><br><br><br><br><br>
<div align="center">2</div>
<h1 id="parenthesis">Balanced Parantheses!</h1>
Given a string A consisting only of '(' and ')'. <br>
You need to find whether parantheses in A is balanced or not ,if it is balanced then return 1 else return 0. <br><br>

<b>Example 1:</b><br>
Input: "(()())"<br>
Output: 1<br>

<b>Example 2:</b><br>
Input: "(()"<br>
Output: 0<br><br>

<b>Follow up:</b><br>
What if we allow our string to contain all kinds of bracket characters like '(', ')', '{', '}', '[' and ']'. The brackets must close in the correct order, "()" and "()[]{}" are all valid but "(]" and "([)]" are not.
<br><br>

Click <a href="https://www.interviewbit.com/problems/balanced-parantheses/">here</a> for the problem link<br>
Click <a href="https://leetcode.com/problems/valid-parentheses/">here</a> for the follow up problem link<br>
<br><br><br>


```cpp
int solve(string A) {
    // Your code ...
}
```

<br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br>
<div align="center">3</div>
Let's consider a normal approach first


```cpp
int solve(string A) {
    int val = 0;

    for (int i=0; i<A.size(); i++) {
        if (A[i] == '(') {
            val++;
        } else {
            val--;
            if (val<0) return 0;
        }
    }

    if (val) return 0;
    return 1;
}
```

<br><br><br>
Aliter, Stack approach

```cpp
int solve(string A) {
     stack<char> st;

    for (int i=0; i<A.size(); i++) {
        if (A[i] == '(') {
            st.push(A[i]);
        } else {
            if (st.empty()) return 0;
            st.pop();
        }
    }

    if (!st.empty()) return 0;
    return 1;
```

<br><br><br>
<h3>Logic Used</h3>
- At any moment of traversal from left to right, the number of opening brackets encountered should be greater than or equal to the number of closing brackets encountered.<br>
- After traversing, the number of opening brackets encountered should be equal to the number of closing brackets encountered. (stack should be empty)

<br><br><br>
<div align="center">4</div>
Solution to the follow up:

```cpp
int solve(string A) {
     stack<char> st;

    for (int i=0; i<A.size(); i++) {
        if ((A[i] == '(') || (A[i] == '[') || (A[i]=='{')) {
            st.push(A[i]);
        } else {
            if (st.empty()) return 0;
            char top = st.top();
            if ((A[i] == ')') && (top != '(')) return 0;;
            if ((A[i] == '}') && (top != '{')) return 0;
            if ((A[i] == ']') && (top != '[')) return 0;
            st.pop();
        }
    }

    if (!st.empty()) return 0;
    return 1;
```

<br><br><h3>Logic Used</h3>
- Whenever we encounter one kind of closing bracket, the opening bracket of the same kind should be present at the top of the stack. <br>
- Whenever we find any substring as balanced, consider its disappearance and just worry about the remaining string.<br><br>

Time Complexity: O(n) <br>
Auxiliary Space: O(n) for stack. 

<br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br>
<div align="center">5</div>
<h1 id="exp-eval">Expression Evaluation</h1>
<h3>Reverse Polish notation (Postfix)</h3>
A mathematical notation in which operators follow their operands. <br><br>
For instance, to add 3 and 4 together, one would write 3 4 + rather than 3 + 4. If there are multiple operations, operators are given immediately after their final operands (often an operator takes two operands, in which case the operator is written after the second operand); so the expression written 3 − 4 + 5 in conventional notation would be written 3 4 − 5 + in postfix notation: 4 is first subtracted from 3, then 5 is added to it. <br><br>
Postfix notation has been found to lead to <b>faster calculations</b>, for two reasons. <br>
1. It do not need expressions to be parenthesized, so fewer operations need to be entered to perform typical calculations. 3 − (4 × 5) is written as 345*- <br>
2. It prevents us from doing multiple scans of the expression for its evaluation. <br>
Say we have to evaluate (a+(b*c))+d

The compiler first scans the expression to evaluate the expression `b * c`, then again scans the expression to add `a` to it. The result is then added to `d` after another scan. The repeated scanning makes it very in-efficient. It is better to convert the expression to postfix(or prefix) form before evaluation. The corresponding expression in postfix form is `abc*+d+`. <br>

The postfix expressions can be evaluated easily using a stack. <br><br>
<b>Example 1:</b><br>
Input: tokens = ["2","1","+","3","*"]<br>
Output: 9<br>
Explanation: ((2 + 1) * 3) = 9<br><br>
<b>Example 2:</b><br>
Input: tokens = ["4","13","5","/","+"]<br>
Output: 6<br>
Explanation: (4 + (13 / 5)) = 6<br><br>
<b>Example 3:</b><br>
Input: tokens = ["10","6","9","3","+","-11","*","/","*","17","+","5","+"]<br>
Output: 22<br>
Explanation: ((10 * (6 / ((9 + 3) * -11))) + 17) + 5<br><br>
Click <a href="https://leetcode.com/problems/evaluate-reverse-polish-notation/">here</a> for the problem link<br>

```cpp
int evalRPN(vector<string> &s) {
    // Your code ...
}
```
<b>Constraints:</b><br>
1 <= s.length <= 104<br>
s[i] is either an operator("+", "-", "*", "/") or an integer in the range [-200, 200].
<div align="center">6</div>

```cpp
int evalRPN(vector<string> &s) {
    stack<int> st;

    for (int i=0; i<s.size();; i++) {
        if ((s[i] == "+") || (s[i] == "-") || (s[i] == "*") || (s[i] == "/")) {
            int second = st.top();
            st.pop();
            int first = st.top();
            st.pop();
            if (s[i]=="+") st.push(first+second);
            if (s[i]=="-") st.push(first-second);
            if (s[i]=="*") st.push(first*second);
            if (s[i]=="/") st.push(first/second);
        } else {
            st.push(stoi(s[i]));
        }
    }

    return st.top();
}

```

<br><br><br>
<h3>Algorithm</h3>
- Traverse the string vector from left to right.<br>
- If the current element is an operand, store it in a stack.<br>
- Else (implying the current element is an operator) get the last two operands from the stack and perform the corresponding operation with them. Store the result obtained in the same stack. <br>
- Return top of the stack at the end.<br><br><br>

The time complexity of the evaluation algorithm is O(n) where n is the number of elements.

<br><br><br><br><br><br><br><br><br><br><br><br><br>
<div align="center">7</div>
<h1 id="nge">Next Greater Element</h1>
Given an integer array, find the next greater element for every array element.<br> The next greater element of a number x is the first greater number to the right of x in the array. Elements for which no greater element exist, consider the next greater element as -1<br><br>
In other words, for each element A[i] in the array A, find an element A[j] such that &nbsp; j > i and A[j] > A[i] and the value of j should be as minimum as possible. If the next greater element doesn’t exist in the array for any element, consider it -1.<br><br>
<b>Example 1:</b><br>
Input: [4, 5, 2, 25]<br>
Output: [5, 25, 25, -1]<br><br>
<b>Example 2:</b><br>
Input: [13, 7, 6, 12}]<br>
Output: [-1, 12, 12, -1]<br><br>
<b>Example 2:</b><br>
Input:  [5, 4, 3, 2, 1]<br>
Output: [-1, -1, -1, -1, -1]<br><br>
Click <a href="https://techiedelight.com/practice/?problem=NextGreaterElement">here</a> for the problem link<br><br>

```cpp
vector<int> findNextGreaterElements(vector<int> &A)
{
	// Your code ...
}
```

<br><br><br>
<b>Follow up:</b>
What if the given array is circular ? <br>
The end of the array wraps around to the start of the array. <br><br>
<b>Example 3:</b><br>
Input:  [3, 5, 2, 4]<br>
Output: [5, -1, 4, 5]<br><br>
Click <a href="https://leetcode.com/problems/next-greater-element-ii/">here</a> for the follow up problem link<br><br>

<br><br><br><br><br><br>
<div align="center">8</div>

```cpp
vector<int> findNextGreaterElements(vector<int> &A)
{
	vector<int> res(A.size());
	stack<int> st;

	for (int i=A.size()-1; i>=0; i--) {
		while (!st.empty() && st.top()<=A[i]) st.pop();
		res[i] = st.empty() ? -1 : st.top();
		st.push(A[i]);
	}
		
	return res;
}
```

<br><br><h3>Logic Used</h3>
- We are always using a sorted stack where the element present at the top is the smallest. <br>
- As at every moment we need to have knowledge of the elements present to the right of the current element, we are traversing from right to left<br><br><br>

Solution to the follow up problem :- <br>
Just by looping twice  <br>
```cpp
vector<int> findNextGreaterElements(vector<int> &A)
{
	vector<int> res(A.size());
    stack<int> st;

    for (int i=A.size()-1; i>=0; i--) {
        while (!st.empty() && st.top()<=A[i]) st.pop();
        st.push(A[i]);
    }

    for (int i=A.size()-1; i>=0; i--) {
        while (!st.empty() && st.top()<=A[i]) st.pop();
        res[i] = st.empty() ? -1 : st.top();
        st.push(A[i]);
    }
    return res;
}
```

<br><br>
<div align="center">9</div>
<h1 id="minstack">Min Stack</h1>

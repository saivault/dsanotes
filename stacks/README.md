<h1>Stacks</h1>

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



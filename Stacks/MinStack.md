```cpp
class MinStack {
2public:
3    std::stack<int> stack;
4    std::stack<int> minStack;
5
6    MinStack() {
7        
8    }
9    
10    void push(int value) {
11        stack.push(value);
12        if (minStack.empty()){
13            minStack.push(value);
14        }else if(value < minStack.top()){
15            minStack.push(value);
16        }
17        else{
18            minStack.push(minStack.top());
19        }
20    }
21    
22    void pop() {
23        stack.pop();
24        minStack.pop();
25       
26
27        
28    }
29    
30    int top() {
31        return stack.top();
32        
33    }
34    
35    int getMin() {
36        return minStack.top();
37        
38    }
39};
40
41/**
42 * Your MinStack object will be instantiated and called as such:
43 * MinStack* obj = new MinStack();
44 * obj->push(value);
45 * obj->pop();
46 * int param_3 = obj->top();
47 * int param_4 = obj->getMin();
48 */
```


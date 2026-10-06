```cpp
class Solution {
2public:
3    bool isValid(string s) {
4        stack<char> st;
5        
6        for(char c :s){
7            if (c == '(' || c == '[' || c =='{'){
8                st.push(c);
9            }
10            if (c == ')' || c== ']' || c =='}'){
11                if (st.empty()) {
12                    return false;
13                }
14
15                switch (c){
16                    case ')':
17                        if(st.top() == '('){
18                            st.pop();
19                            break;
20                        }else{
21                            return false;
22                        }
23                    case ']':
24                        if(st.top() == '['){
25                            st.pop();
26                            break;
27                        }else{
28                            return false;
29                        }
30                    case '}':
31                        if(st.top() == '{'){
32                            st.pop();
33                            break;
34                        }else{
35                            return false;
36                        }
37                default:
38                    return false;
39                }
40            }
41        }
42
43        return st.empty();
44    }
45};
```

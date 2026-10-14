```cpp
1class Solution {
2public:
3    int evalRPN(vector<string>& tokens) {
4        stack<string> stk;
5
6        for(auto c: tokens){
7            if(c != "+" && c!= "-" && c!= "*" && c!="/"){
8                stk.push(c);
9            }
10            else{
11                auto a = stoi(stk.top());
12                stk.pop();
13                auto b = stoi(stk.top());
14                stk.pop();
15
16                if(c == "+"){
17                    auto ans = a+b;
18                    stk.push(to_string(ans));
19                
20                }
21                else if(c == "-"){
22                   auto ans = b-a;
23                   stk.push(to_string(ans));
24                }
25                else if ( c == "*"){
26                    auto ans = a*b;
27                    stk.push(to_string(ans));
28
29                }
30                else{
31                    auto ans = b/a;
32                    stk.push(to_string(ans));
33
34                }
35                
36            }
37        }
38
39        return stoi(stk.top());
40
41
42        
43    }
44};
```

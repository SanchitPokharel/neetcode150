```cpp
1class Solution {
2public:
3    vector<int> dailyTemperatures(vector<int>& temperatures) {
4        stack<pair<int,int>> stck;
5        vector<int> res(temperatures.size(),0);
6
7        for(int i =0; i < temperatures.size(); i++){
8            while(!stck.empty() && temperatures[i] > stck.top().first){
9                auto [prevTemp, prevIdx] = stck.top();
10                stck.pop();
11                res[prevIdx] = i - prevIdx;
12            }
13            
14            
15            // 73,74,75,71,69,72,76,73
16            // 0 , 1, 2, 3, 4, 5, 6, 7
17            stck.push({temperatures[i], i});
18
19        }
20
21
22        return res;
23        
24    }
25    
26};
```


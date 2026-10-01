```cpp
1class Solution {
2public:
3    vector<vector<string>> groupAnagrams(vector<string>& strs) {
4        
5        unordered_map<string, vector<string>> mp;
6        auto sortedStrs = strs;
7
8        for(auto& x: sortedStrs)
9        sort(x.begin(), x.end());
10
11        for(int i = 0; i < sortedStrs.size(); i++){
12            mp[sortedStrs[i]].push_back(strs[i]);
13        }
14
15        vector<vector<string>> result;
16        for (const auto& pair : mp) {
17            result.push_back(pair.second);
18        }
19
20        return result;
21
22
23        
24
25        
26    }
27};
```

Solution: Sort the strings in the array then use those sorted strings as hash key use vector of strings with the original str in the array then create a new vector with our current vectors in the vector map. 

Time: O(n · k log k), space: O(nk).

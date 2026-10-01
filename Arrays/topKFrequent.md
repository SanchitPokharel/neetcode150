```cpp
1class Solution {
2public:
3    vector<int> topKFrequent(vector<int>& nums, int k) {
4        vector<pair<int,int>> answers;
5        vector<int> output;
6        if(k == nums.size()){
7            return nums;
8        }
9        map<int,int> mp;
10        sort(nums.begin(), nums.end());
11
12        for(int i = 0; i < nums.size(); i++){
13            mp[nums[i]]++;
14        }
15
16        for(auto& pair: mp){
17            answers.push_back({pair.second,pair.first});
18
19        }
20
21        sort(answers.begin(),answers.end());
22
23        for(int i = 0; i < k; i++){
24            output.push_back(answers.back().second);
25            answers.pop_back();
26        }
27
28        return output;
29    }
30    
31};
```
Solution: Not Optimal, What was done? Wizardry. 
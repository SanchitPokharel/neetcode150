```cpp
1class Solution {
2public:
3    vector<int> twoSum(vector<int>& nums, int target) {
4        unordered_map<int, int> mp;
5
6        for(int i = 0; i < nums.size();  i++){
7            int compliment = target - nums[i];
8            if(mp.count(compliment)){
9                return {mp[compliment], i};
10            }
11
12            mp[nums[i]] = i;
13        }
14       
15       return {};
16    }
17};
```

Solution: Search for the compliment in the map at the same time we are adding the index into the map. 
Time Complexity: (O(n)), Space Complexity O(n), n = nums
```cpp
1class Solution {
2public:
3    int longestConsecutive(vector<int>& nums) {
4        if (nums.empty()) return 0;
5        
6        //vector<int> lcs;
7        int lcscount=1;
8        int maxlcscount=1;
9
10        sort(nums.begin(), nums.end());
11
12        for(int i = 0; i < nums.size()-1; i++){
13            if(nums[i] == nums[i+1]){
14                continue;
15            }
16            if(nums[i] == nums[i+1]-1){
17                lcscount++;
18                if (lcscount > maxlcscount){
19                    maxlcscount = lcscount;
20                }
21            }else{
22                lcscount = 1;
23            }
24        }
25
26        return maxlcscount;
27
28        
29    }
30};
```


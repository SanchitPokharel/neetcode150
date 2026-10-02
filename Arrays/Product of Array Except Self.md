```cpp
1class Solution {
2public:
3    vector<int> productExceptSelf(vector<int>& nums) {
4        vector<int> output(nums.size(), 1);
5        int left = 1;
6        int right = 1;
7
8        for(int i = 0; i < nums.size(); i++){
9            output[i] = output[i] * left;
10            left = left * nums[i];
11        }
12
13        for(int j =nums.size()-1; j>=0; j--){
14            output[j] = output[j] * right;
15            right = right * nums[j];
16        }
17
18        return output;
19
20         
21    }
22};
```

Weird Solution, Need to review more
```cpp
1class Solution {
2public:
3    int maxArea(vector<int>& height) {
4    int ans = 0;
5    int left = 0;
6    int right = height.size() - 1;
7
8    while (left < right) {
9        int cur = min(height[left], height[right]) * (right - left);
10
11        ans = max(ans, cur);
12
13        if (height[left] < height[right]) {
14            left++;
15        } else {
16            right--;
17        }
18    }
19
20    return ans;
21    }
22
23};
```

lowkey easy 

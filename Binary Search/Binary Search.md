```cpp
1class Solution {
2public:
3    int binarySearch(vector<int>& nums, int target, int left, int right){
4        if(left > right){
5            return -1;
6        }
7
8        int mid = left + (right - left)/2;
9
10        if(nums[mid] == target){
11            return mid;
12        }
13
14        if(nums[mid] < target){
15            return binarySearch(nums, target, mid+1, right);
16        }else{
17            return binarySearch(nums, target, left, mid-1);
18        }
19
20    }
21    int search(vector<int>& nums, int target) {
22        return binarySearch(nums, target, 0, nums.size()-1);
23        
24        
25    }
26};
```

```cpp
class Solution {
2public:
3    vector<int> twoSum(vector<int>& numbers, int target) {
4        int left = 0;
5        int right = numbers.size()-1;
6
7        while(left < right){
8            int sum = numbers[left] + numbers[right];
9
10            if(sum == target){
11                return  {left+1, right+1};
12            }
13
14            else if (sum < target){
15                left++;
16            }
17            else{
18                right --;
19            }
20        }
21        
22
23        return {};
24    }
25};
```

Tried to make solution more complicated than what it really should be. 

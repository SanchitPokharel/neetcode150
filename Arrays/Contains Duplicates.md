```cpp
class Solution {
public:
    bool containsDuplicate(vector<int>& nums) {
        sort(nums.begin(), nums.end());
        for(int i = 0; i < nums.size()-1; i++){
            if(nums[i] == nums[i+1]){
                return true;
            }
        }
        return false;

        
    }
};
```

Solution: Sort first then keep iterating over vector and comparing sorted elements, if duplicate found then return true immediately, if vector is exhausted then return false. 

Time Complexity: O(n), Space Complexity: O(n)

```cpp
class Solution {
public:
    bool containsDuplicate(vector<int>& nums) {
        unordered_set<int> s;
        for(int i = 0; i < nums.size(); i++){
            if(!s.count(nums[i])){
                s.insert(nums[i]);
            }else{
                return true;
            }
        }

        return false;
    }
};
```

Solution: Use an unordered set, Iterate vector and keep adding to set, if already exists in set then return true immideately, if vector is exhausted and no duplicates in set, return false. 

Time Complexity: O(n), Space Complexity O(n)
```cpp
1class Solution {
2public:
3    int findDuplicate(vector<int>& nums) {
4        int slow = nums[0];
5        int fast = nums[0];
6
7        do{
8            slow = nums[slow];
9            fast = nums[nums[fast]];
10        } while(slow != fast);
11
12        // nums[1] = 3 
13        // nums[nums[1]] = nums[3] = 2
14        // 1, 3, 4, 2, 2, s= 3, 2
15
16        // nums[3] = 2
17        // nums[nums[2]] = nums[4] = 2
18        // s = 2, f = 2,
19
20        slow = nums[0];
21        
22        while (slow != fast) {
23            slow = nums[slow];
24            fast = nums[fast];
25        }
26        
27        return slow;
28        
29    }
30};
```

Notes: ### Floyd's Algorithm — Key Lemma

Let (a) = distance from start to cycle entrance, (b) = distance from entrance to first meeting, and (L) = cycle length.

At the first meeting, fast travels twice as far as slow:

[  
2(a+b)-(a+b)=kL  
]

Therefore,

[  
a+b=kL \implies a=kL-b  
]

**Conclusion:** The distance from the start to the cycle entrance equals a whole number of cycle lengths minus the distance from the entrance to the meeting point.

Thus, resetting one pointer to the start and moving both pointers one step at a time makes them meet at the cycle entrance.
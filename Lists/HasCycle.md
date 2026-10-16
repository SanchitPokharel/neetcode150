My solution 
```cpp
1/**
2 * Definition for singly-linked list.
3 * struct ListNode {
4 *     int val;
5 *     ListNode *next;
6 *     ListNode(int x) : val(x), next(NULL) {}
7 * };
8 */
9class Solution {
10public:
11    bool hasCycle(ListNode *head) {
12
13        set<ListNode*> st;
14        ListNode* dummy = head;
15        while(dummy != nullptr){
16            if(st.count(dummy) != 0){
17                return true;
18            }
19          
20            st.insert(dummy);
21            dummy = dummy->next;
22        }
23
24        return false;
25        
26    }
27};
```



Optimal Solution: Use two pointers, one is fast pointer, one is slow pointer.
![[Screenshot 2026-10-14 at 6.25.55 PM.png]]

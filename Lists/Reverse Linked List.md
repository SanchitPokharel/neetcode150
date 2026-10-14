```cpp
1/**
2 * Definition for singly-linked list.
3 * struct ListNode {
4 *     int val;
5 *     ListNode *next;
6 *     ListNode() : val(0), next(nullptr) {}
7 *     ListNode(int x) : val(x), next(nullptr) {}
8 *     ListNode(int x, ListNode *next) : val(x), next(next) {}
9 * };
10 */
11class Solution {
12public:
13    ListNode* reverseList(ListNode* head) {
14        ListNode* prev = nullptr;
15        ListNode* current = head;
16        ListNode* next;
17
18        while(current != nullptr){
19            next = current->next;
20            current->next = prev;
21            prev = current;
22            current = next;
23        }
24
25        return prev;
26        
27    }
28};
```

View less


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
13    ListNode* mergeTwoLists(ListNode* list1, ListNode* list2) {
14        ListNode dummy(0);
15        ListNode* tail = &dummy;
16
17        while(list1 != nullptr && list2 != nullptr){
18            if(list1->val > list2->val){
19                tail->next = list2;
20                list2=list2->next;
21
22            }else{
23                tail->next = list1;
24                list1=list1->next;
25            }
26            tail = tail->next;
27        }
28
29        if(list1 != nullptr){
30            tail->next = list1;
31        }else{
32            tail->next=list2;
33        }
34
35
36        return dummy.next;
37    }
38       
39};
```

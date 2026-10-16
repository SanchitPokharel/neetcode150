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
13    ListNode* removeNthFromEnd(ListNode* head, int n) {
14        ListNode* dummyNode = head;
15        int listSize = 0;
16        while(dummyNode != nullptr){
17            listSize++;
18            dummyNode = dummyNode->next;
19        }
20
21        if(listSize == 1){
22            return nullptr;
23        }
24
25        if(listSize == n){
26            return head->next;
27        }
28
29        int nodePosition = listSize - n;
30        int nodeToChange = nodePosition-1;
31
32        dummyNode = head;
33        int counter = 0;
34        while(dummyNode != nullptr){
35            if(counter == nodeToChange){
36                dummyNode->next = dummyNode->next->next;
37            }
38            counter++;
39            dummyNode = dummyNode->next;
40        }
41
42        return head;
43        
44    }
45};
```
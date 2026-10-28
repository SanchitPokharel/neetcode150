```cpp
1/*
2// Definition for a Node.
3class Node {
4public:
5    int val;
6    Node* next;
7    Node* random;
8    
9    Node(int _val) {
10        val = _val;
11        next = NULL;
12        random = NULL;
13    }
14};
15*/
16
17class Solution {
18public:
19    Node* copyRandomList(Node* head) {
20        Node dummy(0);
21        Node* tail = &dummy;
22        unordered_map<Node*,Node*> mp;
23        Node* ptr = head;
24
25        while(ptr != nullptr){
26            Node* newNode = new Node(ptr->val);
27            mp[ptr] = newNode;
28            ptr = ptr->next;
29        }
30
31        ptr = head;
32
33        while(ptr != nullptr){
34            tail->next = mp[ptr];
35            tail->next->random = (ptr->random == nullptr)
36            ? nullptr
37            : mp[ptr->random];            
38             ptr=ptr->next;
39             tail = tail->next;
40        }
41
42
43        return dummy.next;
44        
45    }
46};
```


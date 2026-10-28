```cpp
1class Solution {
2public:
3    int lengthOfLongestSubstring(string s) {
4        set<char> st;
5        int maxLen = 0;
6        int left = 0;
7
8        for(int right = 0; right < s.size(); right++ ){
9            while(st.count(s[right])){
10                st.erase(s[left]);
11                left++;
12            }
13
14            st.insert(s[right]);
15
16            int currentLength = right -left + 1;
17            maxLen = max(currentLength, maxLen);
18        }
19
20        return maxLen;
21    }
22};
```


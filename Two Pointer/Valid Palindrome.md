```cpp
1class Solution {
2public:
3    bool isPalindrome(string s) {
4
5        s.erase(remove_if(s.begin(), s.end(), [](unsigned char c) {
6        return !isalnum(c);
7    }), s.end());
8
9    for (char& c : s) {
10        c = std::tolower(static_cast<unsigned char>(c));
11    }
12
13    int left = 0;
14    int right = static_cast<int>(s.length()) - 1;
15
16    while(left<right){
17        if(s[left] != s[right]){
18            return false;
19        }
20        left++;
21        right--;
22    }
23
24    return true;
25
26    }
27};
```

Solution: Not Optimal 

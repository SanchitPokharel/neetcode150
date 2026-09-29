
Solution: Use a frequency array, each char is a unique symbol, increment and decrement the array while iterating through the string 

Time Complexity: O(n), space O(s+t)

```cpp
1class Solution {
2public:
3    bool isAnagram(string s, string t) {
4        if(s.size() != t.size()){
5            return false;
6        }
7        int freqArr[26] = {0};
8        
9        for(int i = 0; i < s.size(); i++){
10            freqArr[s[i]-'a']++;
11        }
12
13        for(int j = 0; j < t.size(); j++){
14            freqArr[t[j]-'a']--;
15
16            if(freqArr[t[j]-'a'] < 0){
17                return false;
18            }
19        }
20
21        return true;
22        
23    }
24};
```

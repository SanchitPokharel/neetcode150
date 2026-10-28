```cpp
1class Solution {
2public:
3    int maxProfit(vector<int>& prices) {
4        int maxProfit = 0;
5        int buy = 0;
6        int sell = 1;
7
8        for(int i =0; i < prices.size()-1; i++){
9            if(prices[buy] > prices[sell]){
10                buy = sell;
11            }
12            
13            int currentProfit = prices[sell] - prices[buy];
14            if(currentProfit > maxProfit){
15                maxProfit = currentProfit;
16            }
17            sell++;
18
19        }
20
21        return maxProfit;
22        
23    }
24};
```


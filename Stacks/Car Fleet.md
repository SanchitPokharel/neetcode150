```cpp
1class Solution {
2public:
3    int carFleet(int target, vector<int>& position, vector<int>& speed) {
4        
5        if (position.size() == 1){
6            return 1;
7        }
8
9        vector<pair<int,double>> sortedP;
10        stack<pair<int,int>> stk;
11        int numberOfFleets = 0;
12
13        for(int i = 0; i < position.size(); i++){
14            double arrivalTime = (double(target) - double(position[i]))/double(speed[i]);
15            sortedP.push_back({position[i], arrivalTime});
16        }
17        
18        sort(sortedP.rbegin(), sortedP.rend());
19
20        double prevArrivalTime=0;
21
22        for(int i = 0; i < sortedP.size(); i++){
23            if(sortedP[i].second > prevArrivalTime){
24                numberOfFleets++;
25                prevArrivalTime = sortedP[i].second;
26            }
27
28        }
29
30        return numberOfFleets;
31        
32        
33    }
34};
```

Supposed to use a stack but did not. 

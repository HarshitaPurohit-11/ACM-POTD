POTD DAY3
Best Time to Buy and Sell Stock

Algorith
1. Initialize:
   minPrice=INT_MAX
   maxProfit=0

2. Traverse the array:
   Update minPrice if current price is lower
   Else calculate profit =price-minPrice
   Update maxProfit if profit is higher

3. Return maxProfit

Code
class Solution {
public:
    int maxProfit(vector<int>& prices){
        int minPrice=INT_MAX;
        int maxProfit=0;

        for(int price:prices){
            if(price<minPrice){
                minPrice=price;
            } else{
                int profit=price-minPrice;
                maxProfit=max(maxProfit, profit);
            }
        }

        return maxProfit;
        
    }
};



Screenshot


<img width="1366" height="768" alt="Screenshot (708)" src="https://github.com/user-attachments/assets/bc73cbd9-dd52-49fb-9508-8c70389a94f1" />

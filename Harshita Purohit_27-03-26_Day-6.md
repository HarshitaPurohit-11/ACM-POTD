POTD DAY 6

Question:
Check if N and Its Double Exist

Algorithm:
Initialize an empty hash set
Traverse through each element x in the array:
  If 2 * x exists in the set → return true
  If x is even and x / 2 exists → return true
Insert the current element into the set
If no such pair is found → return false

Time Complexity: o(n)
Space Complexity: o(n)

Solution:
class Solution {
public:
    bool checkIfExist(vector<int>& arr) {
        unordered_set<int> s;

        for (int x:arr){
            if (s.count(2*x)||(x%2==0 && s.count(x/2))){
                return true;
            }
            s.insert(x);
        }
        return false;
        
    }
};

Screenshot


<img width="1366" height="768" alt="Screenshot (729)" src="https://github.com/user-attachments/assets/403d891f-6cf1-43e0-b6bb-ed45cf1892fb" />

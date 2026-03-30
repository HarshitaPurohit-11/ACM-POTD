POTD DAY 9
Date: 30-03-2026

Question:
Linked List Cycle

Algorithm:
1. Initialize two pointers
      slow=head
      fast=head
2. Traverse the list
      While fast != NULL and fast->next != NULL:
          Move slow by 1 step -> slow = slow->next
          Move fast by 2 steps -> fast = fast->next->next
3. Check for cycle
     If at any point slow==fast:
          Cycle exists -> return true
     If loop ends
          fast reached NULL
          No cycle -> return false

Solution:
class Solution {
public:
    bool hasCycle(ListNode *head) {
        if (head==NULL||head->next==NULL)
            return false;

        ListNode *slow=head;
        ListNode *fast=head;

        while (fast!=NULL&&fast->next != NULL) {
            slow=slow->next;           
            fast=fast->next->next;  

            if (slow==fast)         
                return true;
        }

        return false;
        
    }
};

Time complexity: o(n)
Space complexity: o(1)

Screenshot:
<img width="1366" height="768" alt="Screenshot (751)" src="https://github.com/user-attachments/assets/b3ee8dcc-869a-47b3-bfca-e7ecaff6a258" />

POTD DAY 11
Date: 01-04-2026

Problem:
Merge Two Sorted Lists

Algorithm:
1. Create a dummy node
    Initialize a new node dummy
    This helps avoid edge-case handling
    Set a pointer temp = dummy
2. Traverse both lists
    While both list1 and list2 are not NULL:
        Compare values:
           If list1->val <= list2->val
                Attach list1 to temp->next
                Move list1 forward
           Else:
                Attach list2 to temp->next
                 Move list2 forward
        Move temp forward
3. Attach remaining elements
    If list1 is not NULL → attach it
    Else → attach list2
4. Return result
    Return dummy->next (actual head)


Solution:

class Solution {
public:
    ListNode* mergeTwoLists(ListNode* list1, ListNode* list2) {
        
        ListNode*dummy=new ListNode(-1);
        ListNode*temp=dummy;

        
        while (list1!=NULL && list2!=NULL) {
            if (list1->val <= list2->val) {
                temp->next=list1;
                list1=list1->next;
            } else {
                temp->next=list2;
                list2=list2->next;
            }
            temp=temp->next;
        }

        
        if (list1!=NULL) {
            temp->next=list1;
        } else {
            temp->next=list2;
        }

        return dummy->next;
        
    }
};

Time Complexity: O(n+m)
Space Complexity: O(1)



Screenshot:


<img width="1366" height="768" alt="Screenshot (797)" src="https://github.com/user-attachments/assets/b2cb361a-8fe9-4177-9551-7eff7db9c26a" />

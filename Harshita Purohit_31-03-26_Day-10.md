POTD DAY 10
Date: 31-03-2026

Problem:
Middle of the Linked List

Algorithm:
Initialize pointers
    Set slow = head
    Set fast = head
Traverse the list
    While fast != NULL and fast->next != NULL:
        Move slow by 1 step → slow = slow->next
        Move fast by 2 steps → fast = fast->next->next
Stop condition
    Loop ends when:
        fast reaches end (NULL), or
        fast->next is NULL
Return result
    slow will be pointing to the middle node
    In case of even length → it automatically gives the second middle node

Time Complexity: O(n)
Space Complexity: O(1)

Solution:

class Solution {
public:
    ListNode* middleNode(ListNode* head) {
        ListNode* slow=head;
        ListNode* fast=head;

        while (fast!=nullptr && fast->next != nullptr) {
            slow=slow->next;
            fast=fast->next->next;
        }

        return slow;  
    }
};

Screenshot:

<img width="1366" height="768" alt="Screenshot (778)" src="https://github.com/user-attachments/assets/7fceaad6-cd94-4abe-a27e-260639c15559" />

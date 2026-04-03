POTD DAY 13
Date: 03-04-2026

Question:
Intersection of Two Linked Lists

Solution:
class Solution {
public:
    ListNode *getIntersectionNode(ListNode *headA, ListNode *headB) {
        if(headA == NULL || headB == NULL) return NULL;

        ListNode*a=headA;
        ListNode*b=headB;

        while(a!=b) {
            a=(a==NULL)?headB:a->next;
            b=(b==NULL)?headA:b->next;
        }

        return a;
        
    }
};

Algorithm:
1. Initialize two pointers
      ptrA = headA
      ptrB = headB
2. Traverse both lists
      While ptrA != ptrB:
            If ptrA == NULL, move it to headB, else ptrA = ptrA->next
            If ptrB == NULL, move it to headA, else ptrB = ptrB->next
3. Stop condition
     When ptrA == ptrB, exit loop
4. Return result
     If intersection exists → both pointers meet at that node
     If not → both become NULL, return NULL

Time Complexity: O(m + n)
Space Complexity: O(1)

Screenshot:

<img width="1366" height="768" alt="Screenshot (801)" src="https://github.com/user-attachments/assets/81f93c14-6457-4d54-b841-3a01cf43c511" />

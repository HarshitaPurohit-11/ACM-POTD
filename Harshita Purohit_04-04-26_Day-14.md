POTD DAY 14
Date: 04-04-2026

Question:
Palindrome Linked List

Algorithm:

1. Handle base cases
    If the list is empty or has only one node, return true.
2. Find the middle of the list
   Initialize two pointers: slow (1 step) and fast (2 steps).
   Move them until fast reaches the end:

while fast != null and fast.next != null:
    slow = slow.next
    fast = fast.next.next
  slow now points to the middle node.
3. Reverse the second half of the list

   Starting from slow, reverse the list in-place:

prev = null
curr = slow
while curr != null:
    nextNode = curr.next
    curr.next = prev
    prev = curr
    curr = nextNode
prev points to the head of the reversed second half.
4. Compare the two halves
Initialize firstHalf = head and secondHalf = prev.

Compare corresponding nodes:

while secondHalf != null:
    if firstHalf.val != secondHalf.val:
        return false
    firstHalf = firstHalf.next
    secondHalf = secondHalf.next
If all nodes match, the list is a palindrome.
5. Restore the original list
Reverse the second half again to restore the original structure.
6. Return the result
Return true if all comparisons passed.

Solution:
class Solution {
public:
     ListNode* reverseList(ListNode* head) {
        ListNode* prev= nullptr;
        ListNode* curr=head;
        while (curr){
            ListNode*nextNode=curr->next;
            curr->next=prev;
            prev=curr;
            curr=nextNode;
        }
        return prev;
    }
    
    bool isPalindrome(ListNode* head) {
        if (!head||!head->next) return true;

        
        ListNode* slow = head;
        ListNode* fast = head;
        while (fast->next && fast->next->next) {
            slow = slow->next;
            fast = fast->next->next;
        }

        ListNode* secondHalf = reverseList(slow->next);

        ListNode* firstHalf = head;
        ListNode* tempSecond = secondHalf;
        bool palindrome = true;
        while (tempSecond) {
            if (firstHalf->val != tempSecond->val) {
                palindrome = false;
                break;
            }
            firstHalf = firstHalf->next;
            tempSecond = tempSecond->next;
        }

        slow->next = reverseList(secondHalf);

        return palindrome;
        
    }
};

Complexity:

Time: O(n)
Space: O(1)

Screenshot:

<img width="1366" height="768" alt="Screenshot (823)" src="https://github.com/user-attachments/assets/bc48ee7e-1052-43dd-be17-dae11606c072" />

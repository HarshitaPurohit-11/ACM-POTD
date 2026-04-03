POTD Day-12
Date: 02-04-2026

Question:
Remove Duplicates from Sorted List

Algorithm:
1. Start
2. Check if list is empty
        If head == NULL, return head
3. Initialize pointer
        Set current = head
4. Traverse the list
        While current != NULL and current->next != NULL:
                Compare current->val with current->next->val
5. If duplicate found
        If current->val == current->next->val:
                Delete/skip the next node
                Set current->next = current->next->next
6. If not duplicate
        Move forward
        Set current = current->next
7. Repeat until end of list
8. Return head
9. End

Time Complexity: O(n)
Space Complexity: O(1)

Screenshot:

<img width="1366" height="768" alt="Screenshot (800)" src="https://github.com/user-attachments/assets/7db94e49-159a-47cc-96ab-d2567aef783e" />

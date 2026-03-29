POTD DAY8
Date: 29-03-2026

Problem:
Reverse Linked List

Algorithm:
Initialize three pointers:
  prev = NULL
  curr = head
Iterate through the list:
  Save next node → nextNode = curr->next
  Reverse link → curr->next = prev
  Move prev forward → prev = curr
  Move curr forward → curr = nextNode
Return prev as the new head

Solution:
class Solution {
public:
    ListNode* reverseList(ListNode* head){
        ListNode* prev = nullptr;
        ListNode* curr = head;

        while (curr!=nullptr){
            ListNode* nextNode=curr->next; 
            curr->next=prev;              
            prev=curr;                   
            curr=nextNode;             
        }

        return prev;        
    }
};

Screenshot:<img width="1366" height="768" alt="Screenshot (732)" src="https://github.com/user-attachments/assets/8c6507d8-a91d-46c5-b1fa-450c370ce2e2" />

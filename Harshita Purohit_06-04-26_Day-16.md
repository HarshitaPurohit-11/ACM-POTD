POTD DAY 16
Date: 06-04-2026

Question:
Implement Queue using Stacks

Algorithm:
Use two stacks: s1 (push stack) and s2 (pop stack)

Push(x)
Push element into s1

Pop()
If s2 is empty, move all elements from s1 → s2
Pop and return top of s2

Peek()
If s2 is empty, move all elements from s1 → s2
Return top of s2

Empty()
Return true if both s1 and s2 are empty, else false

Complexity:
Push → O(1)
Pop/Peek → Amortized O(1)
Empty → O(1)

Solution:
class MyQueue {
private:
    stack<int> s1, s2;

public:
    MyQueue(){
        
    }
    
    void push(int x){
        s1.push(x);
    }
    
    int pop(){
        if (s2.empty()) {
            while (!s1.empty()) {
                s2.push(s1.top());
                s1.pop();
            }
        }
        int val=s2.top();
        s2.pop();
        return val;
    }
    
    int peek() {
        if (s2.empty()) {
            while (!s1.empty()) {
                s2.push(s1.top());
                s1.pop();
            }
        }
        return s2.top();
    }
    
    bool empty(){
        return s1.empty() && s2.empty();
    }
};

Screenshot:
<img width="1366" height="768" alt="Screenshot (904)" src="https://github.com/user-attachments/assets/b928c46c-6e8b-4e2c-bd7a-89cb34eb6bab" />

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

Screenshots:

<img width="1366" height="768" alt="Screenshot (911)" src="https://github.com/user-attachments/assets/b64bded0-de67-48c3-ad7c-a012efb9cfeb" />
<img width="1366" height="768" alt="Screenshot (910)" src="https://github.com/user-attachments/assets/e60c08ff-65fd-4be5-998e-95ee867f99a6" />
<img width="1366" height="768" alt="Screenshot (909)" src="https://github.com/user-attachments/assets/e0e7b02a-3f09-4389-818b-e1f8523ac4e1" />


POTD DAY 17
Date: 07-04-2026

Question:
Implement Stack using Queues

Algorithm:
Used two queues: q1 (main) and q2 (helper)

Push(x)
Push x into q2
Move all elements from q1 → q2
Swap q1 and q2

Pop()
Remove and return front of q1

Top()
Return front of q1

Empty()
Return true if q1 is empty, else false

Complexity:
Push → O(n)
Pop → O(1)
Top → O(1)
Empty → O(1)

Solution:
class MyStack{
private:
    queue<int> q1, q2;

public:
    MyStack() {
        
    }
    
    void push(int x){
        q2.push(x);
        
        while (!q1.empty()) {
            q2.push(q1.front());
            q1.pop();
        }
        
        swap(q1, q2);
    }
    
    int pop(){
        int val=q1.front();
        q1.pop();
        return val;
    }
    
    int top(){
        return q1.front();
    }
    
    bool empty(){
        return q1.empty();
    }
};

Screenshots:

<img width="1366" height="768" alt="Screenshot (906)" src="https://github.com/user-attachments/assets/f450f9c5-9043-4ef2-bdc4-e99459c53279" />
<img width="1366" height="768" alt="Screenshot (908)" src="https://github.com/user-attachments/assets/e0fdab7d-f7e2-4941-b69a-e8c9528bf658" />
<img width="1366" height="768" alt="Screenshot (907)" src="https://github.com/user-attachments/assets/374d76bd-7d39-4ed9-92fe-2f229cf1147b" />


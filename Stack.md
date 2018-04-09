
#Stack

~~~
#include <iostream>

using namespace std;


class node{
public:
	int data;
	node* prevnode;

	node();
	~node();
};
node::node(){
	data = NULL;
	prevnode = NULL;
}
node::~node(){
	cout << "node is deleted\n";
}
class Stack{
public:
	int length;
	node* top;
public:
	Stack();
	void push(int newdata);
	void pop();
	int getSize();
	bool IsEmpty();
	int getTop();
	
};

Stack::Stack(){
	top = NULL;
	length = 0;
}

bool Stack::IsEmpty(){
	if (top == NULL)
	{
		return true;
	}
	else
		return false;
}
void Stack::push(int newdata)
{
	node*newnode = new node();
	newnode->data = newdata;
	if (top == NULL)
	{
		top = newnode;
		length++;
	}
	else if (top != NULL){
		newnode->prevnode = top;
		top = newnode;
		length++;
	}
}
void Stack::pop(){
	if (IsEmpty()){
		cout << "\nis empty!\n";
		return;
	}
	node* temp = top->prevnode;
	delete top;
	top = temp;
	length--;
}
int Stack::getSize(){
	return length;
}
int Stack::getTop(){
	if (IsEmpty())
	{
		cout << "is empty!";
		return 404;
	}
	else
		return top->data;
}
void main()
{
	int select;
	Stack stc;
	while (true)
	{
		cout << "\n1. push   2. pop  3. 현재top  4.stack_SIZE\n";

		cin >> select;

		switch (select)
		{
		case 1:
			int data;
			cout << "데이터 입력:";
			cin >> data;
			stc.push(data);
			break;
		case 2:
			stc.pop();
			break;
		case 3:
			cout<<"\n"<<stc.getTop()<<"\n";
			break;
		case 4:
			cout<<"\n"<<stc.getSize()<<"\n";
			break;
		}
	}
}
~~~

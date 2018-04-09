#Used CPP

#include <iostream>
using namespace std;

class node{
public:
	int data;
	node* nextnode;
public:
	node();
	~node();
};
node::node(){
	data = NULL;
	nextnode = NULL;
}
node::~node(){
	cout << "node is deleted!\n";
}
class queue{
public:
	node* bottom;
	int length;
public:
	queue();
	void push(int newdata);
	void pop();
	int getLength();
	bool isEmpty();
	void bottom_check();
};

queue::queue(){
	this->bottom = NULL;
	this->length = 0;
}
void queue::push(int newdata){
	node* newnode = new node;
	newnode->data= newdata;
	if (bottom == NULL)
	{
		bottom = newnode;

		
	}
	else
	{
		node* temp = bottom;
		while (temp->nextnode != NULL)
		{
			temp = temp->nextnode;
		}
		temp->nextnode = newnode;
	}
	this->length++;
}
bool queue::isEmpty(){
	if (bottom == NULL){
		return true;
	}
	else if (bottom != NULL){
		return false;
	}
}
void queue::bottom_check(){
	if (isEmpty())
	{
		cout << "is empty!\n";
		//return;
	}
	else if (!isEmpty()){
		cout << bottom->data<<"\n";
		//return;
	}
}
void queue::pop(){
	
	//bottom_check();
	
	if (length == 0)
	{
		cout << "isempty!\n";
		return;
	}
	else if (length != 0)
	{
		node* temp = bottom->nextnode;
		cout << bottom->data << "\n";
		delete bottom;
		bottom = temp;
		length--;
	}
}
int queue::getLength(){
	return this->length;
}
int main()
{
	int select;
	int data;
	queue queue;

	while (1)
	{
		cout << "\n1. push 2.pop 3.getLength 4.bottom_check\n";
		cin >> select;
		switch (select)
		{
		case 1:
			cout << "Input Data:";
			cin >> data;
			queue.push(data);
			break;
		case 2:
			queue.pop();
			break;
		case 3:
			cout << queue.getLength()<<"\n";
			break;
		case 4:
			queue.bottom_check();
			break;
		default:
			break;
		}
	}
}

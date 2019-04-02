# SelectionSort
# Language: CPP

~~~
#include <iostream>
#include <cstdlib>
#include <ctime>
#define MAX 10
using namespace std;



void Selection_Sort(int arr[])
{
	int temp;
	int min;
	for (int i = 0; i < MAX; i++)
	{
		min = i;
		for (int j = i + 1; j < MAX; j++)
		{
			if (arr[min]>arr[j])
			{
				min = j;
			}
		}
		temp = arr[i];
		arr[i] = arr[min];
		arr[min] = temp;
	}
}

void main()
{
	int arr[MAX];
	srand((unsigned)time(NULL));
	for (int i = 0; i < MAX; i++)
	{
		arr[i] = rand() % 100+1;
	}
	Selection_Sort(arr);

	for (int i = 0; i < MAX; i++)
	{
		printf("%d  ", arr[i]);
	}
}
~~~






~~~cpp

#include <iostream>
#include <vector>
#include <cstdlib>

using namespace std;
int main()
{
	int data = 0;
	int index = 0;
	int min, tmp = 0;
	vector<int> v;
	for (int i = 0; i < 10; i++)
	{
		data = rand() % 100 + 1;
		v.push_back(data);
		cout << v.at(i)<<"\t";
	}
	cout << "\n";
	cout << "\n";
	for (int i = 0; i < v.size()-1; i++)
	{
		min = v.at(i);
		index = i;
		for (int j = i+1; j < v.size(); j++)
		{
			if (min > v.at(j)) {
				min = v.at(j);
				index = j;
			}
		}
		if (i != index) {
			tmp = v.at(i);
			v.at(i) = v.at(index);
			v.at(index) = tmp;
		}
		cout << i << " round \n";
		for (int i = 0; i < v.size(); i++)
		{
			cout << v.at(i) << "\t";
		}
		cout << "\n\n";
	}


~~~

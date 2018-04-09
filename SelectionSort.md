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

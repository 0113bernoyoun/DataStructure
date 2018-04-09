# InsertionSort
## Langauge:CPP

~~~
#include <iostream>
#include <cstdlib>
#include <ctime>

#define MAX 10

using namespace std;

void Insertion_Sort(int arr[])
{
	int temp;
	int j;
	for (int i = 1; i < MAX; i++)
	{
		temp = arr[i];
		for ( j = i - 1; j >= 0; j--)
		{
			if (arr[j]>temp)
			{
				arr[j + 1] = arr[j];
			}
			else
				break;
		}
		arr[j + 1] = temp;	
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
	Insertion_Sort(arr);

	for (int i = 0; i < MAX; i++)
	{
		printf("%d  ", arr[i]);
	}
}
~~~

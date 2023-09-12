---
title: BCS - Karachi 01
date: 2023-09-11
tags:
  - pf
  - assignment
  - karachi
---
## Task 1 (a):
Create an algorithm and then write pseudocode for the following problems:
**a)** To find Greatest Common Divisor (GCD) of two given numbers.

```cpp
/* 
1. Start
2. Input Num1 and Num2
3. declare count = 1
4. declare gcd;
5. while (count != (Num1 && Num2))
	1. if(Num1%count == 0 && Num2%count == 0){
		1. gcd = count
	2. }
	3. count++;
6. Output gcd
7. END
*/

int main(){
	int num1, num2, gcd, count;
	cin >> num1;
	cin >> num2;
	
	while(count <= num1 & count <= num2){
		if(num1%count==0 && num2%count==0){
			gcd = count;
		};
	};
	
	cout << gcd;
	return 0;
}
```

![](notes/1.General/PF%20Fast/Assignments/attachments/BCS%20-%20Karachi%2001%202023-09-11%2021.32.10.excalidraw.svg)
%%[🖋 Edit in Excalidraw](notes/1.General/PF%20Fast/Assignments/attachments/BCS%20-%20Karachi%2001%202023-09-11%2021.32.10.excalidraw.md), and the [dark exported image](notes/1.General/PF%20Fast/Assignments/attachments/BCS%20-%20Karachi%2001%202023-09-11%2021.32.10.excalidraw.dark.svg)%%

**b)** To take 3 numbers A, B and C as input and find if the sum of numbers A and B is greater than the
number C.

```cpp
/*
1. Start
2. Input A, B, C
3. sum = A + B
4. if (sum > C)
	1. Output "C is bigger than sum of A and B"
5. else
	1. Output "C is smaller or equal to the sum of A and B"

NI LIKHUNGA ISKA CODEEEEE
*/
```

![](notes/1.General/PF%20Fast/Assignments/attachments/BCS%20-%20Karachi%2001%202023-09-11%2021.52.53.excalidraw.svg)
%%[🖋 Edit in Excalidraw](notes/1.General/PF%20Fast/Assignments/attachments/BCS%20-%20Karachi%2001%202023-09-11%2021.52.53.excalidraw.md), and the [dark exported image](notes/1.General/PF%20Fast/Assignments/attachments/BCS%20-%20Karachi%2001%202023-09-11%2021.52.53.excalidraw.dark.svg)%%

**c)** To find the smallest number in a given list of 10 numbers.
```cpp
#include <vector>
#include <string>
/* 
1. Start
2. declare min = 10000000
3. declare list
4. for (i, list){
	1. if (list[i] < min)
		1. min = list[i]
5. }
6. OUTPUT min

*/

int main(){
	int min = 1000000;
	vector <int> list = {
		5,2,5,7,3,8,36,74,23
	};
	for (int i=0; i< list.size(); i++){
		if (list[i] < min){
			min = list[i];
		};
	};
	
	cout << min << endl;
	
	return 0;
}

```

**d)** Given a list of 5 numbers, rearrange them in descending order.

```cpp
#include <vector>
#include <string>
using namespace std;

/*
1. Start
2. declare list
3. for (i=0, list.size()){
	1. set max = MAX(i, list.size())
	2. swap( list[max], list[i] )
4. }
5. END

*/

int main(){
	int max;
	vector <int> list = {
		5,2,5,7,3,8,36,74,23
	};
	for (int i=0; i < list.size(); i++){
		// Takes the ith value as the maximum
		max = i;
			// Makes the loop continue from ith pos, to find the largest 
		for (int x = i; x < list.size(); x++){
			// Checks if larger
			if (list[x] > list[max]){
				max = x;
			};	
		};
		int t = list[i];
		list[i] = list[max];
		list[max] = t;
	};
	
	for(int i=0; i < list.size(); i++){
		cout << list[i] << endl;
	};
	
	return 0;
}
```


**e)** To find the number of even integers in a given list of numbers.

```cpp
/* 
1. Start
2. Set even = 0;
3. declare list
4. for (i=0; i<list.size(); i++){
	1. if(list[i] % 2 == 0){ even++}
5. }
6. OUTPUT even
7. END
KYN BNAUN ME CPP ME CODE ? FREE ME ? 
*/
```


---
title: "Pattern Problems in C++"
description: "Some pattern practing C++"
tags:
- patterns
- cpp
- fundamentals
---

### Decrementing Block of size (n)
f(3) = 321
		  321
		  321

f(2) = 21
		  21

```cpp
int main(){
	int n = 3;
	//cin >> n;
	int j = 1;
	while (j <= n){
		int i = n;
		while (i > 0){
			cout << i;
			i = i - 1;
		};
		cout<<endl;
		j = j + 1;
	}
	return 0;
}
```

### Block of size n of incrementing numbers

```cpp
int main(){
	int n = 3;
	int i = 1;
	int inc = 1;
	while (i <= n){
		int j = 1;
		while (j<=n){
			cout<<inc<<" ";
			inc = inc + 1;
			j = j + 1;
		}
	i = i + 1;
	cout << endl;
	};
	return 0;
}
```

### Triangle Pattern

For star
```cpp
int main(){
	int n = 10;
	int i = 1;
	while (i <= n){
		int count = 1;
		while (count <= i){    // Print * i number of times
			cout << "*";
			count++;
		};
		cout<< endl;
		i++;
	};
	return 0;
}
```

For num of rows
```cpp
int main(){
	int n = 10;
	int i = 1;
	while (i <= n){
		int count = 1;
		while (count <= i){    // Print * i number of times
			cout << i;
			count++;
		};
		cout<< endl;
		i++;
	};
	return 0;
}
```

For this 
![](notes/1.General/CPP%20DSA/attachments/Pasted%20image%2020230821232837.png)

```cpp
int main(){
	int n = 4;
	int r = 1;
	while (r <= 4){
		int c = 1;
		int num = r;
		while(c <= r){
			cout << num;
			num++;
			c++;
		};
		r++;
		cout << endl;
	}
	return 0;
}
```

- [ ] Do this without `int num = r` #task 


### Blocked Letters Itteration
![](notes/1.General/CPP%20DSA/attachments/Patterns%202023-08-21%2023.43.39.excalidraw.svg)
%%[🖋 Edit in Excalidraw](notes/1.General/CPP%20DSA/attachments/Patterns%202023-08-21%2023.43.39.excalidraw.md), and the [dark exported image](notes/1.General/CPP%20DSA/attachments/Patterns%202023-08-21%2023.43.39.excalidraw.dark.svg)%%

```cpp
int main(){
	int n = 3;
	char chr = 65;
	int r = 1;
	while (r <= 3){
		int c = 1;
		while(c <= 3){
			cout << chr << " ";
			c++;
		};
		chr++;
		cout << endl;
		r++;
	};
	return 0;
}
```

![](notes/1.General/CPP%20DSA/attachments/Patterns%202023-08-21%2023.51.43.excalidraw.svg)
%%[🖋 Edit in Excalidraw](notes/1.General/CPP%20DSA/attachments/Patterns%202023-08-21%2023.51.43.excalidraw.md), and the [dark exported image](notes/1.General/CPP%20DSA/attachments/Patterns%202023-08-21%2023.51.43.excalidraw.dark.svg)%%

```cpp
int main(){
	int n = 3;
	int r = 1;
	while (r <= n){
		char ch = 65;
		int c = 1;
		while(c <= n){
			cout << ch << " ";
			c++;
			ch++;
		};
		r++;
		cout << endl;
	};
	return 0;
}
```


![](notes/1.General/CPP%20DSA/attachments/Patterns%202023-08-21%2023.55.42.excalidraw.svg)
%%[🖋 Edit in Excalidraw](notes/1.General/CPP%20DSA/attachments/Patterns%202023-08-21%2023.55.42.excalidraw.md), and the [dark exported image](notes/1.General/CPP%20DSA/attachments/Patterns%202023-08-21%2023.55.42.excalidraw.dark.svg)%%
```cpp
int main(){
	int n = 3;
	int r = 1;
	char ch = 65;
	while(r <= n){
		int c = 1;
		while (c <= n){
			cout << ch << " ";
			c++;
			ch++;
		};
		cout << endl;
		r++;
	};
	return 0;
}
```



![](notes/1.General/CPP%20DSA/attachments/Patterns%202023-08-21%2023.59.08.excalidraw.svg)
%%[🖋 Edit in Excalidraw](notes/1.General/CPP%20DSA/attachments/Patterns%202023-08-21%2023.59.08.excalidraw.md), and the [dark exported image](notes/1.General/CPP%20DSA/attachments/Patterns%202023-08-21%2023.59.08.excalidraw.dark.svg)%%

```cpp
int main(){
	int n = 3;
	int r = 1;
	char ch = 65;
	while (r <= n){
		int c = 1;
		while (c <= n){
			char chr = ch+c-1;
			cout << chr << " ";
			c++;
		};
		cout << endl;
		ch++;
		r++;
	};
	return 0;
}
```
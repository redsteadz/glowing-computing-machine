---
title: "Snail"
---


# Snail
Given an `n x n` array, return the array elements arranged from outermost elements to the middle element, traveling clockwise.

```
array = [[1,2,3],
         [4,5,6],
         [7,8,9]]
snail(array) #=> [1,2,3,6,9,8,7,4,5]
```

For better understanding, please follow the numbers of the next array consecutively:

```
array = [[1,2,3],
         [8,9,4],
         [7,6,5]]
snail(array) #=> [1,2,3,4,5,6,7,8,9]
```

This image will illustrate things more clearly:

![](http://www.haan.lu/files/2513/8347/2456/snail.png)

NOTE: The idea is not sort the elements from the lowest value to the highest; the idea is to traverse the 2-d array in a clockwise snailshell pattern.

NOTE 2: The 0x0 (empty matrix) is represented as en empty array inside an array `[[]]`.
![](notes/Codedojo/4%20kyu/attachments/Snail%202023-01-09%2001.44.43.excalidraw.svg)
%%[🖋 Edit in Excalidraw](notes/Codedojo/4%20kyu/attachments/Snail%202023-01-09%2001.44.43.excalidraw.md), and the [dark exported image](notes/Codedojo/4%20kyu/attachments/Snail%202023-01-09%2001.44.43.excalidraw.dark.svg)%%
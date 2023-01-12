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

## My solution
```run-javascript
snail = function(array) {
    // enjoy
    let arr = array
    let snail = []
    while (arr[0] != null && arr.length !== 0){ // Continue till the array is empty
    let cr = []; let cl = []; // Reset the coloumn right and left (cr, cl)

      for (i=1; i<arr.length-1; i++){
              cr.push(arr[i].pop())     // Takes the right most value of column
              cl.unshift(arr[i].shift())// Takes the left most value of column
            }
  
    snail.push(arr.shift()) // Inputs Top

    snail.push(cr) // Inputs Right

    if(arr[0] != null){         //
          let last_r = arr.pop()// Inputs Bottom Value
          last_r.reverse()      //
          snail.push(last_r)}   //
    
      snail.push(cl)// Inputs Left

      arr.length == 1 ? snail.push(arr.shift()) : null // Inputs Center Value
      cr = []
      cl= [] 
    }
  return snail.flat()
}

console.log(snail([[1, 2, 3, 4, 5], [6, 7, 8, 9, 10], [11, 12, 13, 14, 15], [16, 17, 18, 19, 20], [21, 22, 23, 24, 25]]))
```


![](notes/Codedojo/4%20kyu/attachments/Snail%202023-01-13%2000.53.26.excalidraw.svg)
%%[🖋 Edit in Excalidraw](notes/Codedojo/4%20kyu/attachments/Snail%202023-01-13%2000.53.26.excalidraw.md), and the [dark exported image](notes/Codedojo/4%20kyu/attachments/Snail%202023-01-13%2000.53.26.excalidraw.dark.svg)%%
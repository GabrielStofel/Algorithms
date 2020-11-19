# Algorithms
This repo was created with the sole purpose of storing various types of Algorithms with easy to understand explanations. If you wish to contribute to this project, feel free to do so! I'm just gonna ask you to follow two simple guidelines which are written below:

> If you're thinking about helping out with this project, please, make sure that your additions are very well and simply explained. Also, all the code must be written in JavaScript. That's it!

Alright, here we go!
## Sorting Algorithms:
### Bubble Sort
This algorithm is one of the easiest to learn, it works like this:

An inner loop runs through the whole Array comparing adjacent elements and swapping them if the current element is bigger than the next one. Also, we have an outer loop that makes sure that if the smallest element is in the position ```array.length - 1```, we can get it to the first place by repeating the inner loop ```array.length``` times.

```javascript
const  array = [4, 5, 2, 1, 8];

// Outer Loop
for (let  i = 0; i < array.length; i++) {
  // Inner Loop
  for (let  j = 0; j < array.length - 1; j++) {
    if (array[j] > array[j + 1]) {
      let  temp = array[j];
			
	array[j] = array[j + 1];
	array[j + 1] = temp;
    }
  }
}

console.log(array);  // Output: [ 1, 2, 4, 5, 8 ]
```

### Selection Sort
This algorithm's time complexity is the worst in this list, but it's still interesting to see how it sorts the elements in an array.

This algorithm kind of "expands" a sorted array inside the original until the entire array is sorted. Notice below how the inner loop runs through the whole array searching for the index of the smallest number and then, after getting to the end, exiting the loop, swapps places with the element in the ```i``` position. After that, the outer loop increments ```i``` and the inner loop searches again for the next smallest number.

```javascript
const  array = [9, 1, 3, 5, 7];

// Outer Loop
for (let i = 0; i < arr.length; i++) {
  let smallest = i;
	
  // Inner Loop (j receives i)
  for (let j = i; j < arr.length; j++) {
    if (arr[j] < arr[smallest]) {
      menor = j;
    }
  }

  const aux = arr[i];
  arr[i] = arr[smallest];
  arr[smallest] = aux;
}

console.log(array);  // Output: [ 1, 3, 5, 7, 9 ]
```

# Algorithms
This repo was created with the sole purpose of storing various types of Algorithms with easy to understand explanations. If you wish to contribute to this project, feel free to do so! I'm just gonna ask you to follow two simple guidelines which are written below:

> If you're thinking about helping out with this project, please, make sure that your additions are very well and simply explained. Also, all the code must be written in JavaScript. That's it!

Now, feel free to pick which type of algorithm you wish to learn first!

* [Sorting Algorithms](#sorting-algorithms) <br/>
* [Searching Algorithms](#searching-algorithms)

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

This algorithm kind of "expands" a sorted section inside the array until the entire array is sorted. Notice below how the inner loop runs through the whole array searching for the index of the smallest number and then, after getting to the end, exiting the loop, swapps places with the element in the ```i``` position. After that, the outer loop increments ```i``` and the inner loop searches again for the next smallest number.

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

### Insertion Sort
This algorithm is very similar to the Selection Sort in the sense that you're again expanding a sorted section.

```javascript
const array = [5, 1, 3, 4, 2];

let key, j;
// Outer loop
for (let i = 1; i < array.length; i++) {
  key = array[i];
  j = i - 1;
	
  // Inner loop
  while (j >= 0 && array[j] > key) {
    array[j + 1] = array[j];
    j = j - 1;
  }

  array[j + 1] = key;
}

console.log(array); // Output: [1, 2, 3, 4, 5]
```

## Searching Algorithms:
### Binary Search
This algorithm - which in this example involves recursion - is very quick and simple, however, it only works if the Array is organized! It has a time complexity of *O(log n)*.

It simply calculates the middle of the array based on the `start` and `end` indexes and checks if the middle number is greater or smaller than the number which we are looking for. If the middle number is smaller than `n`, we know for a fact that if `n` exists it can only be to the right of the middle number, reducing the "search area" by half and so on until the number is found or until `start` is greather than `end`, if that happens the function will return `false`.

```javascript
function binarySearch(array, start, end, n) {
  const middle = Math.floor((start + end) / 2);

  if (start <= end) {
    if (array[middle] > n) {
      return binarySearch(array, 0, middle - 1, n);
    } else if (array[middle] < n) {
      return binarySearch(array, middle + 1, end, n);
    } else {
      return true;
    }
  }

  return false;
}

const arr = [1, 2, 3, 4, 5];

if (binarySearch(arr, 0, arr.length - 1, 1)) {
  console.log("Number found!");
} else {
  console.log("Number NOT found!");
}
```
> Output: Number found!

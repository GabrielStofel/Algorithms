# Algorithms
This repo was created with the sole purpose of storing various types of Algorithms with easy to understand explanations. If you wish to contribute to this project, feel free to do so! I'm just gonna ask you to follow two simple guidelines which are written below:

> If you're thinking about helping out with this project, please, make sure that your additions are very well and simply explained. Also, all the code must be written in JavaScript. That's it!

Alright, here we go!
## Sorting Algorithms:
### Bubble Sort
This algorithm is one of the easiest to learn, it works like this:

An inner loop runs through the whole Array comparing neighbor elements and swapping them if the smaller one is ahead of the bigger. An outer loop 

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

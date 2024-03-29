
﻿# QuickSort Visualization in React

This Component lets you visualize the quick sort algorithm into your React App.

## Demo & Examples
Live demo: https://itsgk93.github.io/QuickSortAlgoVisualization/

## To build the examples locally, run:

```
npm install
npm start
```
Then open localhost:8080 in a browser.


## The algorithm written behind this visualization is 

```
async function quickSort(arr, start, end) {
if (start >= end) {
return;
}
let index = await partition(arr, start, end);
states[index] = -1;
await Promise.all([
quickSort(arr, start, index - 1),
quickSort(arr, index + 1, end)
]);
}
async function partition(arr, start, end) {
for (let i = start; i < end; i++) {
states[i] = 1;
}
let pivotValue = arr[end];
let pivotIndex = start;
states[pivotIndex] = 0;
for (let i = start; i < end; i++) {
if (arr[i] < pivotValue) {
await swap(arr, i, pivotIndex);
states[pivotIndex] = -1;
pivotIndex++;
states[pivotIndex] = 0;
}
}
await swap(arr, pivotIndex, end);
for (let i = start; i < end; i++) {
if (i !== pivotIndex) {
states[i] = -1;
}
}
return pivotIndex;
}
```

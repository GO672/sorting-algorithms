Sorting Algorithms Overview
This project demonstrates four different sorting algorithms: Bubble Sort, Selection Sort, Insertion Sort, and JavaScript's built-in .sort() function. Each algorithm is implemented to sort an array of values provided through dropdowns and display the sorted result.

Algorithms Implemented
1. Bubble Sort
Bubble Sort is a simple comparison-based algorithm that repeatedly steps through the list, compares adjacent elements, and swaps them if they are in the wrong order. This process is repeated until the list is sorted.

const bubbleSort = (array) => {
  for (let i = 0; i < array.length; i++) {
    for (let j = 0; j < array.length - 1; j++) {
      if (array[j] > array[j + 1]) {
        const temp = array[j];
        array[j] = array[j + 1];
        array[j + 1] = temp;
      }
    }
  }
  return array;
}

2. Selection Sort
Selection Sort works by repeatedly finding the minimum element from the unsorted part of the array and swapping it with the first unsorted element. This process continues until the whole array is sorted.

const selectionSort = (array) => {
  for (let i = 0; i < array.length; i++) {
    let minIndex = i;
    for (let j = i + 1; j < array.length; j++) {
      if (array[j] < array[minIndex]) {
        minIndex = j;
      }
    }
    const temp = array[i];
    array[i] = array[minIndex];
    array[minIndex] = temp;
  }
  return array;
}

3. Insertion Sort
Insertion Sort is a simple sorting algorithm that builds the sorted array one item at a time. It works by taking the current value and inserting it into the correct position within the sorted portion of the array.


const insertionSort = (array) => {
  for (let i = 1; i < array.length; i++) {
    const currValue = array[i];
    let j = i - 1;
    while (j >= 0 && array[j] > currValue) {
      array[j + 1] = array[j];
      j--;
    }
    array[j + 1] = currValue;
  }
  return array;
}


 4. JavaScript .sort() Method
JavaScript's built-in .sort() method is highly optimized and uses the Timsort algorithm, a hybrid sorting algorithm derived from Merge Sort and Insertion Sort. It performs well on both small and large datasets, making it the most efficient sorting option among those implemented in this project.

const sortInputArray = (event) => {
  event.preventDefault();
  const inputValues = [...document.getElementsByClassName("values-dropdown")].map((dropdown) => Number(dropdown.value));
  const sortedValues = inputValues.sort((a, b) => a - b);
  updateUI(sortedValues);
}

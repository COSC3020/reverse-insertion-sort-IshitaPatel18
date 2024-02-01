[![Review Assignment Due Date](https://classroom.github.com/assets/deadline-readme-button-24ddc0f5d75046c5622901739e7c5dd533143b0c8e959d652212380cedb1ea36.svg)](https://classroom.github.com/a/Bi-S25fM)
# Reverse Insertion Sort

Consider the code for insertion sort we covered in class:

```javascript
function insertionSort(arr) {
  for(var i = 1; i < arr.length; i++) {
    var val = arr[i];
    var j;
    for(j = i; j > 0 && arr[j-1] > val; j--) {
      arr[j] = arr[j-1];
    }
    arr[j] = val;
  }
  return arr;
}
```

Change this function such that it works from the end of the array rather than
the beginning, `insertionSortReverse()` -- only the direction of
iterating over the elements is reversed, the array is still sorted the same way
(ascending). Add your code in `code.js`. Test your new function; I've provided
some basic testing code that uses [jsverify](https://jsverify.github.io/) in
`code.test.js`.

## Average-Case Time Complexity of Insertion Sort

In the lectures, we covered that insertion sort has best-case time complexity of
$\Theta(n)$ and worst-case time complexity of $\Theta(n^2)$. What is the
average-case time complexity ($\Theta$)?

Hint: Think about what happens in each iteration of the loop, and how often the
loop is executed. Keep in mind that for asymptotic analysis we don't care about
constant factors.

Describe your reasoning and the conclusion you've come to. Your reasoning is
most important -- you can easily find the answer, but you need to demonstrate
that you've understood the concept. Add your answer to this markdown file.


​My answer: 
​
From what I have gathered after reading the Insertion Sort section of the textbook, Introduction to Algorithms, this is my best understanding of the average time complexity of Insertion Sort. In the subarray of sorted elements, the current element to be sorted, A[i], on average can be placed roughly in the middle, as half of the sorted subarray is less than A[i] and the other half is greater than A[i]. Now ti (t subscript i) is equal to i/2, which is the time to run the second for loop. Since constants aren't important enough to change the asymptotic conditions, the ½ can be dropped to leave ti = i, which is the same as the worst case time complexity. If ti = i/2 is used in the summation and the equations used to prove the run time complexities, the summation would only change to equal n(n-1)/4, which again uses the same idea that constants are not as impactful, so $\Theta(n^2)$ is the average time complexity for insertion sort.

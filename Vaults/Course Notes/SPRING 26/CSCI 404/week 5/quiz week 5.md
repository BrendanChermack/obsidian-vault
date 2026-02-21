## quiz 1


|                |     |             |
| -------------- | --- | ----------- |
| **Question 1** |     | 1 / 1 point |

How does QuickSort's divide-and-conquer strategy differ from MergeSort's?

|   |   |
|---|---|
|![Selected](https://stcloudstate.learn.minnstate.edu/d2l/img/0/QuestionCollection.Main.radioChecked.svg?v=20.26.1.24929 "Selected")|QuickSort does work during the divide step (partitioning) and nothing in combine; MergeSort does nothing in divide and work in combine|
|![Unselected](https://stcloudstate.learn.minnstate.edu/d2l/img/0/QuestionCollection.Main.radioUnchecked.svg?v=20.26.1.24929 "Unselected")|QuickSort combines subarrays after sorting; MergeSort doesn't need to combine|
|![Unselected](https://stcloudstate.learn.minnstate.edu/d2l/img/0/QuestionCollection.Main.radioUnchecked.svg?v=20.26.1.24929 "Unselected")|Both algorithms do equal work in divide and combine steps|
|![Unselected](https://stcloudstate.learn.minnstate.edu/d2l/img/0/QuestionCollection.Main.radioUnchecked.svg?v=20.26.1.24929 "Unselected")|QuickSort doesn't use recursion; MergeSort does|

|   |   |
|---|---|
|Hide question 1 feedback|   |
|||
|## Feedback<br><br>QuickSort's key insight: partition does all the work (Θ(n)), placing pivot in final position. Combine is free because subarrays are already in correct order!<br><br>Correct! QuickSort partitions (hard work) then recursively sorts. MergeSort just splits in half, then merges (hard work).|   |

|   |   |   |
|---|---|---|
|**Question 2**||1 / 1 point|

In the basic (non-randomized) PARTITION algorithm, which element is chosen as the pivot?

|   |   |
|---|---|
|![Selected](https://stcloudstate.learn.minnstate.edu/d2l/img/0/QuestionCollection.Main.radioChecked.svg?v=20.26.1.24929 "Selected")|The last element of the subarray: A[r]|
|![Unselected](https://stcloudstate.learn.minnstate.edu/d2l/img/0/QuestionCollection.Main.radioUnchecked.svg?v=20.26.1.24929 "Unselected")|The first element of the subarray: A[p]|
|![Unselected](https://stcloudstate.learn.minnstate.edu/d2l/img/0/QuestionCollection.Main.radioUnchecked.svg?v=20.26.1.24929 "Unselected")|The middle element of the subarray|
|![Unselected](https://stcloudstate.learn.minnstate.edu/d2l/img/0/QuestionCollection.Main.radioUnchecked.svg?v=20.26.1.24929 "Unselected")|A random element from the subarray|

|   |   |
|---|---|
|Hide question 2 feedback|   |
|||
|## Feedback<br><br>PARTITION(A, p, r) sets x = A[r], making the last element the pivot. This simplicity causes problems with sorted input, which randomization fixes.<br><br>Correct! The basic version always chooses A[r] as the pivot for simplicity.|   |

|   |   |   |
|---|---|---|
|**Question 3**||1 / 1 point|

After PARTITION(A, p, r) completes and returns index q, which statement is TRUE?

|   |   |
|---|---|
|![Selected](https://stcloudstate.learn.minnstate.edu/d2l/img/0/QuestionCollection.Main.radioChecked.svg?v=20.26.1.24929 "Selected")|All elements in A[p..q-1] are ≤ A[q], and all elements in A[q+1..r] are ≥ A[q]|
|![Unselected](https://stcloudstate.learn.minnstate.edu/d2l/img/0/QuestionCollection.Main.radioUnchecked.svg?v=20.26.1.24929 "Unselected")|All elements in A[p..q-1] are < A[q], and all elements in A[q+1..r] are > A[q]|
|![Unselected](https://stcloudstate.learn.minnstate.edu/d2l/img/0/QuestionCollection.Main.radioUnchecked.svg?v=20.26.1.24929 "Unselected")|The entire array A[p..r] is sorted|
|![Unselected](https://stcloudstate.learn.minnstate.edu/d2l/img/0/QuestionCollection.Main.radioUnchecked.svg?v=20.26.1.24929 "Unselected")|All elements in A[p..q] are ≤ all elements in A[q..r]|

|   |   |
|---|---|
|Hide question 3 feedback|   |
|||
|## Feedback<br><br>After PARTITION: A[p..q-1] ≤ pivot ≤ A[q+1..r]. The pivot is in its FINAL sorted position and won't move again!<br><br>Correct! The pivot A[q] is in its final sorted position with smaller elements left, larger elements right.|   |

|   |   |   |
|---|---|---|
|**Question 4**||1 / 1 point|

True or False: After PARTITION returns q, the pivot element A[q] is included in both recursive calls to QUICKSORT.

|   |   |   |
|---|---|---|
||![Unselected](https://stcloudstate.learn.minnstate.edu/d2l/img/0/QuestionCollection.Main.radioUnchecked.svg?v=20.26.1.24929 "Unselected")|True|
||![Selected](https://stcloudstate.learn.minnstate.edu/d2l/img/0/QuestionCollection.Main.radioChecked.svg?v=20.26.1.24929 "Selected")|False|

|   |   |
|---|---|
|Hide question 4 feedback|   |
|||
|## Feedback<br><br>The pivot at position q is excluded from both recursive calls because it's already in its final sorted position. We only recursively sort the two sides.<br><br>Correct! QUICKSORT calls itself on A[p..q-1] and A[q+1..r], excluding the pivot at q. The pivot is already correctly placed!|   |

|   |   |   |
|---|---|---|
|**Question 5**||1 / 1 point|

What is the running time of PARTITION(A, p, r) on a subarray of size n = r - p + 1?

|   |   |
|---|---|
|![Selected](https://stcloudstate.learn.minnstate.edu/d2l/img/0/QuestionCollection.Main.radioChecked.svg?v=20.26.1.24929 "Selected")|Θ(n)|
|![Unselected](https://stcloudstate.learn.minnstate.edu/d2l/img/0/QuestionCollection.Main.radioUnchecked.svg?v=20.26.1.24929 "Unselected")|Θ(log n)|
|![Unselected](https://stcloudstate.learn.minnstate.edu/d2l/img/0/QuestionCollection.Main.radioUnchecked.svg?v=20.26.1.24929 "Unselected")|Θ(n²)|
|![Unselected](https://stcloudstate.learn.minnstate.edu/d2l/img/0/QuestionCollection.Main.radioUnchecked.svg?v=20.26.1.24929 "Unselected")|Θ(1)|

|   |   |
|---|---|
|Hide question 5 feedback|   |
|||
|## Feedback<br><br>PARTITION has one for loop from j=p to r-1 (that's n-1 iterations), doing O(1) work per iteration. Total: Θ(n).<br><br>Correct! PARTITION examines each element exactly once in the for loop, doing constant work per element.|   |

|   |   |   |
|---|---|---|
|**Question 6**||2 / 2 points|

At the start of each iteration of the for loop in PARTITION (before examining A[j]), which properties hold? (Select all that apply)

|   |   |
|---|---|
|![Selected](https://s.brightspace.com/lib/bsi/2026.1.213/images/tier2/check-box.svg "Selected")|All elements in A[p..i] are ≤ pivot|
|![Selected](https://s.brightspace.com/lib/bsi/2026.1.213/images/tier2/check-box.svg "Selected")|All elements in A[i+1..j-1] are > pivot|
|![Unselected](https://s.brightspace.com/lib/bsi/2026.1.213/images/tier2/check-box-unchecked.svg "Unselected")|All elements in A[j..r-1] have been examined|
|![Selected](https://s.brightspace.com/lib/bsi/2026.1.213/images/tier2/check-box.svg "Selected")|A[r] contains the pivot|
|![Unselected](https://s.brightspace.com/lib/bsi/2026.1.213/images/tier2/check-box-unchecked.svg "Unselected")|The subarray A[p..j] is sorted|
|![Unselected](https://s.brightspace.com/lib/bsi/2026.1.213/images/tier2/check-box-unchecked.svg "Unselected")|A[i] > A[i+1]|

|   |   |
|---|---|
|Hide question 6 feedback|   |
|||
|## Feedback<br><br>Loop invariant maintains: [≤pivot][>pivot][unexamined][pivot]. This ensures correctness when the loop terminates!<br><br>Correct! This is the low side - all examined elements ≤ pivot are here.<br><br>Correct! This is the high side - all examined elements > pivot are here.<br><br>Correct! The pivot stays at position r until the final swap.|   |

|   |   |   |
|---|---|---|
|**Question 7**||2 / 2 points|

Order these steps to show how QUICKSORT(A, p, r) works:

|   |   |   |   |
|---|---|---|---|
||__3__||Recursively call QUICKSORT(A, p, q-1) to sort the low side|
||__2__||Call PARTITION(A, p, r) to partition around a pivot, returning q|
||__4__||Recursively call QUICKSORT(A, q+1, r) to sort the high side|
||__1__||Check if p < r (base case: at least 2 elements)|

|   |   |
|---|---|
|Hide question 7 feedback|   |
|||
|## Feedback<br><br>QuickSort: (1) Check base case, (2) Partition around pivot, (3) Recursively sort low side, (4) Recursively sort high side. No combine step needed!Step 3: Sort elements less than pivotStep 2: Partition the array, placing pivot in final positionStep 4: Sort elements greater than pivotStep 1: Base case check - single elements are already sorted|   |

|   |   |   |
|---|---|---|
|**Question 8**||1 / 1 point|

Consider partitioning array [8, 3, 7, 1, 5, 6, 2, 4] with pivot = 4 (last element). After PARTITION completes, which element will be at the pivot's final position?

|   |   |
|---|---|
|![Selected](https://stcloudstate.learn.minnstate.edu/d2l/img/0/QuestionCollection.Main.radioChecked.svg?v=20.26.1.24929 "Selected")|4 will be at index 4 in the partitioned array|
|![Unselected](https://stcloudstate.learn.minnstate.edu/d2l/img/0/QuestionCollection.Main.radioUnchecked.svg?v=20.26.1.24929 "Unselected")|4 will be at index 3|
|![Unselected](https://stcloudstate.learn.minnstate.edu/d2l/img/0/QuestionCollection.Main.radioUnchecked.svg?v=20.26.1.24929 "Unselected")|4 will remain at the last position|
|![Unselected](https://stcloudstate.learn.minnstate.edu/d2l/img/0/QuestionCollection.Main.radioUnchecked.svg?v=20.26.1.24929 "Unselected")|4 will be at index 0|

|   |   |
|---|---|
|Hide question 8 feedback|   |
|||
|## Feedback<br><br>Elements ≤4: {3,1,2,4} = 4 elements. In 1-indexed array, 4 goes to position 4. After: [3,1,2,4,8,7,6,5] or similar permutation.<br><br>Correct! Elements ≤4 are: 3,1,2,4 (4 elements). So 4 ends up at position 4 (0-indexed) or position 5 (1-indexed).|   |

|   |   |   |
|---|---|---|
|**Question 9**||1 / 1 point|

Which property is TRUE about QuickSort compared to MergeSort and HeapSort?

|   |   |
|---|---|
|![Selected](https://stcloudstate.learn.minnstate.edu/d2l/img/0/QuestionCollection.Main.radioChecked.svg?v=20.26.1.24929 "Selected")|QuickSort has worse worst-case time (Θ(n²)) but often faster average-case performance in practice|
|![Unselected](https://stcloudstate.learn.minnstate.edu/d2l/img/0/QuestionCollection.Main.radioUnchecked.svg?v=20.26.1.24929 "Unselected")|QuickSort always runs faster than MergeSort and HeapSort on all inputs|
|![Unselected](https://stcloudstate.learn.minnstate.edu/d2l/img/0/QuestionCollection.Main.radioUnchecked.svg?v=20.26.1.24929 "Unselected")|QuickSort uses less space than both MergeSort and HeapSort|
|![Unselected](https://stcloudstate.learn.minnstate.edu/d2l/img/0/QuestionCollection.Main.radioUnchecked.svg?v=20.26.1.24929 "Unselected")|QuickSort is a stable sorting algorithm while MergeSort is not|

|   |   |
|---|---|
|Hide question 9 feedback|   |
|||
|## Feedback<br><br>QuickSort: Θ(n²) worst-case, but Θ(n log n) expected with small constants. Often fastest in practice despite weaker worst-case guarantee!<br><br>Correct! QuickSort is Θ(n²) worst-case but has small constants in the Θ(n log n) expected case, making it fast in practice.|   |

|   |   |   |
|---|---|---|
|**Question 10**||1 / 1 point|

To sort an entire array A of n elements using 1-indexed arrays, what is the initial call to QUICKSORT? Write your answer as: QUICKSORT(A, start, end) with specific values for start and end.

|   |   |   |
|---|---|---|
|Answer:|QUICKSORT(A, 1, n)||

|                                                                                                                                          |     |
| ---------------------------------------------------------------------------------------------------------------------------------------- | --- |
| Hide question 10 feedback                                                                                                                |     |
|                                                                                                                                          |     |
| ## Feedback<br><br>For 1-indexed array of n elements, the initial call is QUICKSORT(A, 1, n) to sort the entire array from index 1 to n. |     |
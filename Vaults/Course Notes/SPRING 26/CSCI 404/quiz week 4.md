## quiz 1

|   |   |   |
|---|---|---|
|**Question 1**||1 / 1 point|

What type of binary tree is a heap?

|   |   |
|---|---|
|![Selected](https://stcloudstate.learn.minnstate.edu/d2l/img/0/QuestionCollection.Main.radioChecked.svg?v=20.26.1.23576 "Selected")|A nearly complete binary tree where all levels are filled except possibly the last, which is filled from left to right|
|![Unselected](https://stcloudstate.learn.minnstate.edu/d2l/img/0/QuestionCollection.Main.radioUnchecked.svg?v=20.26.1.23576 "Unselected")|A completely balanced binary tree where all nodes have exactly two children|
|![Unselected](https://stcloudstate.learn.minnstate.edu/d2l/img/0/QuestionCollection.Main.radioUnchecked.svg?v=20.26.1.23576 "Unselected")|A binary search tree where left children are smaller than the parent|
|![Unselected](https://stcloudstate.learn.minnstate.edu/d2l/img/0/QuestionCollection.Main.radioUnchecked.svg?v=20.26.1.23576 "Unselected")|A full binary tree where all leaves are at the same level|

|   |   |
|---|---|
|Hide question 1 feedback|   |
|||
|## Feedback<br><br>Heaps are nearly complete binary trees, which allows them to be efficiently stored in arrays without wasted space.<br><br>Correct! A heap is a nearly complete binary tree, ensuring efficient array representation.|   |

|   |   |   |
|---|---|---|
|**Question 2**||1 / 1 point|

In a 1-indexed array representation of a heap, if a node is at index i = 6, what is the index of its parent?

|   |   |
|---|---|
|![Selected](https://stcloudstate.learn.minnstate.edu/d2l/img/0/QuestionCollection.Main.radioChecked.svg?v=20.26.1.23576 "Selected")|3|
|![Unselected](https://stcloudstate.learn.minnstate.edu/d2l/img/0/QuestionCollection.Main.radioUnchecked.svg?v=20.26.1.23576 "Unselected")|2|
|![Unselected](https://stcloudstate.learn.minnstate.edu/d2l/img/0/QuestionCollection.Main.radioUnchecked.svg?v=20.26.1.23576 "Unselected")|12|
|![Unselected](https://stcloudstate.learn.minnstate.edu/d2l/img/0/QuestionCollection.Main.radioUnchecked.svg?v=20.26.1.23576 "Unselected")|5|

|   |   |
|---|---|
|Hide question 2 feedback|   |
|||
|## Feedback<br><br>For any node at index i, its parent is at index ⌊i/2⌋. So PARENT(6) = ⌊6/2⌋ = 3<br><br>Correct! PARENT(i) = ⌊i/2⌋ = ⌊6/2⌋ = 3|   |

|   |   |   |
|---|---|---|
|**Question 3**||1 / 1 point|

In a 1-indexed array representation, what are the indices of the children of node at index i = 5?

|   |   |
|---|---|
|![Selected](https://stcloudstate.learn.minnstate.edu/d2l/img/0/QuestionCollection.Main.radioChecked.svg?v=20.26.1.23576 "Selected")|Left child at 10, right child at 11|
|![Unselected](https://stcloudstate.learn.minnstate.edu/d2l/img/0/QuestionCollection.Main.radioUnchecked.svg?v=20.26.1.23576 "Unselected")|Left child at 6, right child at 7|
|![Unselected](https://stcloudstate.learn.minnstate.edu/d2l/img/0/QuestionCollection.Main.radioUnchecked.svg?v=20.26.1.23576 "Unselected")|Left child at 4, right child at 5|
|![Unselected](https://stcloudstate.learn.minnstate.edu/d2l/img/0/QuestionCollection.Main.radioUnchecked.svg?v=20.26.1.23576 "Unselected")|Left child at 9, right child at 10|

|   |   |
|---|---|
|Hide question 3 feedback|   |
|||
|## Feedback<br><br>For node at index i=5: LEFT(5) = 2*5 = 10 and RIGHT(5) = 2*5+1 = 11<br><br>Correct! LEFT(5) = 2*5 = 10, RIGHT(5) = 2*5+1 = 11|   |

|   |   |   |
|---|---|---|
|**Question 4**||1 / 1 point|

Which statement correctly describes the max-heap property?

|   |   |
|---|---|
|![Selected](https://stcloudstate.learn.minnstate.edu/d2l/img/0/QuestionCollection.Main.radioChecked.svg?v=20.26.1.23576 "Selected")|For every node i other than the root, A[PARENT(i)] ≥ A[i]|
|![Unselected](https://stcloudstate.learn.minnstate.edu/d2l/img/0/QuestionCollection.Main.radioUnchecked.svg?v=20.26.1.23576 "Unselected")|For every node i, A[i] ≥ A[PARENT(i)]|
|![Unselected](https://stcloudstate.learn.minnstate.edu/d2l/img/0/QuestionCollection.Main.radioUnchecked.svg?v=20.26.1.23576 "Unselected")|For every node i, A[LEFT(i)] > A[RIGHT(i)]|
|![Unselected](https://stcloudstate.learn.minnstate.edu/d2l/img/0/QuestionCollection.Main.radioUnchecked.svg?v=20.26.1.23576 "Unselected")|The array must be sorted in decreasing order|

|   |   |
|---|---|
|Hide question 4 feedback|   |
|||
|## Feedback<br><br>The max-heap property states that every parent is greater than or equal to its children: A[PARENT(i)] ≥ A[i]<br><br>Correct! The parent must be greater than or equal to its children.|   |

|   |   |   |
|---|---|---|
|**Question 5**||1 / 1 point|

True or False: A max-heap is always stored as a fully sorted array in descending order.

|   |   |   |
|---|---|---|
||![Unselected](https://stcloudstate.learn.minnstate.edu/d2l/img/0/QuestionCollection.Main.radioUnchecked.svg?v=20.26.1.23576 "Unselected")|True|
||![Selected](https://stcloudstate.learn.minnstate.edu/d2l/img/0/QuestionCollection.Main.radioChecked.svg?v=20.26.1.23576 "Selected")|False|

|   |   |
|---|---|
|Hide question 5 feedback|   |
|||
|## Feedback<br><br>Heaps maintain the heap property (parent ≥ children) but are NOT fully sorted. The array [16,14,10,8,7,9,3] is a valid max-heap even though 7<10 and 9<10.<br><br>Correct! Heaps maintain only partial order (parent ≥ children), not full sorting. For example, [16,14,10,8,7,9,3] is a valid max-heap but not sorted.|   |

|   |   |   |
|---|---|---|
|**Question 6**||1 / 1 point|

What is the height of a heap with n = 15 elements? (Height is defined as the number of edges on the longest path from root to leaf)

|   |   |
|---|---|
|![Selected](https://stcloudstate.learn.minnstate.edu/d2l/img/0/QuestionCollection.Main.radioChecked.svg?v=20.26.1.23576 "Selected")|3|
|![Unselected](https://stcloudstate.learn.minnstate.edu/d2l/img/0/QuestionCollection.Main.radioUnchecked.svg?v=20.26.1.23576 "Unselected")|4|
|![Unselected](https://stcloudstate.learn.minnstate.edu/d2l/img/0/QuestionCollection.Main.radioUnchecked.svg?v=20.26.1.23576 "Unselected")|15|
|![Unselected](https://stcloudstate.learn.minnstate.edu/d2l/img/0/QuestionCollection.Main.radioUnchecked.svg?v=20.26.1.23576 "Unselected")|2|

|   |   |
|---|---|
|Hide question 6 feedback|   |
|||
|## Feedback<br><br>For n=15 elements, height = ⌊log₂(15)⌋ = ⌊3.906⌋ = 3. A complete binary tree of height 3 has between 8 and 15 nodes.<br><br>Correct! Height = ⌊log₂(15)⌋ = ⌊3.9⌋ = 3|   |

|   |   |   |
|---|---|---|
|**Question 7**||1 / 1 point|

Which of the following are TRUE about max-heaps? (Select all that apply)

|   |   |
|---|---|
|![Selected](https://s.brightspace.com/lib/bsi/2026.1.213/images/tier2/check-box.svg "Selected")|The largest element is always at the root (index 1)|
|![Selected](https://s.brightspace.com/lib/bsi/2026.1.213/images/tier2/check-box.svg "Selected")|The height of an n-element heap is ⌊log₂(n)⌋|
|![Unselected](https://s.brightspace.com/lib/bsi/2026.1.213/images/tier2/check-box-unchecked.svg "Unselected")|The array must be sorted in descending order|
|![Selected](https://s.brightspace.com/lib/bsi/2026.1.213/images/tier2/check-box.svg "Selected")|Finding the maximum element takes O(1) time|
|![Unselected](https://s.brightspace.com/lib/bsi/2026.1.213/images/tier2/check-box-unchecked.svg "Unselected")|All elements on the left half are larger than elements on the right half|
|![Selected](https://s.brightspace.com/lib/bsi/2026.1.213/images/tier2/check-box.svg "Selected")|Every parent node has a value greater than or equal to its children|

|   |   |
|---|---|
|Hide question 7 feedback|   |
|||
|## Feedback<br><br>Max-heaps have the root as maximum (O(1) access), height O(log n), and every parent ≥ children. They are NOT fully sorted.<br><br>Correct! The max-heap property ensures the maximum is at the root.<br><br>Correct! This is a key property that makes heap operations O(log n).<br><br>Correct! It's just A[1], constant time access.<br><br>Correct! This is the definition of the max-heap property.|   |

|   |   |   |
|---|---|---|
|**Question 8**||1 / 1 point|

In a heap with n = 10 elements stored in array A[1..10], which indices represent leaf nodes?

|   |   |
|---|---|
|![Selected](https://stcloudstate.learn.minnstate.edu/d2l/img/0/QuestionCollection.Main.radioChecked.svg?v=20.26.1.23576 "Selected")|Indices 6, 7, 8, 9, 10|
|![Unselected](https://stcloudstate.learn.minnstate.edu/d2l/img/0/QuestionCollection.Main.radioUnchecked.svg?v=20.26.1.23576 "Unselected")|Indices 5, 6, 7, 8, 9, 10|
|![Unselected](https://stcloudstate.learn.minnstate.edu/d2l/img/0/QuestionCollection.Main.radioUnchecked.svg?v=20.26.1.23576 "Unselected")|Indices 8, 9, 10|
|![Unselected](https://stcloudstate.learn.minnstate.edu/d2l/img/0/QuestionCollection.Main.radioUnchecked.svg?v=20.26.1.23576 "Unselected")|Only index 10|

|   |   |
|---|---|
|Hide question 8 feedback|   |
|||
|## Feedback<br><br>The leaves are elements A[⌊n/2⌋+1..n]. For n=10: leaves are A[6..10]. This is because LEFT(5)=10 (last node with a child).<br><br>Correct! Leaves are at indices ⌊n/2⌋+1 through n, so ⌊10/2⌋+1=6 through 10.|   |

|   |   |   |
|---|---|---|
|**Question 9**||1 / 1 point|

Which array represents a valid MIN-heap?

|   |   |
|---|---|
|![Selected](https://stcloudstate.learn.minnstate.edu/d2l/img/0/QuestionCollection.Main.radioChecked.svg?v=20.26.1.23576 "Selected")|[1, 2, 3, 4, 5, 6, 7]|
|![Unselected](https://stcloudstate.learn.minnstate.edu/d2l/img/0/QuestionCollection.Main.radioUnchecked.svg?v=20.26.1.23576 "Unselected")|[7, 6, 5, 4, 3, 2, 1]|
|![Unselected](https://stcloudstate.learn.minnstate.edu/d2l/img/0/QuestionCollection.Main.radioUnchecked.svg?v=20.26.1.23576 "Unselected")|[1, 3, 2, 7, 4, 6, 5]|
|![Unselected](https://stcloudstate.learn.minnstate.edu/d2l/img/0/QuestionCollection.Main.radioUnchecked.svg?v=20.26.1.23576 "Unselected")|[4, 2, 6, 1, 3, 5, 7]|

|   |   |
|---|---|
|Hide question 9 feedback|   |
|||
|## Feedback<br><br>Check each parent-child relationship. In [1,2,3,4,5,6,7]: 1≤2,3; 2≤4,5; 3≤6,7. All valid!<br><br>Correct! Every parent is less than its children: 1<2,3; 2<4,5; 3<6,7|   |

|   |   |   |
|---|---|---|
|**Question 10**||1 / 1 point|

What is the key difference between a COMPLETE binary tree (used for heaps) and a FULL binary tree?

|   |   |
|---|---|
|![Selected](https://stcloudstate.learn.minnstate.edu/d2l/img/0/QuestionCollection.Main.radioChecked.svg?v=20.26.1.23576 "Selected")|A complete tree's last level is filled left-to-right but may be incomplete; a full tree has all levels completely filled|
|![Unselected](https://stcloudstate.learn.minnstate.edu/d2l/img/0/QuestionCollection.Main.radioUnchecked.svg?v=20.26.1.23576 "Unselected")|A full tree can have gaps in its array representation; a complete tree cannot|
|![Unselected](https://stcloudstate.learn.minnstate.edu/d2l/img/0/QuestionCollection.Main.radioUnchecked.svg?v=20.26.1.23576 "Unselected")|A complete tree must have all nodes with exactly 2 or 0 children; a full tree doesn't|
|![Unselected](https://stcloudstate.learn.minnstate.edu/d2l/img/0/QuestionCollection.Main.radioUnchecked.svg?v=20.26.1.23576 "Unselected")|There is no difference; they are the same concept|

|   |   |
|---|---|
|Hide question 10 feedback|   |
|||
|## Feedback<br><br>Complete binary trees (used for heaps) have all levels full except possibly the last, which is filled left-to-right. This ensures consecutive array storage.<br><br>Correct! Complete trees allow partial filling of the last level (left-to-right), enabling efficient array representation.|   |
## quiz 2
|   |   |   |
|---|---|---|
|**Question 1**||1 / 1 point|

What is the purpose of the MAX-HEAPIFY(A, i) procedure?

|   |   |
|---|---|
|![Selected](https://stcloudstate.learn.minnstate.edu/d2l/img/0/QuestionCollection.Main.radioChecked.svg?v=20.26.1.23576 "Selected")|To restore the max-heap property at node i, assuming its children's subtrees are already max-heaps|
|![Unselected](https://stcloudstate.learn.minnstate.edu/d2l/img/0/QuestionCollection.Main.radioUnchecked.svg?v=20.26.1.23576 "Unselected")|To build a max-heap from an unordered array|
|![Unselected](https://stcloudstate.learn.minnstate.edu/d2l/img/0/QuestionCollection.Main.radioUnchecked.svg?v=20.26.1.23576 "Unselected")|To extract the maximum element from the heap|
|![Unselected](https://stcloudstate.learn.minnstate.edu/d2l/img/0/QuestionCollection.Main.radioUnchecked.svg?v=20.26.1.23576 "Unselected")|To insert a new element into the heap|

|   |   |
|---|---|
|Hide question 1 feedback|   |
|||
|## Feedback<br><br>MAX-HEAPIFY assumes the subtrees at LEFT(i) and RIGHT(i) are valid max-heaps, then fixes any violation at node i by floating it down.<br><br>Correct! MAX-HEAPIFY floats the value at i down until the subtree rooted at i satisfies the max-heap property.|   |

|   |   |   |
|---|---|---|
|**Question 2**||1 / 1 point|

What is the worst-case running time of MAX-HEAPIFY(A, i) on a heap of n elements?

|   |   |
|---|---|
|![Selected](https://stcloudstate.learn.minnstate.edu/d2l/img/0/QuestionCollection.Main.radioChecked.svg?v=20.26.1.23576 "Selected")|O(log n)|
|![Unselected](https://stcloudstate.learn.minnstate.edu/d2l/img/0/QuestionCollection.Main.radioUnchecked.svg?v=20.26.1.23576 "Unselected")|O(n)|
|![Unselected](https://stcloudstate.learn.minnstate.edu/d2l/img/0/QuestionCollection.Main.radioUnchecked.svg?v=20.26.1.23576 "Unselected")|O(1)|
|![Unselected](https://stcloudstate.learn.minnstate.edu/d2l/img/0/QuestionCollection.Main.radioUnchecked.svg?v=20.26.1.23576 "Unselected")|O(n log n)|

|   |   |
|---|---|
|Hide question 2 feedback|   |
|||
|## Feedback<br><br>MAX-HEAPIFY follows a single path from node i to a leaf in the worst case. Since heap height is O(log n), the running time is O(log n).<br><br>Correct! MAX-HEAPIFY may traverse from node i down to a leaf, which is O(height) = O(log n).|   |

|   |   |   |
|---|---|---|
|**Question 3**||1 / 1 point|

What is the tight asymptotic running time of BUILD-MAX-HEAP on an array of n elements?

|   |   |
|---|---|
|![Selected](https://stcloudstate.learn.minnstate.edu/d2l/img/0/QuestionCollection.Main.radioChecked.svg?v=20.26.1.23576 "Selected")|Θ(n)|
|![Unselected](https://stcloudstate.learn.minnstate.edu/d2l/img/0/QuestionCollection.Main.radioUnchecked.svg?v=20.26.1.23576 "Unselected")|Θ(n log n)|
|![Unselected](https://stcloudstate.learn.minnstate.edu/d2l/img/0/QuestionCollection.Main.radioUnchecked.svg?v=20.26.1.23576 "Unselected")|Θ(log n)|
|![Unselected](https://stcloudstate.learn.minnstate.edu/d2l/img/0/QuestionCollection.Main.radioUnchecked.svg?v=20.26.1.23576 "Unselected")|Θ(n²)|

|   |   |
|---|---|
|Hide question 3 feedback|   |
|||
|## Feedback<br><br>BUILD-MAX-HEAP runs in Θ(n) time. While we call MAX-HEAPIFY n/2 times, most calls are on nodes near leaves where work is minimal. The sum Σ(h=0 to log n) ⌈n/2^(h+1)⌉·O(h) = O(n).<br><br>Correct! Although it seems like O(n log n), the tight bound is Θ(n) because most nodes are near the leaves where MAX-HEAPIFY does little work.|   |

|   |   |   |
|---|---|---|
|**Question 4**||1 / 1 point|

BUILD-MAX-HEAP starts calling MAX-HEAPIFY from which index and proceeds in which direction?

|   |   |
|---|---|
|![Selected](https://stcloudstate.learn.minnstate.edu/d2l/img/0/QuestionCollection.Main.radioChecked.svg?v=20.26.1.23576 "Selected")|Starts at ⌊n/2⌋ and proceeds downto 1|
|![Unselected](https://stcloudstate.learn.minnstate.edu/d2l/img/0/QuestionCollection.Main.radioUnchecked.svg?v=20.26.1.23576 "Unselected")|Starts at 1 and proceeds to n|
|![Unselected](https://stcloudstate.learn.minnstate.edu/d2l/img/0/QuestionCollection.Main.radioUnchecked.svg?v=20.26.1.23576 "Unselected")|Starts at n and proceeds downto 1|
|![Unselected](https://stcloudstate.learn.minnstate.edu/d2l/img/0/QuestionCollection.Main.radioUnchecked.svg?v=20.26.1.23576 "Unselected")|Starts at ⌊n/2⌋ and proceeds to n|

|   |   |
|---|---|
|Hide question 4 feedback|   |
|||
|## Feedback<br><br>BUILD-MAX-HEAP starts at ⌊n/2⌋ (last internal node) and works backwards to 1 (root). Nodes ⌊n/2⌋+1 through n are leaves and don't need processing.<br><br>Correct! We start at the last internal node and work backwards to the root.|   |

|   |   |   |
|---|---|---|
|**Question 5**||1 / 1 point|

What is the worst-case running time of HEAPSORT on an array of n elements?

|   |   |
|---|---|
|![Selected](https://stcloudstate.learn.minnstate.edu/d2l/img/0/QuestionCollection.Main.radioChecked.svg?v=20.26.1.23576 "Selected")|Θ(n log n)|
|![Unselected](https://stcloudstate.learn.minnstate.edu/d2l/img/0/QuestionCollection.Main.radioUnchecked.svg?v=20.26.1.23576 "Unselected")|Θ(n)|
|![Unselected](https://stcloudstate.learn.minnstate.edu/d2l/img/0/QuestionCollection.Main.radioUnchecked.svg?v=20.26.1.23576 "Unselected")|Θ(n²)|
|![Unselected](https://stcloudstate.learn.minnstate.edu/d2l/img/0/QuestionCollection.Main.radioUnchecked.svg?v=20.26.1.23576 "Unselected")|Θ(log n)|

|   |   |
|---|---|
|Hide question 5 feedback|   |
|||
|## Feedback<br><br>HEAPSORT: BUILD-MAX-HEAP takes O(n), then we extract maximum n-1 times, each taking O(log n). Total: O(n) + O(n log n) = Θ(n log n).<br><br>Correct! BUILD-MAX-HEAP takes O(n), then we call MAX-HEAPIFY n-1 times at O(log n) each: O(n) + (n-1)·O(log n) = Θ(n log n).|   |

|   |   |   |
|---|---|---|
|**Question 6**||1 / 1 point|

True or False: HEAPSORT requires O(n) auxiliary space for a temporary array, similar to merge sort.

|   |   |   |
|---|---|---|
||![Unselected](https://stcloudstate.learn.minnstate.edu/d2l/img/0/QuestionCollection.Main.radioUnchecked.svg?v=20.26.1.23576 "Unselected")|True|
||![Selected](https://stcloudstate.learn.minnstate.edu/d2l/img/0/QuestionCollection.Main.radioChecked.svg?v=20.26.1.23576 "Selected")|False|

|   |   |
|---|---|
|Hide question 6 feedback|   |
|||
|## Feedback<br><br>HEAPSORT sorts in place, requiring only O(1) extra space for a few variables. The sorted elements accumulate at the end of the array as the heap shrinks.<br><br>Correct! HEAPSORT sorts in place using the input array itself, requiring only O(1) auxiliary space. This is one of its main advantages over merge sort.|   |

|   |   |   |
|---|---|---|
|**Question 7**||2 / 2 points|

Which of the following are correct steps in the HEAPSORT algorithm? (Select all that apply)

|   |   |
|---|---|
|![Selected](https://s.brightspace.com/lib/bsi/2026.1.213/images/tier2/check-box.svg "Selected")|Call BUILD-MAX-HEAP on the input array|
|![Selected](https://s.brightspace.com/lib/bsi/2026.1.213/images/tier2/check-box.svg "Selected")|Swap the root with the last element in the heap|
|![Selected](https://s.brightspace.com/lib/bsi/2026.1.213/images/tier2/check-box.svg "Selected")|Decrement heap-size to exclude the sorted elements|
|![Selected](https://s.brightspace.com/lib/bsi/2026.1.213/images/tier2/check-box.svg "Selected")|Call MAX-HEAPIFY(A, 1) after each swap|
|![Unselected](https://s.brightspace.com/lib/bsi/2026.1.213/images/tier2/check-box-unchecked.svg "Unselected")|Call MAX-HEAPIFY on all nodes after each extraction|
|![Unselected](https://s.brightspace.com/lib/bsi/2026.1.213/images/tier2/check-box-unchecked.svg "Unselected")|Use a temporary array to store sorted elements|

|   |   |
|---|---|
|Hide question 7 feedback|   |
|||
|## Feedback<br><br>HEAPSORT: (1) BUILD-MAX-HEAP, (2) repeatedly swap root with last element, (3) decrement heap-size, (4) MAX-HEAPIFY(1). It sorts in place!<br><br>Correct! This is step 1 - convert the unordered array into a max-heap.<br><br>Correct! This places the maximum element in its final sorted position.<br><br>Correct! We shrink the heap boundary, growing the sorted section.<br><br>Correct! This restores the heap property after moving a small element to the root.|   |

|   |   |   |
|---|---|---|
|**Question 8**||2 / 2 points|

Order these steps to show how MAX-HEAPIFY(A, i) works:

|   |   |   |   |
|---|---|---|---|
||__1__||Compute l = LEFT(i) and r = RIGHT(i)|
||__4__||Recursively call MAX-HEAPIFY(A, largest)|
||__3__||If largest ≠ i, swap A[i] with A[largest]|
||__2__||Compare A[i] with A[l] and A[r] to find the largest|

|   |   |
|---|---|
|Hide question 8 feedback|   |
|||
|## Feedback<br><br>MAX-HEAPIFY: (1) Get children, (2) Find largest of parent and children, (3) Swap if needed, (4) Recurse on affected subtree.Step 1: Get the indices of the childrenStep 4: Continue fixing down the affected subtreeStep 3: Fix the violation by swapping if necessaryStep 2: Determine which of the three values is largest|   |

|   |   |   |
|---|---|---|
|**Question 9**||1 / 1 point|

Consider the array [3, 5, 1, 4, 2]. After calling BUILD-MAX-HEAP, which element will be at the root (index 1)?

|   |   |
|---|---|
|![Selected](https://stcloudstate.learn.minnstate.edu/d2l/img/0/QuestionCollection.Main.radioChecked.svg?v=20.26.1.23576 "Selected")|5|
|![Unselected](https://stcloudstate.learn.minnstate.edu/d2l/img/0/QuestionCollection.Main.radioUnchecked.svg?v=20.26.1.23576 "Unselected")|3|
|![Unselected](https://stcloudstate.learn.minnstate.edu/d2l/img/0/QuestionCollection.Main.radioUnchecked.svg?v=20.26.1.23576 "Unselected")|1|
|![Unselected](https://stcloudstate.learn.minnstate.edu/d2l/img/0/QuestionCollection.Main.radioUnchecked.svg?v=20.26.1.23576 "Unselected")|4|

|   |   |
|---|---|
|Hide question 9 feedback|   |
|||
|## Feedback<br><br>BUILD-MAX-HEAP creates a max-heap where the root is the maximum. For [3,5,1,4,2], the maximum is 5, so it will be at A[1].<br><br>Correct! After BUILD-MAX-HEAP, the maximum element (5) must be at the root.|   |

|   |   |   |
|---|---|---|
|**Question 10**||1 / 1 point|

In BUILD-MAX-HEAP on an array of n=20 elements, how many times is MAX-HEAPIFY called? (Enter just the number)

|   |   |   |
|---|---|---|
|Answer:|10||

|   |   |
|---|---|
|Hide question 10 feedback|   |
|||
|## Feedback<br><br>BUILD-MAX-HEAP calls MAX-HEAPIFY for i = ⌊20/2⌋ downto 1, which is i = 10 downto 1. That's 10 calls.|   |
## quiz 3
In which scenarios would a heap/priority queue be a POOR choice? (Select all that apply)

|   |   |
|---|---|
|![Selected](https://s.brightspace.com/lib/bsi/2026.1.213/images/tier2/check-box.svg "Selected")|Searching for an arbitrary element by value (not by priority)|
|![Selected](https://s.brightspace.com/lib/bsi/2026.1.213/images/tier2/check-box.svg "Selected")|Maintaining a fully sorted order of all elements at all times|
|![Unselected](https://s.brightspace.com/lib/bsi/2026.1.213/images/tier2/check-box-unchecked.svg "Unselected")|Finding the minimum or maximum element quickly|
|![Selected](https://s.brightspace.com/lib/bsi/2026.1.213/images/tier2/check-box.svg "Selected")|Accessing the median element efficiently|
|![Unselected](https://s.brightspace.com/lib/bsi/2026.1.213/images/tier2/check-box-unchecked.svg "Unselected")|Dynamic priority management where priorities change frequently|
|![Selected](https://s.brightspace.com/lib/bsi/2026.1.213/images/tier2/check-box.svg "Selected")|Random access to elements by index position|

|   |   |
|---|---|
|Hide question 1 feedback|   |
|||
|## Feedback<br><br>Heaps excel at min/max extraction and dynamic priorities, but struggle with arbitrary element search, maintaining full sort order, and random access patterns.<br><br>Correct! Heaps don't support efficient search for arbitrary values - that takes O(n) time.<br><br>Correct! Heaps are only partially ordered. If you need full sorted order continuously, use a balanced BST.<br><br>Correct! Heaps can't directly give you the median in O(1) time (though two heaps can maintain it in O(log n)).<br><br>Correct! While heaps use arrays, they don't support efficient random access to arbitrary positions in sorted order.|   |

|   |   |   |
|---|---|---|
|**Question 2**||2 / 2 points|

You need to sort 10 million records. Your teammate says: 'Let's use heapsort! It's O(n log n) like merge sort but uses WAY less space!' Are they correct?

|   |   |
|---|---|
|![Selected](https://stcloudstate.learn.minnstate.edu/d2l/img/0/QuestionCollection.Main.radioChecked.svg?v=20.26.1.23576 "Selected")|Yes, heapsort is O(n log n) time and O(1) space vs merge sort's O(n) space|
|![Unselected](https://stcloudstate.learn.minnstate.edu/d2l/img/0/QuestionCollection.Main.radioUnchecked.svg?v=20.26.1.23576 "Unselected")|No, heapsort is actually O(n²) time|
|![Unselected](https://stcloudstate.learn.minnstate.edu/d2l/img/0/QuestionCollection.Main.radioUnchecked.svg?v=20.26.1.23576 "Unselected")|No, heapsort uses O(n) space just like merge sort|
|![Unselected](https://stcloudstate.learn.minnstate.edu/d2l/img/0/QuestionCollection.Main.radioUnchecked.svg?v=20.26.1.23576 "Unselected")|Yes, but heapsort is O(n) time which is even better|

|   |   |
|---|---|
|Hide question 2 feedback|   |
|||
|## Feedback<br><br>Your teammate is right! Heapsort: O(n log n) time, O(1) space. Merge sort: O(n log n) time, O(n) space. Heapsort wins on space!<br><br>Correct! Your teammate understands the space-time tradeoff. Heapsort sorts in place!|   |

|   |   |   |
|---|---|---|
|**Question 3**||2 / 2 points|

You're running a video game tournament with 128 players. Each match eliminates one player. You want to quickly find the current top player after each match. Which data structure is BEST for this?

|   |   |
|---|---|
|![Selected](https://stcloudstate.learn.minnstate.edu/d2l/img/0/QuestionCollection.Main.radioChecked.svg?v=20.26.1.23576 "Selected")|A max-heap (max-priority queue)|
|![Unselected](https://stcloudstate.learn.minnstate.edu/d2l/img/0/QuestionCollection.Main.radioUnchecked.svg?v=20.26.1.23576 "Unselected")|A sorted array|
|![Unselected](https://stcloudstate.learn.minnstate.edu/d2l/img/0/QuestionCollection.Main.radioUnchecked.svg?v=20.26.1.23576 "Unselected")|An unsorted array|
|![Unselected](https://stcloudstate.learn.minnstate.edu/d2l/img/0/QuestionCollection.Main.radioUnchecked.svg?v=20.26.1.23576 "Unselected")|A linked list|

|   |   |
|---|---|
|Hide question 3 feedback|   |
|||
|## Feedback<br><br>A max-heap lets you extract the top player in O(log n) and update rankings in O(log n). Much better than re-sorting an array after each match!<br><br>Correct! Extract-max gives you the top player in O(log n), and you can update rankings efficiently. Perfect for tournament management!|   |

|   |   |   |
|---|---|---|
|**Question 4**||2 / 2 points|

You're implementing a real-time operating system scheduler. Tasks arrive with priorities, priorities change dynamically, and you need to quickly dispatch the highest-priority task. You need O(log n) or better for all operations. What's your move?

|   |   |
|---|---|
|![Selected](https://stcloudstate.learn.minnstate.edu/d2l/img/0/QuestionCollection.Main.radioChecked.svg?v=20.26.1.23576 "Selected")|Use a max-heap with handles/hash table for O(log n) insert, extract-max, and increase-key|
|![Unselected](https://stcloudstate.learn.minnstate.edu/d2l/img/0/QuestionCollection.Main.radioUnchecked.svg?v=20.26.1.23576 "Unselected")|Use a sorted array for O(1) max extraction|
|![Unselected](https://stcloudstate.learn.minnstate.edu/d2l/img/0/QuestionCollection.Main.radioUnchecked.svg?v=20.26.1.23576 "Unselected")|Use an unsorted array for O(1) insertion|
|![Unselected](https://stcloudstate.learn.minnstate.edu/d2l/img/0/QuestionCollection.Main.radioUnchecked.svg?v=20.26.1.23576 "Unselected")|Use a binary search tree|

|   |   |
|---|---|
|Hide question 4 feedback|   |
|||
|## Feedback<br><br>Max-heap with proper indexing (handles/hash) gives O(log n) for insert, extract, and update - perfect for real-time scheduling!<br><br>Correct! This is the classic solution for dynamic priority scheduling. Handles enable O(log n) updates by position.|   |

|   |   |   |
|---|---|---|
|**Question 5**||2 / 2 points|

Netflix wants to recommend movies by priority score, but scores change as users interact with the app. They need to frequently extract the highest-priority item and update priorities. What's the time complexity for these operations using a heap of size n?

|   |   |
|---|---|
|![Selected](https://stcloudstate.learn.minnstate.edu/d2l/img/0/QuestionCollection.Main.radioChecked.svg?v=20.26.1.23576 "Selected")|O(log n) for both extraction and priority update|
|![Unselected](https://stcloudstate.learn.minnstate.edu/d2l/img/0/QuestionCollection.Main.radioUnchecked.svg?v=20.26.1.23576 "Unselected")|O(1) for extraction, O(n) for update|
|![Unselected](https://stcloudstate.learn.minnstate.edu/d2l/img/0/QuestionCollection.Main.radioUnchecked.svg?v=20.26.1.23576 "Unselected")|O(n) for extraction, O(log n) for update|
|![Unselected](https://stcloudstate.learn.minnstate.edu/d2l/img/0/QuestionCollection.Main.radioUnchecked.svg?v=20.26.1.23576 "Unselected")|O(1) for both operations|

|   |   |
|---|---|
|Hide question 5 feedback|   |
|||
|## Feedback<br><br>Both EXTRACT-MAX and INCREASE-KEY run in O(log n) because they may traverse the height of the heap to maintain the heap property.<br><br>Correct! EXTRACT-MAX and INCREASE-KEY both run in O(log n) time. Heaps are perfect for dynamic priority queues!|   |

|   |   |   |
|---|---|---|
|**Question 6**||2 / 2 points|

Surprising fact: BUILD-MAX-HEAP on n elements is O(n), not O(n log n)! Why? What's the intuition?

|   |   |
|---|---|
|![Selected](https://stcloudstate.learn.minnstate.edu/d2l/img/0/QuestionCollection.Main.radioChecked.svg?v=20.26.1.23576 "Selected")|Most nodes are near the leaves where MAX-HEAPIFY does very little work|
|![Unselected](https://stcloudstate.learn.minnstate.edu/d2l/img/0/QuestionCollection.Main.radioUnchecked.svg?v=20.26.1.23576 "Unselected")|We only call MAX-HEAPIFY n/2 times, not n times|
|![Unselected](https://stcloudstate.learn.minnstate.edu/d2l/img/0/QuestionCollection.Main.radioUnchecked.svg?v=20.26.1.23576 "Unselected")|MAX-HEAPIFY runs in O(1) time, not O(log n)|
|![Unselected](https://stcloudstate.learn.minnstate.edu/d2l/img/0/QuestionCollection.Main.radioUnchecked.svg?v=20.26.1.23576 "Unselected")|Actually, BUILD-MAX-HEAP is O(n log n), not O(n)|

|   |   |
|---|---|
|Hide question 6 feedback|   |
|||
|## Feedback<br><br>Key insight: In a heap, roughly n/2 nodes are leaves (work=0), n/4 are height 1 (work=1), etc. The sum Σ(n/2^h)·h converges to O(n)!<br><br>Correct! The mathematical insight: lots of shallow nodes (cheap work) × many nodes dominates few deep nodes (expensive work) × few nodes.|   |

|   |   |   |
|---|---|---|
|**Question 7**||2 / 2 points|

An ER uses a priority queue where patients are treated by severity (10=critical, 1=minor). As new patients arrive and conditions change, severity scores are updated. If a patient's condition worsens from severity 3 to severity 9, which heap operation is used?

|   |   |
|---|---|
|![Selected](https://stcloudstate.learn.minnstate.edu/d2l/img/0/QuestionCollection.Main.radioChecked.svg?v=20.26.1.23576 "Selected")|INCREASE-KEY (for max-heap) or DECREASE-KEY (for min-heap with inverted priorities)|
|![Unselected](https://stcloudstate.learn.minnstate.edu/d2l/img/0/QuestionCollection.Main.radioUnchecked.svg?v=20.26.1.23576 "Unselected")|EXTRACT-MAX|
|![Unselected](https://stcloudstate.learn.minnstate.edu/d2l/img/0/QuestionCollection.Main.radioUnchecked.svg?v=20.26.1.23576 "Unselected")|INSERT|
|![Unselected](https://stcloudstate.learn.minnstate.edu/d2l/img/0/QuestionCollection.Main.radioUnchecked.svg?v=20.26.1.23576 "Unselected")|BUILD-HEAP|

|   |   |
|---|---|
|Hide question 7 feedback|   |
|||
|## Feedback<br><br>INCREASE-KEY updates a patient's priority and bubbles them up in the heap - running in O(log n) time. Much faster than rebuilding the entire queue!<br><br>Correct! When severity increases, we need to update the patient's priority and bubble them up in the priority queue.|   |

|   |   |   |
|---|---|---|
|**Question 8**||2 / 2 points|

You find this array: [16, 14, 10, 8, 7, 9, 3, 2, 4, 1]. Is this a valid max-heap?

|   |   |
|---|---|
|![Selected](https://stcloudstate.learn.minnstate.edu/d2l/img/0/QuestionCollection.Main.radioChecked.svg?v=20.26.1.23576 "Selected")|Yes, it's a valid max-heap|
|![Unselected](https://stcloudstate.learn.minnstate.edu/d2l/img/0/QuestionCollection.Main.radioUnchecked.svg?v=20.26.1.23576 "Unselected")|No, it violates the heap property|
|![Unselected](https://stcloudstate.learn.minnstate.edu/d2l/img/0/QuestionCollection.Main.radioUnchecked.svg?v=20.26.1.23576 "Unselected")|No, it's not a complete binary tree|
|![Unselected](https://stcloudstate.learn.minnstate.edu/d2l/img/0/QuestionCollection.Main.radioUnchecked.svg?v=20.26.1.23576 "Unselected")|Cannot determine without knowing heap-size|

|   |   |
|---|---|
|Hide question 8 feedback|   |
|||
|## Feedback<br><br>This is valid! Every parent is ≥ both children: 16≥14,10; 14≥8,7; 10≥9,3; 8≥2,4; 7≥1. Perfect max-heap!<br><br>Correct! Check all parent-child relationships: 16≥14,10; 14≥8,7; 10≥9,3; 8≥2,4. All valid!|   |

|   |   |   |
|---|---|---|
|**Question 9**||2 / 2 points|

You're in a coding competition with 1 million integers to sort on a memory-constrained system. Which sorting algorithm should you choose?

|   |   |
|---|---|
|![Selected](https://stcloudstate.learn.minnstate.edu/d2l/img/0/QuestionCollection.Main.radioChecked.svg?v=20.26.1.23576 "Selected")|Heapsort - O(n log n) time and O(1) space|
|![Unselected](https://stcloudstate.learn.minnstate.edu/d2l/img/0/QuestionCollection.Main.radioUnchecked.svg?v=20.26.1.23576 "Unselected")|Merge sort - O(n log n) time but O(n) space|
|![Unselected](https://stcloudstate.learn.minnstate.edu/d2l/img/0/QuestionCollection.Main.radioUnchecked.svg?v=20.26.1.23576 "Unselected")|Quicksort - fast average case but O(n²) worst case|
|![Unselected](https://stcloudstate.learn.minnstate.edu/d2l/img/0/QuestionCollection.Main.radioUnchecked.svg?v=20.26.1.23576 "Unselected")|Insertion sort - O(n²) but O(1) space|

|   |   |
|---|---|
|Hide question 9 feedback|   |
|||
|## Feedback<br><br>Heapsort is perfect for memory-constrained systems: guaranteed O(n log n) time and sorts in place with only O(1) extra space!<br><br>Correct! Heapsort guarantees O(n log n) with minimal memory overhead. Perfect for constrained systems!|   |

|   |   |   |
|---|---|---|
|**Question 10**||1.5 / 2 points|

Match each heap operation to its worst-case time complexity on a heap of n elements:

|   |   |   |
|---|---|---|
|\|   \|   \|   \|   \|<br>\|---\|---\|---\|---\|<br>\|![Incorrect Response](https://stcloudstate.learn.minnstate.edu/d2l/img/0/Shared.Main.infIncorrect.gif?v=20.26.1.23576 "Incorrect Response")\|__1__\|**(3)**\|O(n)\|<br>\|__2__\|O(log n)\|<br>\|__1__\|O(1)\|<br>\|__4__\|O(log n)\|||\|   \|   \|<br>\|---\|---\|<br>\|**1**.\|Finding the maximum element (MAX-HEAP-MAXIMUM)\|<br>\|**2**.\|Extracting the maximum element (EXTRACT-MAX)\|<br>\|**3**.\|Building a heap from an unordered array (BUILD-MAX-HEAP)\|<br>\|**4**.\|Increasing a key value (INCREASE-KEY)\||

|                                                                                                                                                    |     |
| -------------------------------------------------------------------------------------------------------------------------------------------------- | --- |
| Hide question 10 feedback                                                                                                                          |     |
|                                                                                                                                                    |     |
| ## Feedback<br><br>MAX = O(1) (just read A[1]); EXTRACT-MAX & INCREASE-KEY = O(log n) (traverse height); BUILD-HEAP = O(n) (surprising but true!). |     |
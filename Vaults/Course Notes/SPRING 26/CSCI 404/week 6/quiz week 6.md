## quiz 1

|                |     |             |
| -------------- | --- | ----------- |
| **Question 1** |     | 1 / 1 point |

What defines a comparison sort?

Question options:

|   |   |
|---|---|
|![Selected](https://stcloudstate.learn.minnstate.edu/d2l/img/0/QuestionCollection.Main.radioChecked.svg?v=20.26.2.21973 "Selected")|The only operation used to gain order information is comparing pairs of elements|
|![Unselected](https://stcloudstate.learn.minnstate.edu/d2l/img/0/QuestionCollection.Main.radioUnchecked.svg?v=20.26.2.21973 "Unselected")|The algorithm must compare every pair of elements at least once|
|![Unselected](https://stcloudstate.learn.minnstate.edu/d2l/img/0/QuestionCollection.Main.radioUnchecked.svg?v=20.26.2.21973 "Unselected")|The algorithm uses less than n² comparisons|
|![Unselected](https://stcloudstate.learn.minnstate.edu/d2l/img/0/QuestionCollection.Main.radioUnchecked.svg?v=20.26.2.21973 "Unselected")|The algorithm sorts elements by comparing their memory addresses|

|   |   |
|---|---|
|Hide question 1 feedback|   |
|||
|## Feedback<br><br>Comparison sorts gain order information ONLY through comparisons (≤, <, ≥, >, =). Examples: merge sort, quicksort, heapsort, insertion sort - all comparison sorts!<br><br>Correct! Comparison sorts can ONLY learn about element ordering through pairwise comparisons like A[i] ≤ A[j].|   |

|   |   |   |
|---|---|---|
|**Question 2**||1 / 1 point|

In the decision tree model for comparison sorts, what do the LEAVES represent?

Question options:

|   |   |
|---|---|
|![Selected](https://stcloudstate.learn.minnstate.edu/d2l/img/0/QuestionCollection.Main.radioChecked.svg?v=20.26.2.21973 "Selected")|Possible output permutations of the input|
|![Unselected](https://stcloudstate.learn.minnstate.edu/d2l/img/0/QuestionCollection.Main.radioUnchecked.svg?v=20.26.2.21973 "Unselected")|Individual comparisons between elements|
|![Unselected](https://stcloudstate.learn.minnstate.edu/d2l/img/0/QuestionCollection.Main.radioUnchecked.svg?v=20.26.2.21973 "Unselected")|The worst-case input for the algorithm|
|![Unselected](https://stcloudstate.learn.minnstate.edu/d2l/img/0/QuestionCollection.Main.radioUnchecked.svg?v=20.26.2.21973 "Unselected")|The number of comparisons made by the algorithm|

|   |   |
|---|---|
|Hide question 2 feedback|   |
|||
|## Feedback<br><br>Leaves = output permutations. For n=3 elements, we have 3!=6 possible leaves like ⟨1,2,3⟩, ⟨1,3,2⟩, etc. Each represents a sorted order.<br><br>Correct! Each leaf represents one of the n! possible sorted orderings of n elements.|   |

|   |   |   |
|---|---|---|
|**Question 3**||1 / 1 point|

What is the tight lower bound for comparison-based sorting in the worst case?

Question options:

|   |   |
|---|---|
|![Selected](https://stcloudstate.learn.minnstate.edu/d2l/img/0/QuestionCollection.Main.radioChecked.svg?v=20.26.2.21973 "Selected")|Ω(n log n) comparisons|
|![Unselected](https://stcloudstate.learn.minnstate.edu/d2l/img/0/QuestionCollection.Main.radioUnchecked.svg?v=20.26.2.21973 "Unselected")|Ω(n²) comparisons|
|![Unselected](https://stcloudstate.learn.minnstate.edu/d2l/img/0/QuestionCollection.Main.radioUnchecked.svg?v=20.26.2.21973 "Unselected")|Ω(n) comparisons|
|![Unselected](https://stcloudstate.learn.minnstate.edu/d2l/img/0/QuestionCollection.Main.radioUnchecked.svg?v=20.26.2.21973 "Unselected")|Ω(log n) comparisons|

|   |   |
|---|---|
|Hide question 3 feedback|   |
|||
|## Feedback<br><br>The lower bound is Ω(n log n). Proof: decision tree must have ≥n! leaves, height h ≥ log₂(n!) = Θ(n log n). Merge sort and heapsort match this bound!<br><br>Correct! Any comparison sort requires at least Ω(n log n) comparisons in the worst case - this is a fundamental limit.|   |

|   |   |   |
|---|---|---|
|**Question 4**||1 / 1 point|

True or False: A decision tree for a correct comparison sort on n elements must have at least n! reachable leaves.

Question options:

|   |   |
|---|---|
|![Selected](https://stcloudstate.learn.minnstate.edu/d2l/img/0/QuestionCollection.Main.radioChecked.svg?v=20.26.2.21973 "Selected")|True|
|![Unselected](https://stcloudstate.learn.minnstate.edu/d2l/img/0/QuestionCollection.Main.radioUnchecked.svg?v=20.26.2.21973 "Unselected")|False|

|   |   |
|---|---|
|Hide question 4 feedback|   |
|||
|## Feedback<br><br>n elements have n! possible permutations (sorted orders). A correct sort must handle all input patterns, so all n! permutations must appear as reachable leaves.<br><br>Correct! There are n! possible permutations of n elements, and a correct sorting algorithm must be able to produce ANY of them, so all must appear as leaves.|   |

|   |   |   |
|---|---|---|
|**Question 5**||1 / 1 point|

Counting sort requires that input elements are:

Question options:

|   |   |
|---|---|
|![Selected](https://stcloudstate.learn.minnstate.edu/d2l/img/0/QuestionCollection.Main.radioChecked.svg?v=20.26.2.21973 "Selected")|Integers in a range from 0 to k for some integer k|
|![Unselected](https://stcloudstate.learn.minnstate.edu/d2l/img/0/QuestionCollection.Main.radioUnchecked.svg?v=20.26.2.21973 "Unselected")|Real numbers uniformly distributed over [0,1)|
|![Unselected](https://stcloudstate.learn.minnstate.edu/d2l/img/0/QuestionCollection.Main.radioUnchecked.svg?v=20.26.2.21973 "Unselected")|Multi-digit integers|
|![Unselected](https://stcloudstate.learn.minnstate.edu/d2l/img/0/QuestionCollection.Main.radioUnchecked.svg?v=20.26.2.21973 "Unselected")|Already partially sorted|

|   |   |
|---|---|
|Hide question 5 feedback|   |
|||
|## Feedback<br><br>Counting sort uses element values as indices: C[A[i]]. This requires integers in a known range 0 to k. When k=O(n), counting sort runs in Θ(n) time!<br><br>Correct! Counting sort uses element values as array indices, so they must be non-negative integers in a known range.|   |

|   |   |   |
|---|---|---|
|**Question 6**||1 / 1 point|

What is the running time of counting sort for n elements in the range 0 to k?

Question options:

|   |   |
|---|---|
|![Selected](https://stcloudstate.learn.minnstate.edu/d2l/img/0/QuestionCollection.Main.radioChecked.svg?v=20.26.2.21973 "Selected")|Θ(n + k)|
|![Unselected](https://stcloudstate.learn.minnstate.edu/d2l/img/0/QuestionCollection.Main.radioUnchecked.svg?v=20.26.2.21973 "Unselected")|Θ(n log k)|
|![Unselected](https://stcloudstate.learn.minnstate.edu/d2l/img/0/QuestionCollection.Main.radioUnchecked.svg?v=20.26.2.21973 "Unselected")|Θ(n log n)|
|![Unselected](https://stcloudstate.learn.minnstate.edu/d2l/img/0/QuestionCollection.Main.radioUnchecked.svg?v=20.26.2.21973 "Unselected")|Θ(k)|

|   |   |
|---|---|
|Hide question 6 feedback|   |
|||
|## Feedback<br><br>Counting sort: Θ(k) initialization + Θ(n) counting + Θ(k) sums + Θ(n) placement = Θ(n+k). When k=O(n), this is Θ(n) - linear time!<br><br>Correct! We initialize k buckets (Θ(k)), scan n elements (Θ(n)), compute running sums (Θ(k)), and place elements (Θ(n)). Total: Θ(n+k).|   |

|   |   |   |
|---|---|---|
|**Question 7**||1 / 1 point|

True or False: Counting sort is a stable sorting algorithm.

Question options:

|   |   |
|---|---|
|![Selected](https://stcloudstate.learn.minnstate.edu/d2l/img/0/QuestionCollection.Main.radioChecked.svg?v=20.26.2.21973 "Selected")|True|
|![Unselected](https://stcloudstate.learn.minnstate.edu/d2l/img/0/QuestionCollection.Main.radioUnchecked.svg?v=20.26.2.21973 "Unselected")|False|

|   |   |
|---|---|
|Hide question 7 feedback|   |
|||
|## Feedback<br><br>Counting sort is STABLE because lines 10-12 process elements backwards (for j=n downto 1), ensuring equal elements maintain their input order. Crucial for radix sort!<br><br>Correct! Counting sort processes elements from right to left in the placement step, which preserves the relative order of equal elements.|   |

|   |   |   |
|---|---|---|
|**Question 8**||2 / 2 points|

Which of the following are comparison sorts? (Select all that apply)

Question options:

|   |   |
|---|---|
|![Selected](https://s.brightspace.com/lib/bsi/2026.2.264/images/tier2/check-box.svg "Selected")|Merge sort|
|![Selected](https://s.brightspace.com/lib/bsi/2026.2.264/images/tier2/check-box.svg "Selected")|QuickSort|
|![Selected](https://s.brightspace.com/lib/bsi/2026.2.264/images/tier2/check-box.svg "Selected")|HeapSort|
|![Unselected](https://s.brightspace.com/lib/bsi/2026.2.264/images/tier2/check-box-unchecked.svg "Unselected")|Counting sort|
|![Unselected](https://s.brightspace.com/lib/bsi/2026.2.264/images/tier2/check-box-unchecked.svg "Unselected")|Radix sort|
|![Selected](https://s.brightspace.com/lib/bsi/2026.2.264/images/tier2/check-box.svg "Selected")|Insertion sort|

|   |   |
|---|---|
|Hide question 8 feedback|   |
|||
|## Feedback<br><br>Comparison sorts: merge, quick, heap, insertion. Non-comparison: counting, radix, bucket. The latter beat Ω(n log n) by using operations other than comparisons!<br><br>Correct! Merge sort only uses comparisons to merge sorted subarrays.<br><br>Correct! QuickSort partitions based on comparisons with the pivot.<br><br>Correct! HeapSort uses comparisons to maintain the heap property.<br><br>Correct! Insertion sort compares each element with previously sorted elements.|   |

|   |   |   |
|---|---|---|
|**Question 9**||2 / 2 points|

How do linear-time sorting algorithms (counting, radix, bucket) beat the Ω(n log n) comparison sort lower bound?

Question options:

|   |   |
|---|---|
|![Selected](https://stcloudstate.learn.minnstate.edu/d2l/img/0/QuestionCollection.Main.radioChecked.svg?v=20.26.2.21973 "Selected")|They use operations other than comparisons, such as array indexing and digit extraction|
|![Unselected](https://stcloudstate.learn.minnstate.edu/d2l/img/0/QuestionCollection.Main.radioUnchecked.svg?v=20.26.2.21973 "Unselected")|They use parallel processing to compare multiple elements simultaneously|
|![Unselected](https://stcloudstate.learn.minnstate.edu/d2l/img/0/QuestionCollection.Main.radioUnchecked.svg?v=20.26.2.21973 "Unselected")|They make assumptions that reduce the number of possible permutations below n!|
|![Unselected](https://stcloudstate.learn.minnstate.edu/d2l/img/0/QuestionCollection.Main.radioUnchecked.svg?v=20.26.2.21973 "Unselected")|They violate the lower bound proof, showing the proof is incorrect|

|   |   |
|---|---|
|Hide question 9 feedback|   |
|||
|## Feedback<br><br>The Ω(n log n) lower bound applies ONLY to comparison sorts. Linear-time sorts use array indexing (C[A[i]]), digit extraction, bucket distribution - NOT comparisons!<br><br>Correct! By using element values as array indices or extracting digits, they gain information without comparing pairs of elements.|   |

|   |   |   |
|---|---|---|
|**Question 10**||1 / 1 point|

A decision tree for sorting n elements has at least n! leaves. What is the minimum height h of such a tree? Express your answer using logarithms and factorials.

|   |   |   |
|---|---|---|
|Answer:|log(n!)||

|                                                                                                                                                 |     |
| ----------------------------------------------------------------------------------------------------------------------------------------------- | --- |
| Hide question 10 feedback                                                                                                                       |     |
|                                                                                                                                                 |     |
| ## Feedback<br><br>Binary tree with height h has ≤2^h leaves. Need ≥n! leaves, so 2^h ≥ n!, giving h ≥ log₂(n!). This simplifies to Θ(n log n)! |     |
## quiz 2
|   |   |   |
|---|---|---|
|**Question 1**||2 / 2 points|

In radix sort, why do we sort starting with the LEAST significant digit first (not the most significant)?

Question options:

|   |   |
|---|---|
|![Selected](https://stcloudstate.learn.minnstate.edu/d2l/img/0/QuestionCollection.Main.radioChecked.svg?v=20.26.2.21973 "Selected")|Because the stable sort ensures previously sorted digits remain in correct relative order|
|![Unselected](https://stcloudstate.learn.minnstate.edu/d2l/img/0/QuestionCollection.Main.radioUnchecked.svg?v=20.26.2.21973 "Unselected")|Because it's faster to access the rightmost digit in memory|
|![Unselected](https://stcloudstate.learn.minnstate.edu/d2l/img/0/QuestionCollection.Main.radioUnchecked.svg?v=20.26.2.21973 "Unselected")|Because most numbers differ in their least significant digits|
|![Unselected](https://stcloudstate.learn.minnstate.edu/d2l/img/0/QuestionCollection.Main.radioUnchecked.svg?v=20.26.2.21973 "Unselected")|Because we can't sort by most significant digit first|

|   |   |
|---|---|
|Hide question 1 feedback|   |
|||
|## Feedback<br><br>Radix sort works least-to-most significant BECAUSE of stability. After sorting digit i, elements are sorted by rightmost i digits. Stable sort on digit i+1 preserves this!<br><br>Correct! Starting with least significant digit works BECAUSE we use stable sorting. Later passes preserve the work of earlier passes.|   |

|   |   |   |
|---|---|---|
|**Question 2**||2 / 2 points|

What happens if the digit-sorting algorithm used in radix sort is NOT stable?

Question options:

|   |   |
|---|---|
|![Selected](https://stcloudstate.learn.minnstate.edu/d2l/img/0/QuestionCollection.Main.radioChecked.svg?v=20.26.2.21973 "Selected")|Radix sort produces incorrect results - elements sorted by earlier digits get scrambled|
|![Unselected](https://stcloudstate.learn.minnstate.edu/d2l/img/0/QuestionCollection.Main.radioUnchecked.svg?v=20.26.2.21973 "Unselected")|Radix sort still works but runs slower|
|![Unselected](https://stcloudstate.learn.minnstate.edu/d2l/img/0/QuestionCollection.Main.radioUnchecked.svg?v=20.26.2.21973 "Unselected")|Radix sort works but is no longer in-place|
|![Unselected](https://stcloudstate.learn.minnstate.edu/d2l/img/0/QuestionCollection.Main.radioUnchecked.svg?v=20.26.2.21973 "Unselected")|Radix sort works only for numbers with fewer than 10 digits|

|   |   |
|---|---|
|Hide question 2 feedback|   |
|||
|## Feedback<br><br>Without stability, radix sort FAILS! Example: after sorting by ones digit, we have partial order. Unstable sort on tens digit destroys this order. Result: unsorted!<br><br>Correct! Without stability, later passes destroy the work of earlier passes. The final result is not sorted.|   |

|   |   |   |
|---|---|---|
|**Question 3**||2 / 2 points|

For n numbers with d digits each, where each digit is in range 0 to k-1, and using counting sort as the stable sort, what is radix sort's running time?

Question options:

|   |   |
|---|---|
|![Selected](https://stcloudstate.learn.minnstate.edu/d2l/img/0/QuestionCollection.Main.radioChecked.svg?v=20.26.2.21973 "Selected")|Θ(d(n + k))|
|![Unselected](https://stcloudstate.learn.minnstate.edu/d2l/img/0/QuestionCollection.Main.radioUnchecked.svg?v=20.26.2.21973 "Unselected")|Θ(n + k)|
|![Unselected](https://stcloudstate.learn.minnstate.edu/d2l/img/0/QuestionCollection.Main.radioUnchecked.svg?v=20.26.2.21973 "Unselected")|Θ(d · n log k)|
|![Unselected](https://stcloudstate.learn.minnstate.edu/d2l/img/0/QuestionCollection.Main.radioUnchecked.svg?v=20.26.2.21973 "Unselected")|Θ(n log n)|

|   |   |
|---|---|
|Hide question 3 feedback|   |
|||
|## Feedback<br><br>Radix sort makes d passes. Each pass uses counting sort: Θ(n+k). Total: d × Θ(n+k) = Θ(d(n+k)). When d=O(1) and k=O(n), this is Θ(n)!<br><br>Correct! d passes of counting sort, each taking Θ(n + k) time. Total: Θ(d(n + k)).|   |

|   |   |   |
|---|---|---|
|**Question 4**||2 / 2 points|

When sorting n b-bit integers with radix sort, how should we choose the digit size r to minimize running time?

Question options:

|   |   |
|---|---|
|![Selected](https://stcloudstate.learn.minnstate.edu/d2l/img/0/QuestionCollection.Main.radioChecked.svg?v=20.26.2.21973 "Selected")|Choose r ≈ log n so that 2^r ≈ n, balancing number of passes against work per pass|
|![Unselected](https://stcloudstate.learn.minnstate.edu/d2l/img/0/QuestionCollection.Main.radioUnchecked.svg?v=20.26.2.21973 "Unselected")|Choose r = 1 (binary digits) to minimize the digit range|
|![Unselected](https://stcloudstate.learn.minnstate.edu/d2l/img/0/QuestionCollection.Main.radioUnchecked.svg?v=20.26.2.21973 "Unselected")|Choose r = b (treat entire number as one digit)|
|![Unselected](https://stcloudstate.learn.minnstate.edu/d2l/img/0/QuestionCollection.Main.radioUnchecked.svg?v=20.26.2.21973 "Unselected")|Choose r = b/2 to balance evenly|

|   |   |
|---|---|
|Hide question 4 feedback|   |
|||
|## Feedback<br><br>Optimal: r ≈ log n gives 2^r ≈ n. Then: (b/log n) passes × Θ(n) per pass = Θ(bn/log n). For b=O(log n), this is Θ(n)!<br><br>Correct! With r = log n, we have b/log n passes, each costing Θ(n + n) = Θ(n), for total Θ((b/log n)·n).|   |

|   |   |   |
|---|---|---|
|**Question 5**||1 / 1 point|

Bucket sort assumes input is:

Question options:

|   |   |
|---|---|
|![Selected](https://stcloudstate.learn.minnstate.edu/d2l/img/0/QuestionCollection.Main.radioChecked.svg?v=20.26.2.21973 "Selected")|Uniformly distributed over the interval [0,1)|
|![Unselected](https://stcloudstate.learn.minnstate.edu/d2l/img/0/QuestionCollection.Main.radioUnchecked.svg?v=20.26.2.21973 "Unselected")|Sorted in increasing order|
|![Unselected](https://stcloudstate.learn.minnstate.edu/d2l/img/0/QuestionCollection.Main.radioUnchecked.svg?v=20.26.2.21973 "Unselected")|Integers in a small range 0 to k|
|![Unselected](https://stcloudstate.learn.minnstate.edu/d2l/img/0/QuestionCollection.Main.radioUnchecked.svg?v=20.26.2.21973 "Unselected")|Multi-digit integers|

|   |   |
|---|---|
|Hide question 5 feedback|   |
|||
|## Feedback<br><br>Bucket sort needs UNIFORM distribution over [0,1). This ensures E[elements per bucket] = 1, making insertion sort on each bucket O(1) expected time!<br><br>Correct! With uniform distribution, each bucket gets O(1) expected elements, making sorting each bucket fast.|   |

|   |   |   |
|---|---|---|
|**Question 6**||1 / 1 point|

What is the expected running time of bucket sort on n uniformly distributed inputs?

Question options:

|   |   |
|---|---|
|![Selected](https://stcloudstate.learn.minnstate.edu/d2l/img/0/QuestionCollection.Main.radioChecked.svg?v=20.26.2.21973 "Selected")|Θ(n)|
|![Unselected](https://stcloudstate.learn.minnstate.edu/d2l/img/0/QuestionCollection.Main.radioUnchecked.svg?v=20.26.2.21973 "Unselected")|Θ(n log n)|
|![Unselected](https://stcloudstate.learn.minnstate.edu/d2l/img/0/QuestionCollection.Main.radioUnchecked.svg?v=20.26.2.21973 "Unselected")|Θ(n²)|
|![Unselected](https://stcloudstate.learn.minnstate.edu/d2l/img/0/QuestionCollection.Main.radioUnchecked.svg?v=20.26.2.21973 "Unselected")|O(1)|

|   |   |
|---|---|
|Hide question 6 feedback|   |
|||
|## Feedback<br><br>Expected time Θ(n): distribute n elements in Θ(n), n buckets each with E[1] element sorted in E[O(1)], concatenate in Θ(n). Total: Θ(n)!<br><br>Correct! Expected linear time: Θ(n) to distribute + E[Θ(1)] per bucket × n buckets = Θ(n).|   |

|   |   |   |
|---|---|---|
|**Question 7**||1 / 1 point|

True or False: Bucket sort has Θ(n²) worst-case time when all elements land in a single bucket.

Question options:

|   |   |
|---|---|
|![Selected](https://stcloudstate.learn.minnstate.edu/d2l/img/0/QuestionCollection.Main.radioChecked.svg?v=20.26.2.21973 "Selected")|True|
|![Unselected](https://stcloudstate.learn.minnstate.edu/d2l/img/0/QuestionCollection.Main.radioUnchecked.svg?v=20.26.2.21973 "Unselected")|False|

|   |   |
|---|---|
|Hide question 7 feedback|   |
|||
|## Feedback<br><br>Worst case Θ(n²): if input is adversarial (all in [0, 0.1)), all n elements land in bucket 0. Insertion sort takes Θ(n²). Hence we analyze EXPECTED time!<br><br>Correct! If all n elements go to one bucket, insertion sort on that bucket takes Θ(n²) time. This happens with non-uniform distributions.|   |

|   |   |   |
|---|---|---|
|**Question 8**||2 / 2 points|

Match each input type to the most appropriate linear-time sorting algorithm: (Select all correct pairings)

Question options:

|   |   |
|---|---|
|![Selected](https://s.brightspace.com/lib/bsi/2026.2.264/images/tier2/check-box.svg "Selected")|Integers in range 0-100: use Counting Sort|
|![Selected](https://s.brightspace.com/lib/bsi/2026.2.264/images/tier2/check-box.svg "Selected")|32-bit integers: use Radix Sort|
|![Selected](https://s.brightspace.com/lib/bsi/2026.2.264/images/tier2/check-box.svg "Selected")|Random real numbers in [0,1): use Bucket Sort|
|![Unselected](https://s.brightspace.com/lib/bsi/2026.2.264/images/tier2/check-box-unchecked.svg "Unselected")|Unknown integer distribution: use Counting Sort|
|![Unselected](https://s.brightspace.com/lib/bsi/2026.2.264/images/tier2/check-box-unchecked.svg "Unselected")|Integers 0 to n³: use Counting Sort|
|![Selected](https://s.brightspace.com/lib/bsi/2026.2.264/images/tier2/check-box.svg "Selected")|Employee records by age (0-120): use Counting Sort|

|   |   |
|---|---|
|Hide question 8 feedback|   |
|||
|## Feedback<br><br>Counting: small k. Radix: fixed bits or digits. Bucket: uniform distribution in [0,1). Choose based on input properties!<br><br>Correct! Small range (k=100) makes counting sort perfect: Θ(n + 100) = Θ(n).<br><br>Correct! Fixed number of bits (b=32) means radix sort with r=log n gives Θ(n) time.<br><br>Correct! Uniform distribution over [0,1) is exactly what bucket sort needs for Θ(n) expected time.<br><br>Correct! Small range (k=120) makes counting sort efficient: Θ(n + 120) = Θ(n).|   |

|   |   |   |
|---|---|---|
|**Question 9**||1 / 1 point|

What is the space complexity of counting sort (beyond the input array)?

Question options:

|   |   |
|---|---|
|![Selected](https://stcloudstate.learn.minnstate.edu/d2l/img/0/QuestionCollection.Main.radioChecked.svg?v=20.26.2.21973 "Selected")|Θ(n + k) for the output array B[1..n] and count array C[0..k]|
|![Unselected](https://stcloudstate.learn.minnstate.edu/d2l/img/0/QuestionCollection.Main.radioUnchecked.svg?v=20.26.2.21973 "Unselected")|Θ(1) because it sorts in place|
|![Unselected](https://stcloudstate.learn.minnstate.edu/d2l/img/0/QuestionCollection.Main.radioUnchecked.svg?v=20.26.2.21973 "Unselected")|Θ(n log n)|
|![Unselected](https://stcloudstate.learn.minnstate.edu/d2l/img/0/QuestionCollection.Main.radioUnchecked.svg?v=20.26.2.21973 "Unselected")|Θ(k) only for the count array|

|   |   |
|---|---|
|Hide question 9 feedback|   |
|||
|## Feedback<br><br>Counting sort needs: C[0..k] for counts (Θ(k)), B[1..n] for output (Θ(n)). Total space: Θ(n+k). NOT in-place!<br><br>Correct! We need B[1..n] to store sorted output (Θ(n)) and C[0..k] to count elements (Θ(k)). Total: Θ(n+k).|   |

|   |   |   |
|---|---|---|
|**Question 10**||2 / 2 points|

Radix sort runs in Θ(n) time when sorting n b-bit integers, provided b = O(?). Fill in the blank with the tightest bound.

|   |   |   |
|---|---|---|
|Answer:|log n||

|                                                                                                                                                             |     |
| ----------------------------------------------------------------------------------------------------------------------------------------------------------- | --- |
| Hide question 10 feedback                                                                                                                                   |     |
|                                                                                                                                                             |     |
| ## Feedback<br><br>With r = log n, radix sort time = Θ((b/log n)·n). This is Θ(n) when b/log n = O(1), i.e., b = O(log n). Examples: log n bits per number! |     |

## quiz 3
|   |   |   |
|---|---|---|
|**Question 1**||2 / 2 points|

You need to sort 50,000 student exam scores (0-100) for a grade report due in 5 minutes. Your computer is slow. Which algorithm saves your job?

|   |   |
|---|---|
|![Selected](https://stcloudstate.learn.minnstate.edu/d2l/img/0/QuestionCollection.Main.radioChecked.svg?v=20.26.2.21973 "Selected")|Counting sort - Θ(n + k) = Θ(50,000 + 100) = Θ(50,000) operations|
|![Unselected](https://stcloudstate.learn.minnstate.edu/d2l/img/0/QuestionCollection.Main.radioUnchecked.svg?v=20.26.2.21973 "Unselected")|QuickSort - expected Θ(n log n) ≈ 800,000 operations|
|![Unselected](https://stcloudstate.learn.minnstate.edu/d2l/img/0/QuestionCollection.Main.radioUnchecked.svg?v=20.26.2.21973 "Unselected")|Insertion sort - it's simple and easy to implement|
|![Unselected](https://stcloudstate.learn.minnstate.edu/d2l/img/0/QuestionCollection.Main.radioUnchecked.svg?v=20.26.2.21973 "Unselected")|Bucket sort - students are uniformly distributed|

|   |   |
|---|---|
|Hide question 1 feedback|   |
|||
|## Feedback<br><br>Counting sort wins! Small range (0-100) means Θ(50,000+100) ≈ 50,100 operations vs quicksort's ~800,000. Time to celebrate, not panic!<br><br>Correct! Small range (k=100) makes counting sort MUCH faster than comparison sorts. Linear time saves the day!|   |

|   |   |   |
|---|---|---|
|**Question 2**||2 / 2 points|

A government database needs to sort 300 million Social Security Numbers (9-digit integers). Which algorithm should they use?

|   |   |
|---|---|
|![Selected](https://stcloudstate.learn.minnstate.edu/d2l/img/0/QuestionCollection.Main.radioChecked.svg?v=20.26.2.21973 "Selected")|Radix sort with 9 passes (one per digit), using counting sort for each digit|
|![Unselected](https://stcloudstate.learn.minnstate.edu/d2l/img/0/QuestionCollection.Main.radioUnchecked.svg?v=20.26.2.21973 "Unselected")|Counting sort with k = 999,999,999|
|![Unselected](https://stcloudstate.learn.minnstate.edu/d2l/img/0/QuestionCollection.Main.radioUnchecked.svg?v=20.26.2.21973 "Unselected")|Bucket sort assuming SSNs are uniformly distributed|
|![Unselected](https://stcloudstate.learn.minnstate.edu/d2l/img/0/QuestionCollection.Main.radioUnchecked.svg?v=20.26.2.21973 "Unselected")|QuickSort - it's the industry standard|

|   |   |
|---|---|
|Hide question 2 feedback|   |
|||
|## Feedback<br><br>Radix sort shines here! 9 passes × Θ(300M + 10) ≈ 2.7 billion operations. Compare quicksort: ~300M × log(300M) ≈ 8.5 billion. Radix wins!<br><br>Correct! 9 digits, each 0-9. Time: Θ(9(n+10)) = Θ(9n) = Θ(n). Perfect for fixed-length numbers!|   |

|   |   |   |
|---|---|---|
|**Question 3**||2 / 2 points|

You generated 1 million random floating-point numbers in [0,1) using Math.random(). Which sort would a statistician use to verify they're truly uniform?

|   |   |
|---|---|
|![Selected](https://stcloudstate.learn.minnstate.edu/d2l/img/0/QuestionCollection.Main.radioChecked.svg?v=20.26.2.21973 "Selected")|Bucket sort - if uniform, each bucket should have ~1000 elements (1M/1000 buckets)|
|![Unselected](https://stcloudstate.learn.minnstate.edu/d2l/img/0/QuestionCollection.Main.radioUnchecked.svg?v=20.26.2.21973 "Unselected")|Counting sort - random numbers are integers|
|![Unselected](https://stcloudstate.learn.minnstate.edu/d2l/img/0/QuestionCollection.Main.radioUnchecked.svg?v=20.26.2.21973 "Unselected")|Radix sort - random numbers are multi-digit|
|![Unselected](https://stcloudstate.learn.minnstate.edu/d2l/img/0/QuestionCollection.Main.radioUnchecked.svg?v=20.26.2.21973 "Unselected")|QuickSort - randomness helps performance|

|   |   |
|---|---|
|Hide question 3 feedback|   |
|||
|## Feedback<br><br>Bucket sort does double duty: sorts in Θ(n) AND tests uniformity! If distribution is bad, buckets will be unbalanced - you'll detect it immediately!<br><br>Correct! Bucket sort IS the uniformity test! If buckets are uneven, the generator is biased. Plus, it sorts in Θ(n) expected time.|   |

|   |   |   |
|---|---|---|
|**Question 4**||1.667 / 2 points|

You're on a game show! Match each scenario to WIN. Which statements are TRUE? (Select all correct)

|   |   |
|---|---|
|![Correct Answer](https://stcloudstate.learn.minnstate.edu/d2l/img/0/QuestionCollection.Main.infRightAnswer.gif?v=20.26.2.21973 "Correct Answer")![Incorrect Response](https://stcloudstate.learn.minnstate.edu/d2l/img/0/Shared.Main.infIncorrect.gif?v=20.26.2.21973 "Incorrect Response")![Unselected](https://s.brightspace.com/lib/bsi/2026.2.264/images/tier2/check-box-unchecked.svg "Unselected")|Sorting 1000 employee IDs (6-digit numbers): Radix sort beats QuickSort|
|![Unselected](https://s.brightspace.com/lib/bsi/2026.2.264/images/tier2/check-box-unchecked.svg "Unselected")|Sorting arbitrary strings: Counting sort is fastest|
|![Correct Answer](https://stcloudstate.learn.minnstate.edu/d2l/img/0/QuestionCollection.Main.infRightAnswer.gif?v=20.26.2.21973 "Correct Answer")![Selected](https://s.brightspace.com/lib/bsi/2026.2.264/images/tier2/check-box.svg "Selected")|Sorting 100 test scores (0-100): Counting sort beats HeapSort|
|![Correct Answer](https://stcloudstate.learn.minnstate.edu/d2l/img/0/QuestionCollection.Main.infRightAnswer.gif?v=20.26.2.21973 "Correct Answer")![Selected](https://s.brightspace.com/lib/bsi/2026.2.264/images/tier2/check-box.svg "Selected")|Sorting uniformly random reals in [0,1): Bucket sort beats MergeSort|
|![Unselected](https://s.brightspace.com/lib/bsi/2026.2.264/images/tier2/check-box-unchecked.svg "Unselected")|Sorting unknown data: Radix sort is safest choice|
|![Correct Answer](https://stcloudstate.learn.minnstate.edu/d2l/img/0/QuestionCollection.Main.infRightAnswer.gif?v=20.26.2.21973 "Correct Answer")![Selected](https://s.brightspace.com/lib/bsi/2026.2.264/images/tier2/check-box.svg "Selected")|Sorting birthdates (365 possible values): Counting sort is excellent|

|   |   |
|---|---|
|Hide question 4 feedback|   |
|||
|## Feedback<br><br>Key insight: Linear-time sorts dominate when their assumptions hold (small range, fixed bits, uniform distribution). Otherwise, comparison sorts are safer!<br><br>Correct! Θ(100+100)=Θ(200) counting vs Θ(100 log 100)≈664 heap operations. Counting wins!<br><br>Correct! Θ(n) expected bucket vs Θ(n log n) merge. Bucket wins with uniform distribution!<br><br>Correct! k=365, so Θ(n+365)=Θ(n) for large n. Perfect for counting sort!|   |

|   |   |   |
|---|---|---|
|**Question 5**||2 / 2 points|

An old 1960s card-sorting machine sorts punch cards by processing one column at a time. Starting with rightmost column, it's implementing:

|   |   |
|---|---|
|![Selected](https://stcloudstate.learn.minnstate.edu/d2l/img/0/QuestionCollection.Main.radioChecked.svg?v=20.26.2.21973 "Selected")|Radix sort! Processing least-significant column first with stable sorting|
|![Unselected](https://stcloudstate.learn.minnstate.edu/d2l/img/0/QuestionCollection.Main.radioUnchecked.svg?v=20.26.2.21973 "Unselected")|Counting sort - each column has only 12 possible holes|
|![Unselected](https://stcloudstate.learn.minnstate.edu/d2l/img/0/QuestionCollection.Main.radioUnchecked.svg?v=20.26.2.21973 "Unselected")|Bucket sort - cards are distributed into bins|
|![Unselected](https://stcloudstate.learn.minnstate.edu/d2l/img/0/QuestionCollection.Main.radioUnchecked.svg?v=20.26.2.21973 "Unselected")|MergeSort adapted for cards|

|   |   |
|---|---|
|Hide question 5 feedback|   |
|||
|## Feedback<br><br>This is radix sort's origin story! 1960s card sorters processed rightmost column first, maintained order (stability), repeated left. Pure radix sort!<br><br>Correct! This is EXACTLY how radix sort was originally implemented on real card-sorting machines! History in action!|   |

|   |   |   |
|---|---|---|
|**Question 6**||2 / 2 points|

A student argues: 'The Ω(n log n) lower bound is wrong because counting sort is Θ(n)!' What's the flaw in their reasoning?

|   |   |
|---|---|
|![Selected](https://stcloudstate.learn.minnstate.edu/d2l/img/0/QuestionCollection.Main.radioChecked.svg?v=20.26.2.21973 "Selected")|The lower bound applies only to comparison sorts; counting sort uses array indexing, not comparisons|
|![Unselected](https://stcloudstate.learn.minnstate.edu/d2l/img/0/QuestionCollection.Main.radioUnchecked.svg?v=20.26.2.21973 "Unselected")|Counting sort is actually Θ(n log n) when k is large|
|![Unselected](https://stcloudstate.learn.minnstate.edu/d2l/img/0/QuestionCollection.Main.radioUnchecked.svg?v=20.26.2.21973 "Unselected")|The lower bound is indeed wrong and should be updated|
|![Unselected](https://stcloudstate.learn.minnstate.edu/d2l/img/0/QuestionCollection.Main.radioUnchecked.svg?v=20.26.2.21973 "Unselected")|Counting sort only works for small inputs, so the bound still holds|

|   |   |
|---|---|
|Hide question 6 feedback|   |
|||
|## Feedback<br><br>The Ω(n log n) bound has a condition: 'for comparison sorts.' Counting sort escapes by using C[value] indexing instead of comparing elements. Different game, different rules!<br><br>Correct! Lower bound proof assumes ONLY comparisons provide information. Counting sort 'cheats' by using indices!|   |

|   |   |   |
|---|---|---|
|**Question 7**||2 / 2 points|

Your boss says: 'Use HeapSort - it's Θ(n log n) and O(1) space. Counting sort uses too much memory!' When is your boss WRONG?

|   |   |
|---|---|
|![Selected](https://stcloudstate.learn.minnstate.edu/d2l/img/0/QuestionCollection.Main.radioChecked.svg?v=20.26.2.21973 "Selected")|When k = O(n) - counting sort uses Θ(n) space but is FASTER: Θ(n) time vs Θ(n log n)|
|![Unselected](https://stcloudstate.learn.minnstate.edu/d2l/img/0/QuestionCollection.Main.radioUnchecked.svg?v=20.26.2.21973 "Unselected")|Never - HeapSort's O(1) space always beats counting sort's Θ(n+k) space|
|![Unselected](https://stcloudstate.learn.minnstate.edu/d2l/img/0/QuestionCollection.Main.radioUnchecked.svg?v=20.26.2.21973 "Unselected")|When k > n - counting sort becomes more space-efficient|
|![Unselected](https://stcloudstate.learn.minnstate.edu/d2l/img/0/QuestionCollection.Main.radioUnchecked.svg?v=20.26.2.21973 "Unselected")|HeapSort is always the better choice for production systems|

|   |   |
|---|---|
|Hide question 7 feedback|   |
|||
|## Feedback<br><br>When k=O(n): counting sort uses Θ(2n) space vs HeapSort's O(1), BUT saves time: Θ(n) vs Θ(n log n). For n=1M, that's 1M vs 20M operations. Worth it!<br><br>Correct! When k=O(n), counting sort uses comparable space but runs asymptotically faster. Worth the memory!|   |

|   |   |   |
|---|---|---|
|**Question 8**||2 / 2 points|

You're a sorting consultant. Match each dataset to the BEST algorithm:

|   |   |   |
|---|---|---|
|\|   \|   \|   \|   \|<br>\|---\|---\|---\|---\|<br>\|__4__\|QuickSort (safe general-purpose)\|<br>\|__3__\|Counting sort (tiny range k=5)\|<br>\|__1__\|Radix sort (fixed digits, fast)\|<br>\|__2__\|Bucket sort (uniform in [0,1))\|||\|   \|   \|<br>\|---\|---\|<br>\|**1**.\|10M phone numbers (10 digits each)\|<br>\|**2**.\|1M random doubles from Math.random()\|<br>\|**3**.\|5000 product ratings (1-5 stars)\|<br>\|**4**.\|Unknown data from user upload\||

|   |   |
|---|---|
|Hide question 8 feedback|   |
|||
|## Feedback<br><br>Radix for fixed-length integers, bucket for uniform reals, counting for small ranges, comparison sorts when assumptions don't hold!|   |

|   |   |   |
|---|---|---|
|**Question 9**||2 / 2 points|

You're sorting employee records by salary using radix sort, then by hire date using counting sort. Why is stability crucial?

|   |   |
|---|---|
|![Selected](https://stcloudstate.learn.minnstate.edu/d2l/img/0/QuestionCollection.Main.radioChecked.svg?v=20.26.2.21973 "Selected")|Without stability, the salary ordering is destroyed when sorting by hire date - you lose the multi-level sort|
|![Unselected](https://stcloudstate.learn.minnstate.edu/d2l/img/0/QuestionCollection.Main.radioUnchecked.svg?v=20.26.2.21973 "Unselected")|Stability makes the algorithms run faster|
|![Unselected](https://stcloudstate.learn.minnstate.edu/d2l/img/0/QuestionCollection.Main.radioUnchecked.svg?v=20.26.2.21973 "Unselected")|Unstable sorts might crash with employee records|
|![Unselected](https://stcloudstate.learn.minnstate.edu/d2l/img/0/QuestionCollection.Main.radioUnchecked.svg?v=20.26.2.21973 "Unselected")|The algorithms won't work at all without stability|

|   |   |
|---|---|
|Hide question 9 feedback|   |
|||
|## Feedback<br><br>Multi-key sort trick: sort by least important key first (hire date), then more important (salary). Stability preserves date-order within same-salary groups. Magic!<br><br>Correct! Stable sorts preserve previous orderings when values tie. This enables multi-key sorting: sort by secondary key, then primary key!|   |

|   |   |   |
|---|---|---|
|**Question 10**||3 / 3 points|

Sort 1 billion 64-bit integers. Available RAM: 8GB. Counting sort needs 2^64 buckets (18 exabytes!). What's your move?

|   |   |
|---|---|
|![Selected](https://stcloudstate.learn.minnstate.edu/d2l/img/0/QuestionCollection.Main.radioChecked.svg?v=20.26.2.21973 "Selected")|Radix sort with digit size r=log₂(1B)≈30 bits, requiring ~3 passes with manageable bucket arrays|
|![Unselected](https://stcloudstate.learn.minnstate.edu/d2l/img/0/QuestionCollection.Main.radioUnchecked.svg?v=20.26.2.21973 "Unselected")|Use counting sort anyway - it's fastest|
|![Unselected](https://stcloudstate.learn.minnstate.edu/d2l/img/0/QuestionCollection.Main.radioUnchecked.svg?v=20.26.2.21973 "Unselected")|Give up on linear time and use QuickSort|
|![Unselected](https://stcloudstate.learn.minnstate.edu/d2l/img/0/QuestionCollection.Main.radioUnchecked.svg?v=20.26.2.21973 "Unselected")|Use bucket sort with 1 billion buckets|

|                                                                                                                                                                                                                                                                                                                  |     |
| ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | --- |
| Hide question 10 feedback                                                                                                                                                                                                                                                                                        |     |
|                                                                                                                                                                                                                                                                                                                  |     |
| ## Feedback<br><br>Radix sort saves the day! Choose r=30: 64-bit numbers = 3 base-2³⁰ digits. Each pass needs 2³⁰ buckets (4GB). Total: 3 passes × 4GB = 12GB peak. Close but doable!<br><br>Correct! Treat as base-2³⁰ numbers: 64/30≈3 digits, k=2³⁰≈1B buckets. Θ(3(n+n))=Θ(n) time, Θ(n) space. Fits in RAM! |     |
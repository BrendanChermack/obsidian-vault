Assignments, quizzes, and activities: 45%  
Mid-term Exam: 30%  
Final Exam: 25%

**Week 1**
- What is an algorithm?
	- Well defined computational procedure that takes some values or sets of values as input and produces some value or sets of values as output.
	- ![[Pasted image 20260126141856.png]]
	- input - 0 or more
	- output - at least 1 output
	- definite - clear, cant have imaginary numbers
	- Finitness - duration must be finite and return a value in a reasonable amount of time
	- effectiveness - must make a difference, serve some purpose have a result
- Analyze an algorithm
	- time
	- space
	- data transfer
	- power - battery constraint devices
	- cpu registers
- ![[Pasted image 20260126142229.png]]
- Insertion sort
	- ![[Pasted image 20260126142412.png]]
	- ![[Pasted image 20260126142429.png]]
	- ![[Pasted image 20260126142459.png]]
	- ![[Pasted image 20260126142649.png]]
	- ![[Pasted image 20260126143031.png]]
	- ![[Pasted image 20260126143045.png]]
	- ![[Pasted image 20260126143410.png]]
	- ![[Pasted image 20260126143440.png]]
**Week 2**
- Merge sort
	- hypothetically - O(nlogn)
	- better than insertion sort as size increases
	- divide and conquer algo
	- large amounts of data
	- ![[Pasted image 20260126143916.png]]
	- ![[Pasted image 20260126143929.png]]
	- steps
		- if n < 2 then the array is sorted already
		- otherwise n>1 and we perform the following 3 steps
		1. Sort the left half of the array using mergeSort
		2. Sort the right half of the array using mergeSort
		3. Merge the sorted left and right halves
	 - ![[Pasted image 20260126144122.png]]
	 - ![[Pasted image 20260126144149.png]]
	 - ![[Pasted image 20260126144210.png]]
	 - ![[Pasted image 20260126144244.png]]
	 - ![[Pasted image 20260126144304.png]]
	 - ![[Pasted image 20260126144319.png]]
	 - conclusions
		 - O(nlogn) grows more slowly than O(n^2)
		 - merge sort asymptotically beats insertion sort in the worst case
		 - in practice, merge sort beats insertion sort for n > 30 or so
 - Characterizing runtimes
	 - O notation
		 - O notation characterizes an upper bound on the asymptotic behavior of a function
			 - it says that a function grows no faster than a certain rate
			 - rate is based on the highest order term
		 - for example:
			 - f(n) = 7n^3 + 100n^2 - 20n + 6 is O(n^3) since the highest order term is 7n^3 and therefore the function grows no faster than n^3
			 - the function f(n) is also O(n^5), O(n^6) and O(n^c) for any constant c ≥ 3
	 - Omega notion 
		 - characterizes a lower bound on the asymptotic behavior of a function
		 - for example 
			 -  f(n) = 7n^3 + 100n^2 - 20n + 6 is Omega(n^3) since the highest order term n^3 grows atleast as fast as n^3
			 - the function f(n) is also Omega(n^2), Omega(n) and Omega(nc) for any constant c ≤ 3
	 - Theta Notion
		 - Theta notion characterizes a tight bound on the asymptotic behavior of a function
			 - a function grows precisely at a certain rate, again based on the highest order term
			 - if a function is both O(f(n)) and Omega(f(n)) then Theta(f(n))
	 - Insertion sort (a, n)
	 - ```
	   For i = 2 to n
		   Key = A[i]
		   //insert A[i] into the sorted subarray A[1:i-1]
		   j = i - 1
		   While j > 0 and A[j] > key
			   A[j+1] = A[j]
			   J = j - 1
		   A[j + 1] = key
	   ```
	   - first how that insertion sort runs in O(n^2) time, regardless of the input
		   - the outer for loop runs n-1 times regardless of the values being sorted
		   - the inner while loop iterates at most i-1 times
		   - the exact number of iterations the while loop makes depends on the values it iterates over but it will definitely iterate between o and i-1 times
		   - since i is at most n, the total number of iterations of the inner loop is at mosr (n-1)(n-1) which is less than n^2 
	   - Each inner loop iteration takes constant time, for a total of at mosr cn^2 for some constant c or O(n^2)
	   - ![[Pasted image 20260126152226.png]]
	   - ![[Pasted image 20260126152241.png]]
	   - ![[Pasted image 20260126152255.png]]
	   - ![[Pasted image 20260126152306.png]]
	   - ![[Pasted image 20260126152322.png]]
	   - ![[Pasted image 20260126152332.png]]
	   - ![[Pasted image 20260126152345.png]]
	   - ![[Pasted image 20260126152356.png]]
	   - ![[Pasted image 20260126152414.png]]
	   - ![[Pasted image 20260126152426.png]]
	   - ![[Pasted image 20260126152439.png]]
	   - ![[Pasted image 20260126152455.png]]
	   - ![[Pasted image 20260126152509.png]]
	   - ![[Pasted image 20260126152522.png]]
**Week 3**
- Divide and conquer paradigm
	- divide the problem into one or more subproblem that are smaller instances of the same problem
	- conquer the subproblems by solving them recursively
		- base case: if the subproblems are small enough, just solve them by brute force
	- combine the subproblem solutions to form a solution to the original problem
	- use a recurrence to characterize the running time of a divide and conquer algo
	- solve the recurrence gives us the asymptotic running time
	- a recurrence is a function is defined in terms of
		- one or more bases cases, and
		- itself with smaller arguments
- Algo Recurrences
	- interested in recurrences that describe running times of algos
	- a recurrence T(n) is algorithmic if for every sufficently large threshold constan n0 > 0:
		- For all n < n0, T(n) = Theta(1) [can consider the running time constant for small problem sizes]
		- for all n>n0, every path of recursion terminates in a defined base case within a finite number of recursive invocations
- Conventions
	- we often don't include the bases case in algorithmic recurrences 
	- admit Ceiling and floor because they don't change the asymptotic solution
	- some recurrences are inequalities rather than equatons
		- ![[Pasted image 20260126160813.png]]
- ![[Pasted image 20260126160833.png]]
- Substitution method
	- Guess the solution, then use induction to prove that it's correct
	- steps:
	1. Guess the solution
	2. Use induction to find the constants and show that the solution works
	- Example
		- determine an asymptotic upper bound on T(n)=2T(n//2) + Theta(n) floor function ensures that T(n) is defined over ints
		- Guess: T(n) = O(nlogn)
		- Inductive step:
			- Assume that T(n) ≤ cnLogN for all numbers ≥ n0  and < n. If n≥ 2n0, holds for n//2 => T(n//2) ≤ cn//2logn//2 substitute into the recurrences
			- ![[Pasted image 20260126161253.png]]
			- ![[Pasted image 20260126161311.png]]
- Making a good guess
	- no general way to
	- T(n) = 2T(n/2) + Theta(n) we know is merge sort with dividing it in half is is reasonable to guess O(nlogn)
	- draw a recursion tree to see the pattern
		- why?
			- visualize the structure and generate a good guess
		- 


- Recursion tree
	- finding the height
		- height is log_b(n)
		- b is what youre dividing by
		- ex
			- T(n) = 4T(n/2) + cn
				- You're dividing by **2** (see the n/2?)
				- So b = 2
				- Height = log₂(n) = **lg n**
		- quick rules
			- Look at T(n/**b**) in your recurrence:
			- If it's T(n/**2**) → height is **lg n**
			- If it's T(n/**3**) → height is **log₃ n**
			- If it's T(n/**4**) → height is **log₄ n**
	- Quick way to tell about a tree's balance
		- when a equation has multiple *n/ * if they are different they are probably unbalanced 
		- **Balanced:** Both divide by the same amount
			- T(n) = 2T(n/2) + ... → **Balanced** (both n/2)
			- T(n) = 4T(n/2) + ... → **Balanced** (both n/2)
		- **Unbalanced:** They divide differently
			- T(n) = T(n/3) + T(2n/3) + ... → **Unbalanced** (n/3 vs 2n/3)
			- T(n) = T(n/4) + T(n/2) + ... → **Unbalanced** (n/4 vs n/2)
	- 
- ![[Pasted image 20260126174530.png]]
- In recursive matrix multiplication it has many more leaves so it doesn't improve efficiency from n^3 we need to reduce the bushiness - make there less recusive calls
- Use Strassen's algorithm
	- perform 7 recursive multiplications rather than 8
	- less multiplications but more additions
	- ![[Pasted image 20260126174905.png]]
	- ![[Pasted image 20260126174923.png]]
	- ![[Pasted image 20260126174941.png]]
	- ![[Pasted image 20260126175000.png]]
	- ![[Pasted image 20260126175040.png]]
- # Master Method: Complete Guide in Nested Bullet Format

## **Master Method Overview**

- **What is it?**
    - A formula for solving divide-and-conquer recurrences
    - Provides a quick way to get asymptotic solutions
    - Alternative to recursion trees and substitution method
- **Required Form**
    - Must be: **T(n) = aT(n/b) + f(n)**
        - **a ≥ 1**: number of recursive subproblems
        - **b > 1**: factor by which problem size is reduced
        - **f(n)**: cost of work done outside the recursive calls (the "driving function")
        - Both a and b must be **constants**
        - All subproblems must be the **same size** (n/b)
- **When Master Method DOESN'T Apply**
    - Subproblems have different sizes
        - Example: T(n) = T(n/3) + T(2n/3) + n
        - Different sizes: n/3 vs 2n/3 ❌
    - Not dividing by a constant
        - Example: T(n) = T(n-1) + n
        - Subtracting, not dividing ❌
    - Driving function not polynomially bounded
        - Example: T(n) = 2T(n/2) + n/lg n
        - Falls in a "gap" between cases ❌
    - Coefficients aren't constants
        - Example: T(n) = nT(n/2) + n
        - 'a' varies with n ❌

---

## **The Watershed Function: n^(log_b a)**

- **What is it?**
    - The critical comparison point
    - Represents the **cost of the leaves** in the recursion tree
    - Formula: **n^(log_b a)**
- **How to Calculate**
    - Given: T(n) = aT(n/b) + f(n)
    - Find: log_b(a)
        - "What power do I raise b to get a?"
    - Result: n^(log_b a)
- **Examples**
    - T(n) = 8T(n/2) + n²
        - a = 8, b = 2
        - log₂(8) = 3 (because 2³ = 8)
        - Watershed: n³
    - T(n) = 9T(n/3) + n²
        - a = 9, b = 3
        - log₃(9) = 2 (because 3² = 9)
        - Watershed: n²
    - T(n) = 7T(n/2) + n²
        - a = 7, b = 2
        - log₂(7) ≈ 2.807
        - Watershed: n^2.807
- **Why It Matters**
    - Determines which case of the Master Method applies
    - Compare f(n) with n^(log_b a) to find your case
    - Tells you whether leaves, root, or all levels dominate

---

## **Case 1: Leaves Dominate**

- **Intuition**
    - The driving function f(n) is **much smaller** than the watershed
    - Most work happens at the **leaves** of the recursion tree
    - The recursive calls dominate the total cost
- **Formal Condition**
    - f(n) = O(n^(log_b a - ε)) for some constant **ε > 0**
        - "f(n) is **polynomially smaller** than n^(log_b a)"
        - Not just smaller by a constant factor
        - Smaller by a whole polynomial degree (n^ε)
        - The ε ensures there's a gap
- **Solution**
    - **T(n) = Θ(n^(log_b a))**
    - The watershed function dominates
    - f(n) is ignored in the final answer
- **How to Check**
    - Calculate n^(log_b a)
    - Compare with f(n)
    - Ask: "Is f(n) polynomially smaller?"
        - If f(n) = n and watershed = n², then YES (ε = 1)
        - If f(n) = n² and watershed = n³, then YES (ε = 1)
        - If f(n) = n/lg n and watershed = n, then NO (only log factor)
- **Examples**
    - **Example 1: T(n) = 8T(n/2) + Θ(n²)**
        - a = 8, b = 2, f(n) = n²
        - Watershed: n^(log₂ 8) = n³
        - Compare: n² vs n³
        - Is n² = O(n^(3-ε))? Yes, with ε = 1
        - n² is polynomially smaller ✓
        - **Solution: T(n) = Θ(n³)**
        - Visual: Leaves do n³ work, root only n², leaves win
    - **Example 2: T(n) = 8T(n/4) + Θ(n)**
        - a = 8, b = 4, f(n) = n
        - Watershed: n^(log₄ 8) = n^1.5
        - Compare: n vs n^1.5
        - Is n = O(n^(1.5-ε))? Yes, with ε = 0.5
        - **Solution: T(n) = Θ(n^1.5)**
    - **Example 3: Matrix Multiplication T(n) = 8T(n/2) + Θ(1)**
        - a = 8, b = 2, f(n) = 1
        - Watershed: n³
        - Compare: 1 vs n³
        - Constant vs cubic → polynomially smaller
        - **Solution: T(n) = Θ(n³)**
        - This is why standard matrix multiplication is O(n³)
- **Tree Visualization for Case 1**

```
  Root:    f(n) = small cost
  Level 1: Slightly more nodes
  Level 2: Even more nodes
  ...
  Leaves:  MANY nodes, huge total cost ← DOMINATES
```

- Cost increases as you go down
- Leaves contribute most to total
- Geometric series with ratio > 1

---

## **Case 2: All Levels Balanced**

- **Intuition**
    - The driving function f(n) **equals** the watershed (possibly times logarithmic factors)
    - Work is **evenly distributed** across all levels
    - Every level contributes the same amount
    - Must multiply by the number of levels
- **Formal Condition**
    - f(n) = Θ(n^(log_b a) · lg^k n) for some constant **k ≥ 0**
        - "f(n) equals the watershed times some power of log"
        - k can be 0, 1, 2, 3, ...
        - k = 0 is the most common case (no log factor)
- **Solution**
    - **T(n) = Θ(n^(log_b a) · lg^(k+1) n)**
    - Add one more logarithmic factor
    - If k = 0: solution has lg n
    - If k = 3: solution has lg⁴ n
- **How to Check**
    - Calculate n^(log_b a)
    - Check if f(n) equals this (times logarithmic factors)
    - Count logarithmic factors to find k
    - Apply formula with k+1
- **Examples**
    - **Example 1: Merge Sort T(n) = 2T(n/2) + Θ(n)**
        - a = 2, b = 2, f(n) = n
        - Watershed: n^(log₂ 2) = n¹ = n
        - Compare: n vs n
        - They're equal! ✓
        - f(n) = n = Θ(n · lg⁰ n), so k = 0
        - **Solution: T(n) = Θ(n · lg^(0+1) n) = Θ(n lg n)**
        - This is why merge sort is O(n lg n)
        - Tree visualization:

```
      Level 0: n work
      Level 1: n work (2 × n/2)
      Level 2: n work (4 × n/4)
      ...
      lg n levels × n work per level = n lg n
```

- **Example 2: Binary Search T(n) = T(n/2) + Θ(1)**
    - a = 1, b = 2, f(n) = 1
    - Watershed: n^(log₂ 1) = n⁰ = 1
    - Compare: 1 vs 1
    - Equal! f(n) = Θ(1 · lg⁰ n), so k = 0
    - **Solution: T(n) = Θ(1 · lg¹ n) = Θ(lg n)**
    - Each level does constant work, lg n levels
- **Example 3: Case 2 with k = 3**
    - **T(n) = 4T(n/2) + Θ(n² lg³ n)**
    - a = 4, b = 2, f(n) = n² lg³ n
    - Watershed: n^(log₂ 4) = n²
    - Compare: n² lg³ n vs n²
    - f(n) = Θ(n² · lg³ n), so k = 3
    - **Solution: T(n) = Θ(n² · lg^(3+1) n) = Θ(n² lg⁴ n)**
    - Log factors get incremented
- **Example 4: 3-way Merge Sort T(n) = 3T(n/3) + Θ(n)**
    - a = 3, b = 3, f(n) = n
    - Watershed: n^(log₃ 3) = n
    - Equal! k = 0
    - **Solution: T(n) = Θ(n lg n)**
    - Same complexity as 2-way merge sort
- **Example 5: T(n) = 4T(n/2) + Θ(n²)**
    - a = 4, b = 2, f(n) = n²
    - Watershed: n^(log₂ 4) = n²
    - Equal! k = 0
    - **Solution: T(n) = Θ(n² lg n)**
- **Tree Visualization for Case 2**

```
  Level 0: f(n) = c·n^(log_b a)
  Level 1: a nodes × f(n/b) = c·n^(log_b a)
  Level 2: a² nodes × f(n/b²) = c·n^(log_b a)
  ...
  All levels equal!
  Total = (cost per level) × (# of levels)
       = Θ(n^(log_b a)) × Θ(lg n)
       = Θ(n^(log_b a) lg n)
```

- **Common Pattern**
    - Any "standard" divide-and-conquer with linear combining
    - T(n) = aT(n/a) + Θ(n) → Θ(n lg n)
    - Dividing into a pieces of size n/a with linear merge
    - Classic examples: merge sort, quick sort (average case)

---

## **Case 3: Root Dominates**

- **Intuition**
    - The driving function f(n) is **much larger** than the watershed
    - Most work happens at the **root** of the recursion tree
    - The non-recursive work dominates the total cost
    - Work decreases as you go down the tree
- **Formal Conditions (BOTH Required)**
    1. **Polynomial Growth:** f(n) = Ω(n^(log_b a + ε)) for some ε > 0
        - "f(n) is polynomially larger than the watershed"
        - At least n^ε larger
    2. **Regularity Condition:** af(n/b) ≤ cf(n) for some c < 1
        - "The function shrinks properly when divided"
        - Ensures the root actually dominates
        - Most polynomial functions satisfy this
- **Solution**
    - **T(n) = Θ(f(n))**
    - The driving function dominates
    - Watershed is ignored in final answer
- **How to Check**
    - Calculate n^(log_b a)
    - Check if f(n) is polynomially larger
    - **Must also verify regularity condition!**
        - Calculate af(n/b)
        - Check if ≤ cf(n) for some c < 1
    - Both conditions required
- **Checking Regularity - General Pattern**
    - For f(n) = n^k where k > log_b a:
        - af(n/b) = a(n/b)^k = a · n^k/b^k
        - = (a/b^k) · n^k
        - Need: (a/b^k) < 1
        - Equivalently: a < b^k
        - Usually satisfied when f(n) is polynomially larger
- **Examples**
    - **Example 1: T(n) = 2T(n/2) + Θ(n²)**
        - a = 2, b = 2, f(n) = n²
        - Watershed: n^(log₂ 2) = n
        - Compare: n² vs n
        - **Check polynomial growth:**
            - Is n² = Ω(n^(1+ε))? Yes, with ε = 1
            - n² is polynomially larger ✓
        - **Check regularity:**
            - af(n/b) = 2(n/2)² = 2 · n²/4 = n²/2
            - Is n²/2 ≤ c · n² for some c < 1?
            - Yes! c = 1/2 < 1 ✓
        - **Both conditions met!**
        - **Solution: T(n) = Θ(n²)**
        - Root does n² work, dominates everything
    - **Example 2: T(n) = 3T(n/4) + Θ(n²)**
        - a = 3, b = 4, f(n) = n²
        - Watershed: n^(log₄ 3) ≈ n^0.793
        - Compare: n² vs n^0.793
        - **Polynomial growth:** n² >> n^0.793, ε ≈ 1.2 ✓
        - **Regularity:**
            - af(n/b) = 3(n/4)² = 3n²/16
            - 3n²/16 ≤ c·n² for c = 3/16 < 1 ✓
        - **Solution: T(n) = Θ(n²)**
    - **Example 3: T(n) = 4T(n/2) + Θ(n³)**
        - a = 4, b = 2, f(n) = n³
        - Watershed: n^(log₂ 4) = n²
        - **Polynomial growth:** n³ vs n², ε = 1 ✓
        - **Regularity:**
            - af(n/b) = 4(n/2)³ = 4 · n³/8 = n³/2
            - n³/2 ≤ c·n³ for c = 1/2 < 1 ✓
        - **Solution: T(n) = Θ(n³)**
    - **Example 4: T(n) = 27T(n/3) + Θ(n²)**
        - a = 27, b = 3, f(n) = n²
        - Watershed: n^(log₃ 27) = n³
        - Compare: n² vs n³
        - n² is SMALLER, not larger!
        - This is **Case 1**, not Case 3!
        - **Solution: T(n) = Θ(n³)**
- **Tree Visualization for Case 3**

```
  Root:    f(n) = HUGE cost ← DOMINATES
  Level 1: Smaller total cost
  Level 2: Even smaller
  ...
  Leaves:  Very little work
```

- Cost decreases geometrically as you go down
- Geometric series with ratio < 1
- Root contributes most
- **When Regularity Might Fail**
    - Weird functions that don't shrink properly
    - Example: f(n) = n²(2 + sin n)
        - Oscillates, doesn't shrink predictably
    - Most "normal" polynomial functions satisfy it
- **Why Both Conditions Matter**
    - Polynomial growth alone isn't enough
    - Regularity ensures the root actually dominates
    - Without it, later levels might contribute significantly
    - Both required for Case 3 to apply

---
**Quick Check Before Answering:**

1. Is f(n) **<** watershed? → Case 1 → Answer is **watershed**
2. Is f(n) **=** watershed? → Case 2 → Answer is **watershed × lg**
3. Is f(n) **>** watershed? → Case 3 → Answer is **f(n)**
## **Summary Comparison Table**

|Aspect|Case 1|Case 2|Case 3|
|---|---|---|---|
|**f(n) vs watershed**|Much smaller|Equal (±logs)|Much larger|
|**Who dominates**|Leaves|All levels|Root|
|**Condition**|f(n) = O(n^(log_b a - ε))|f(n) = Θ(n^(log_b a) lg^k n)|f(n) = Ω(n^(log_b a + ε)) AND regularity|
|**Solution**|Θ(n^(log_b a))|Θ(n^(log_b a) lg^(k+1) n)|Θ(f(n))|
|**Tree pattern**|Costs increase down|Costs same each level|Costs decrease down|
|**Series type**|Geometric, r > 1|Arithmetic-like|Geometric, r < 1|
|**Example**|T(n) = 8T(n/2) + n²|T(n) = 2T(n/2) + n|T(n) = 2T(n/2) + n²|
|**Result**|Θ(n³)|Θ(n lg n)|Θ(n²)|

---

## **Step-by-Step Process for Using Master Method**

1. **Verify the form**
    - Is it T(n) = aT(n/b) + f(n)?
    - Are a and b constants?
    - Are all subproblems the same size?
    - If NO → Master Method doesn't apply
2. **Extract a, b, and f(n)**
    - a = number of recursive calls
    - b = division factor
    - f(n) = driving function
3. **Calculate the watershed**
    - Compute log_b(a)
    - Watershed = n^(log_b a)
4. **Compare f(n) with watershed**
    - Is f(n) polynomially smaller? → Case 1
    - Is f(n) equal (times logs)? → Case 2
    - Is f(n) polynomially larger? → Check Case 3
5. **For Case 1:**
    - Verify f(n) = O(n^(log_b a - ε)) for some ε > 0
    - Solution: T(n) = Θ(n^(log_b a))
6. **For Case 2:**
    - Identify k (power of logarithm)
    - Solution: T(n) = Θ(n^(log_b a) lg^(k+1) n)
7. **For Case 3:**
    - Verify f(n) = Ω(n^(log_b a + ε)) for some ε > 0
    - **CHECK REGULARITY:** af(n/b) ≤ cf(n) for c < 1
    - If both hold → Solution: T(n) = Θ(f(n))
    - If regularity fails → Master Method doesn't apply

---

## **Common Pitfalls and Tips**

- **Don't forget regularity for Case 3**
    - Both conditions must hold
    - Most polynomials satisfy it, but always check
- **Watch for "gap" cases**
    - Some f(n) fall between cases
    - Example: f(n) = n/lg n when watershed is n
    - Master Method doesn't apply to these
- **Logarithm bases don't matter asymptotically**
    - lg n, log₃ n, log₁₀ n differ only by constants
    - In Θ notation, they're all the same
- **Don't confuse a with exponent of f(n)**
    - a is the coefficient of T(...)
    - Not the exponent in the driving function
- **Case 2 is most common for "balanced" algorithms**
    - Merge sort, binary search, many classics
    - Even split with linear (or constant) work
- **Strassen's algorithm uses Case 1**
    - T(n) = 7T(n/2) + Θ(n²)
    - Reduces multiplications from 8 to 7
    - Gets n^(log₂ 7) ≈ n^2.807 instead of n³

## Week 5 quick sort
- Goals
	- worse case Theta n^2
	- randomized version has expected theta nlon
	- constants hidden are small
	- sorts in place
	- good cache performance
- Quicksort is 3 step divide and conquer
- To sort the subarray A[p:r]
1. Divide: partition A[p:r] into two possibly empty subarrays A[p:q-1] and A[q+1:r] such that each element in the first subarray A[p:q-1] is ≤ A[q] and A[q] is ≤ each element in the second subarray A[q+1:r]
2. Conquer: sort the two subarray by recursive calls to quick sort
3. No worked is needed to combine the subarrays because they are sorted in place
- Perform the divide step by a procedures partition which returns the index q that marks the position separating the subarrays
- Pseudocode
	- ![[Pasted image 20260211144357.png]]
	- ![[Pasted image 20260211144416.png]]
	- ![[Pasted image 20260211144532.png]]
	- ![[Pasted image 20260211144842.png]]
- ![[Pasted image 20260211144902.png]]
- ![[Pasted image 20260211145002.png]]
- ![[Pasted image 20260211145036.png]]
- ![[Pasted image 20260211145143.png]]
- ![[Pasted image 20260211145301.png]]
- ![[Pasted image 20260211145401.png]]
- ![[Pasted image 20260211145428.png]]
- ![[Pasted image 20260211145548.png]]
- ![[Pasted image 20260211145646.png]]
- ![[Pasted image 20260211145815.png]]



Week 6
- ![[Pasted image 20260219183721.png]]
- ![[Pasted image 20260219183815.png]]
- ![[Pasted image 20260219184036.png]]
- ![[Pasted image 20260219184144.png]]
- ![[Pasted image 20260219184234.png]]
- ![[Pasted image 20260219184304.png]]
- ![[Pasted image 20260219184346.png]]
- ![[Pasted image 20260219184419.png]]
- ![[Pasted image 20260219184511.png]]
- ![[Pasted image 20260219184544.png]]
- ![[Pasted image 20260219184650.png]]
- ![[Pasted image 20260219184725.png]]
- ![[Pasted image 20260219184753.png]]
- ![[Pasted image 20260219184811.png]]
- ![[Pasted image 20260219184857.png]]
- ![[Pasted image 20260219185030.png]]
- ![[Pasted image 20260219185116.png]]
- ![[Pasted image 20260219185148.png]]
- ![[Pasted image 20260219185203.png]]
- ![[Pasted image 20260219185212.png]]
- ![[Pasted image 20260219185224.png]]
- ![[Pasted image 20260219185236.png]]
- ![[Pasted image 20260219185252.png]]
- ![[Pasted image 20260219185303.png]]















































































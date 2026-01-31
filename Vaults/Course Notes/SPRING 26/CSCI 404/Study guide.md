# Comprehensive Study Guide: Question-by-Question Explanations

---

## QUIZ 1: MASTER METHOD

### Question 1: Which recurrence has the correct form for applying the master method?

**Answer:** T(n) = 4T(n/2) + Θ(n²)

**Step-by-Step Solution:**

**Step 1:** Recall the Master Method form: **T(n) = aT(n/b) + f(n)**

- Must have constant coefficients a and b
- All subproblems must be the SAME size (n/b)
- f(n) must be polynomially bounded

**Step 2:** Check each option:

❌ **T(n) = T(n-1) + Θ(n)**

- This is LINEAR recursion (n-1), not DIVIDING
- Master Method requires division (n/b)

✅ **T(n) = 4T(n/2) + Θ(n²)**

- a = 4 (constant)
- b = 2 (constant)
- All subproblems are size n/2
- f(n) = n² (polynomial)
- PERFECT FORM!

❌ **T(n) = T(n/3) + T(2n/3) + Θ(n)**

- Two DIFFERENT subproblem sizes (n/3 and 2n/3)
- Master Method requires all subproblems be the same size

❌ **T(n) = 2T(n/2) + Θ(n/lg n)**

- f(n) = n/lg n is NOT polynomially bounded
- Falls in a "gap" between cases
- Master Method doesn't apply

**Key Takeaway:** Master Method needs identical subproblems with polynomial driving function.

---

### Question 2: For the recurrence T(n) = 8T(n/2) + Θ(n³) what are the values of a and b?

**Answer:** a = 8, b = 2

**Step-by-Step Solution:**

**Step 1:** Identify the form T(n) = aT(n/b) + f(n)

**Step 2:** Match up the parts:

- **T(n) = 8T(n/2) + Θ(n³)**
- **T(n) = aT(n/b) + f(n)**

**Step 3:** Extract values:

- **a** = coefficient of T(...) = **8**
    - This is the number of recursive calls
- **b** = what n is divided by = **2**
    - Look inside T(n/2) → dividing by 2
- f(n) = Θ(n³) (not asked for, but good to identify)

**Common Mistake:** Don't confuse a with the exponent of f(n)

- a = 8 (number of recursive calls)
- NOT a = 3 (that's the exponent in n³)

**Key Takeaway:**

- a = how many recursive calls
- b = what you divide n by

---

### Question 3: For T(n) = 9T(n/3) + Θ(n²) what is the watershed function n^(log_b a)?

**Answer:** n²

**Step-by-Step Solution:**

**Step 1:** Identify a and b

- T(n) = 9T(n/3) + Θ(n²)
- a = 9
- b = 3

**Step 2:** Calculate n^(log_b a)

- n^(log_b a) = n^(log₃ 9)

**Step 3:** Simplify log₃ 9

- What power do you raise 3 to get 9?
- 3² = 9
- So log₃ 9 = 2

**Step 4:** Therefore

- n^(log₃ 9) = n² ✓

**Alternative Method (if you forget logarithms):**

- 9 = 3^x → x = 2
- So n^(log₃ 9) = n²

**Key Takeaway:** The watershed function tells you the cost of the leaves and is critical for determining which Master Method case applies.

---

### Question 4: Which recurrence uses Case 1 of the master method?

**Answer:** T(n) = 8T(n/2) + Θ(n²)

**Step-by-Step Solution:**

**Step 1:** Remember Case 1 condition:

- f(n) is **polynomially smaller** than n^(log_b a)
- Solution: T(n) = Θ(n^(log_b a))

**Step 2:** Check each option:

**Option 1:** T(n) = 8T(n/2) + Θ(n²)

- a = 8, b = 2
- n^(log₂ 8) = n³
- Compare: f(n) = n² vs n³
- n² is polynomially smaller than n³ (by a factor of n)
- **This is Case 1!** ✓

**Option 2:** T(n) = 2T(n/2) + Θ(n)

- a = 2, b = 2
- n^(log₂ 2) = n
- Compare: f(n) = n vs n
- They're equal → Case 2

**Option 3:** T(n) = 4T(n/2) + Θ(n³)

- a = 4, b = 2
- n^(log₂ 4) = n²
- Compare: f(n) = n³ vs n²
- n³ is polynomially larger → Case 3

**Option 4:** T(n) = 9T(n/3) + Θ(n²)

- a = 9, b = 3
- n^(log₃ 9) = n²
- Compare: f(n) = n² vs n²
- They're equal → Case 2

**Key Takeaway:** In Case 1, the leaves dominate because f(n) is much smaller than the watershed.

---

### Question 5: Which statement correctly describes when Case 2 of the master method applies?

**Answer:** When f(n) = Θ(n^(log_b a) lg^k n) for k ≥ 0

**Step-by-Step Solution:**

**Step 1:** Understand what Case 2 means:

- f(n) and n^(log_b a) are "balanced"
- They're the same (possibly with logarithmic factors)
- All levels contribute equally to the total cost

**Step 2:** The general form:

- f(n) = Θ(n^(log_b a) · lg^k n)
- Where k ≥ 0 (can be 0, 1, 2, 3, ...)

**Step 3:** Examples:

- k = 0: f(n) = Θ(n^(log_b a))
    - Example: T(n) = 2T(n/2) + Θ(n)
- k = 1: f(n) = Θ(n^(log_b a) lg n)
    - Example: T(n) = 2T(n/2) + Θ(n lg n)
- k = 3: f(n) = Θ(n^(log_b a) lg³ n)
    - Example: T(n) = 4T(n/2) + Θ(n² lg³ n)

**Step 4:** Why other options are wrong:

- "Polynomially smaller" → That's Case 1
- "Polynomially larger" → That's Case 3
- "Doesn't have the form" → Master Method doesn't apply

**Key Takeaway:** Case 2 = balanced, possibly with log factors. Solution adds one more log.

---

### Question 6: For T(n) = 4T(n/2) + Θ(n²) which case applies and what is the solution?

**Answer:** Case 2: T(n) = Θ(n² lg n)

**Step-by-Step Solution:**

**Step 1:** Find a and b

- a = 4, b = 2

**Step 2:** Calculate watershed n^(log_b a)

- n^(log₂ 4) = n²

**Step 3:** Compare f(n) with n^(log_b a)

- f(n) = n²
- n^(log_b a) = n²
- They're EQUAL!

**Step 4:** Check if it's Case 2 form

- f(n) = Θ(n²) = Θ(n² · lg⁰ n)
- So k = 0
- This is Case 2!

**Step 5:** Apply Case 2 solution

- Solution: Θ(n^(log_b a) · lg^(k+1) n)
- = Θ(n² · lg^(0+1) n)
- = **Θ(n² lg n)** ✓

**Visual Understanding:**

- Each level of the tree costs n²
- There are lg n levels
- Total: n² × lg n = Θ(n² lg n)

**Key Takeaway:** When f(n) equals the watershed, multiply by an extra log.

---

### Question 7: For Case 3 of the master method to apply which conditions must be met?

**Answer:** Both polynomial growth AND regularity condition must hold

**Step-by-Step Solution:**

**Step 1:** Understand Case 3 requirements

**Condition 1 - Polynomial Growth:**

- f(n) = Ω(n^(log_b a + ε)) for some ε > 0
- f(n) must be polynomially LARGER than the watershed
- Not just slightly larger, but by a polynomial factor

**Condition 2 - Regularity:**

- af(n/b) ≤ cf(n) for some constant c < 1
- The function must "shrink" properly when you divide
- This ensures the root dominates

**Step 2:** Why BOTH are needed:

**Polynomial growth alone isn't enough:**

- Example: f(n) = n² lg n might be larger than n², but if it doesn't satisfy regularity, Case 3 doesn't apply

**Regularity alone isn't enough:**

- You also need f(n) to be significantly larger

**Step 3:** Example where both hold:

- T(n) = 2T(n/2) + n²
- f(n) = n², n^(log_b a) = n
- n² = Ω(n^(1+1)) → polynomial growth ✓
- Check regularity: 2(n/2)² = n²/2 ≤ (1/2)n² where 1/2 < 1 ✓
- **Both conditions met!**

**Key Takeaway:** Case 3 is the most restrictive case - both conditions are mandatory.

---

### Question 8: What is the solution to T(n) = 8T(n/4) + Θ(n)?

**Answer:** Θ(n^1.5)

**Step-by-Step Solution:**

**Step 1:** Identify a, b, f(n)

- a = 8
- b = 4
- f(n) = n

**Step 2:** Calculate watershed

- n^(log_b a) = n^(log₄ 8)

**Step 3:** Simplify log₄ 8

- What power do you raise 4 to get 8?
- 4^x = 8
- (2²)^x = 2³
- 2^(2x) = 2³
- 2x = 3
- x = 3/2 = 1.5
- So log₄ 8 = 1.5

**Step 4:** Compare f(n) with watershed

- f(n) = n = n¹
- n^(log₄ 8) = n^1.5
- n¹ vs n^1.5

**Step 5:** Determine the case

- Is n polynomially smaller than n^1.5?
- n = O(n^(1.5 - 0.5)) = O(n¹)
- Yes! ε = 0.5
- **This is Case 1**

**Step 6:** Apply Case 1 solution

- T(n) = Θ(n^(log_b a))
- T(n) = **Θ(n^1.5)** ✓

**Key Takeaway:** The leaves dominate, giving us Θ(n^1.5).

---

### Question 9: What is the solution to T(n) = 2T(n/2) + Θ(n²)?

**Answer:** Θ(n²)

**Step-by-Step Solution:**

**Step 1:** Identify a, b, f(n)

- a = 2
- b = 2
- f(n) = n²

**Step 2:** Calculate watershed

- n^(log₂ 2) = n¹ = n

**Step 3:** Compare f(n) with watershed

- f(n) = n²
- n^(log_b a) = n
- n² vs n

**Step 4:** Determine the case

- Is n² polynomially larger than n?
- n² = Ω(n^(1+1)) = Ω(n²)
- Yes! ε = 1
- This looks like Case 3!

**Step 5:** Check regularity condition

- af(n/b) ≤ cf(n)
- 2 · (n/2)² ≤ c · n²
- 2 · n²/4 ≤ c · n²
- n²/2 ≤ c · n²
- This holds for c = 1/2 < 1 ✓

**Step 6:** Apply Case 3 solution

- T(n) = Θ(f(n))
- T(n) = **Θ(n²)** ✓

**Key Takeaway:** The root dominates because the work at the top level (n²) is much more than the recursive work.

---

### Question 10: The recurrence for merge sort is T(n) = 2T(n/2) + Θ(n). What is its solution?

**Answer:** Θ(n lg n)

**Step-by-Step Solution:**

**Step 1:** Understand merge sort

- Divide array in half (2 subproblems)
- Each subproblem is size n/2
- Merging takes Θ(n) time

**Step 2:** Identify a, b, f(n)

- a = 2 (two recursive calls)
- b = 2 (divide by 2)
- f(n) = n (merging cost)

**Step 3:** Calculate watershed

- n^(log₂ 2) = n¹ = n

**Step 4:** Compare f(n) with watershed

- f(n) = n
- n^(log_b a) = n
- They're EQUAL!

**Step 5:** Determine the case

- f(n) = Θ(n) = Θ(n · lg⁰ n)
- k = 0
- **This is Case 2**

**Step 6:** Apply Case 2 solution

- T(n) = Θ(n^(log_b a) · lg^(k+1) n)
- T(n) = Θ(n · lg^1 n)
- T(n) = **Θ(n lg n)** ✓

**Visual Understanding:**

```
Level 0: n work
Level 1: n/2 + n/2 = n work
Level 2: n/4 + n/4 + n/4 + n/4 = n work
...
lg n levels, each doing n work
Total: n × lg n
```

**Key Takeaway:** This is the classic divide-and-conquer pattern giving O(n lg n).

---

### Question 11: What does it mean for f(n) to be polynomially smaller than n^(log_b a) in Case 1?

**Answer:** f(n) = O(n^(log_b a - ε)) for some constant ε > 0

**Step-by-Step Solution:**

**Step 1:** Understand "polynomially smaller"

- Not just smaller by a constant factor
- Smaller by at least n^ε for some ε > 0
- A whole polynomial degree smaller

**Step 2:** The formal definition:

- f(n) = O(n^(log_b a - ε))
- The ε > 0 ensures a gap
- It's not just slightly smaller, but significantly smaller

**Step 3:** Examples:

**Polynomially smaller (Case 1):**

- f(n) = n, watershed = n²
- n = O(n^(2-1)) = O(n)
- ε = 1 ✓
- f(n) = n², watershed = n³
- n² = O(n^(3-1)) = O(n²)
- ε = 1 ✓

**NOT polynomially smaller:**

- f(n) = n, watershed = n
- Can't find ε > 0 where n = O(n^(1-ε))
- f(n) = n/lg n, watershed = n
- Only smaller by logarithmic factor, not polynomial

**Step 4:** Why other options are wrong:

- "Any amount smaller" - too weak, needs polynomial gap
- "Logarithmically smaller" - not enough, needs polynomial gap
- "Slower by any factor" - not precise enough

**Key Takeaway:** Polynomial gap means at least n^ε smaller for some ε > 0.

---

### Question 12: Why doesn't the master method apply to T(n) = 2T(n/2) + Θ(n/lg n)?

**Answer:** Because f(n) falls in the gap between Case 1 and Case 2

**Step-by-Step Solution:**

**Step 1:** Check the form

- T(n) = 2T(n/2) + Θ(n/lg n)
- a = 2, b = 2, f(n) = n/lg n
- Form looks correct: T(n) = aT(n/b) + f(n) ✓

**Step 2:** Calculate watershed

- n^(log₂ 2) = n

**Step 3:** Try to match a case

**Is it Case 1?** (f(n) polynomially smaller)

- f(n) = n/lg n
- watershed = n
- Is n/lg n = O(n^(1-ε)) for some ε > 0?
- No! n/lg n is only slightly smaller than n (by log factor)
- Not polynomially smaller ✗

**Is it Case 2?** (f(n) equals watershed times log factor)

- f(n) = n/lg n
- watershed = n
- Is n/lg n = Θ(n · lg^k n) for some k ≥ 0?
- n/lg n = n · lg^(-1) n
- k = -1 < 0 ✗
- Case 2 requires k ≥ 0

**Is it Case 3?** (f(n) polynomially larger)

- f(n) = n/lg n
- watershed = n
- Is n/lg n polynomially larger than n?
- No! It's actually smaller ✗

**Step 4:** Conclusion

- f(n) = n/lg n falls in the "gap"
- Too small for Case 2 (k would be negative)
- Not small enough for Case 1 (only log factor, not polynomial)
- Master Method **doesn't apply**

**Key Takeaway:** There are functions that fall between the cases - Master Method has limitations.

---

### Question 13: The simple recursive matrix multiplication has recurrence T(n) = 8T(n/2) + Θ(1). What is its solution?

**Answer:** Θ(n³)

**Step-by-Step Solution:**

**Step 1:** Understand the algorithm

- Multiplying two n×n matrices
- Divide each matrix into 4 blocks (2×2)
- Need 8 multiplications of n/2 × n/2 matrices
- Combining results takes constant time

**Step 2:** Identify a, b, f(n)

- a = 8 (eight subproblems)
- b = 2 (each dimension halved)
- f(n) = Θ(1) (constant combining time)

**Step 3:** Calculate watershed

- n^(log₂ 8) = n³

**Step 4:** Compare f(n) with watershed

- f(n) = 1
- n^(log_b a) = n³
- 1 vs n³

**Step 5:** Determine the case

- Is 1 polynomially smaller than n³?
- 1 = O(n^(3-3)) = O(n⁰)
- Yes! ε = 3
- **This is Case 1**

**Step 6:** Apply Case 1 solution

- T(n) = Θ(n^(log_b a))
- T(n) = **Θ(n³)** ✓

**Visual Understanding:**

- All the work is in the leaves
- Number of leaves = 8^(lg n) = n^(lg 8) = n³
- Each leaf does constant work
- Total: Θ(n³)

**Key Takeaway:** Standard matrix multiplication is cubic because of 8 recursive multiplications.

---

### Question 14: Strassen's algorithm has recurrence T(n) = 7T(n/2) + Θ(n²). What is its solution?

**Answer:** Θ(n^(lg 7))

**Step-by-Step Solution:**

**Step 1:** Understand Strassen's improvement

- Uses only 7 multiplications instead of 8
- Combining takes Θ(n²) instead of Θ(1)
- Trade-off: fewer recursive calls for more combining work

**Step 2:** Identify a, b, f(n)

- a = 7 (seven subproblems!)
- b = 2
- f(n) = n²

**Step 3:** Calculate watershed

- n^(log₂ 7) ≈ n^2.807

**Step 4:** Compare f(n) with watershed

- f(n) = n²
- n^(log_b a) = n^(lg 7) ≈ n^2.807
- n² vs n^2.807

**Step 5:** Determine the case

- Is n² polynomially smaller than n^2.807?
- n² = O(n^(2.807 - 0.807)) = O(n²)
- Yes! ε ≈ 0.807
- **This is Case 1**

**Step 6:** Apply Case 1 solution

- T(n) = Θ(n^(log_b a))
- T(n) = **Θ(n^(lg 7))** ✓
- This is approximately **Θ(n^2.807)**

**Why this is better:**

- Standard: Θ(n³)
- Strassen: Θ(n^2.807)
- Strassen is asymptotically faster!

**Key Takeaway:** Reducing recursive calls from 8 to 7 gives a significant speedup.

---

### Question 15: For T(n) = 4T(n/2) + Θ(n² lg³ n) which case applies?

**Answer:** Case 2 with k=3

**Step-by-Step Solution:**

**Step 1:** Identify a, b, f(n)

- a = 4
- b = 2
- f(n) = n² lg³ n

**Step 2:** Calculate watershed

- n^(log₂ 4) = n²

**Step 3:** Compare f(n) with watershed

- f(n) = n² lg³ n
- n^(log_b a) = n²

**Step 4:** Check the form

- f(n) = n² lg³ n
- = n² · lg³ n
- = Θ(n^(log_b a) · lg^k n) where k = 3

**Step 5:** Verify Case 2

- Form: f(n) = Θ(n^(log_b a) · lg^k n) for k ≥ 0
- We have: f(n) = Θ(n² · lg³ n)
- k = 3 ≥ 0 ✓
- **This is Case 2 with k = 3**

**Step 6:** Apply Case 2 solution

- T(n) = Θ(n^(log_b a) · lg^(k+1) n)
- T(n) = Θ(n² · lg^(3+1) n)
- T(n) = **Θ(n² lg⁴ n)**

**Key Takeaway:** Logarithmic factors in f(n) don't change the case, just the value of k.

---

### Question 16: For T(n) = 2T(n/2) + Θ(n²) does the regularity condition hold?

**Answer:** Yes: 2(n/2)² = n²/2 ≤ cn² for c = 1/2 < 1

**Step-by-Step Solution:**

**Step 1:** Understand regularity condition

- For Case 3: af(n/b) ≤ cf(n) for some c < 1
- This ensures the function "shrinks" properly

**Step 2:** Identify a, b, f(n)

- a = 2
- b = 2
- f(n) = n²

**Step 3:** Calculate af(n/b)

- af(n/b) = 2 · f(n/2)
- = 2 · (n/2)²
- = 2 · n²/4
- = n²/2

**Step 4:** Check if af(n/b) ≤ cf(n)

- n²/2 ≤ c · n²
- Divide both sides by n²:
- 1/2 ≤ c
- We can choose c = 1/2

**Step 5:** Verify c < 1

- c = 1/2 < 1 ✓
- **Regularity condition holds!**

**Why this matters:**

- This confirms Case 3 applies
- Without regularity, even if f(n) is larger, Case 3 doesn't work
- The root must dominate by a sufficient factor

**Common pattern:**

- For f(n) = n^k where k > log_b a
- af(n/b) = a(n/b)^k = a · n^k/b^k = (a/b^k) · n^k
- If a/b^k < 1, regularity holds with c = a/b^k

**Key Takeaway:** Regularity is easy to verify for polynomials - just check if a/b^k < 1.

---

### Question 17: Can the master method solve T(n) = T(n/3) + T(2n/3) + Θ(n)?

**Answer:** No because subproblems have different sizes

**Step-by-Step Solution:**

**Step 1:** Recall Master Method requirements

- Form: T(n) = aT(n/b) + f(n)
- ALL subproblems must be the SAME size (n/b)

**Step 2:** Examine this recurrence

- T(n) = T(n/3) + T(2n/3) + Θ(n)
- First subproblem: size n/3
- Second subproblem: size 2n/3
- **Different sizes!**

**Step 3:** Why Master Method fails

- Master Method assumes uniformity
- It calculates based on a identical subproblems of size n/b
- Here we have different sizes, so the analysis doesn't work

**Step 4:** What about the Akra-Bazzi method?

- The question mentions it
- Akra-Bazzi is a generalization of Master Method
- It CAN handle different subproblem sizes
- But it's not part of the standard Master Method

**Step 5:** How to solve this recurrence?

- Use substitution method
- Or draw a recursion tree
- Tree will be unbalanced (different path lengths)
- Solution is still Θ(n lg n), but Master Method can't prove it

**Visual Understanding:**

```
           n
        /     \
      n/3     2n/3
     /  \     /   \
  n/9  2n/9 2n/9  4n/9
```

Notice the asymmetry - paths have different lengths.

**Key Takeaway:** Master Method is powerful but limited to uniform subproblem sizes.

---

### Question 18: Binary search has recurrence T(n) = T(n/2) + Θ(1). What is its solution?

**Answer:** Θ(lg n)

**Step-by-Step Solution:**

**Step 1:** Understand binary search

- Search a sorted array
- Compare with middle element
- Recursively search ONE half
- Only constant work per step

**Step 2:** Identify a, b, f(n)

- a = 1 (only one recursive call)
- b = 2 (search half the array)
- f(n) = Θ(1) (constant comparison)

**Step 3:** Calculate watershed

- n^(log₂ 1) = n⁰ = 1

**Step 4:** Compare f(n) with watershed

- f(n) = 1
- n^(log_b a) = 1
- They're EQUAL!

**Step 5:** Determine the case

- f(n) = Θ(1) = Θ(1 · lg⁰ n)
- k = 0
- **This is Case 2**

**Step 6:** Apply Case 2 solution

- T(n) = Θ(n^(log_b a) · lg^(k+1) n)
- T(n) = Θ(1 · lg^1 n)
- T(n) = **Θ(lg n)** ✓

**Visual Understanding:**

```
Level 0: 1 work (compare)
Level 1: 1 work (compare)
Level 2: 1 work (compare)
...
lg n levels, each doing constant work
Total: Θ(lg n)
```

**Key Takeaway:** Binary search's efficiency comes from eliminating half the search space each time.

---

### Question 19: A 3-way merge sort has recurrence T(n) = 3T(n/3) + Θ(n). What is its solution?

**Answer:** Θ(n lg n)

**Step-by-Step Solution:**

**Step 1:** Understand 3-way merge sort

- Divide array into THREE parts
- Recursively sort each third
- Merge three sorted arrays

**Step 2:** Identify a, b, f(n)

- a = 3 (three recursive calls)
- b = 3 (divide into thirds)
- f(n) = n (merging three arrays)

**Step 3:** Calculate watershed

- n^(log₃ 3) = n¹ = n

**Step 4:** Compare f(n) with watershed

- f(n) = n
- n^(log_b a) = n
- They're EQUAL!

**Step 5:** Determine the case

- f(n) = Θ(n) = Θ(n · lg⁰ n)
- k = 0
- **This is Case 2**

**Step 6:** Apply Case 2 solution

- T(n) = Θ(n^(log_b a) · lg^(k+1) n)
- T(n) = Θ(n · lg n)
- T(n) = **Θ(n lg n)** ✓

**Note on logarithm base:**

- The solution says Θ(n log₃ n)
- But log₃ n and lg n differ only by a constant factor
- log₃ n = lg n / lg 3
- In big-Theta notation, constant factors don't matter
- **Both Θ(n lg n) and Θ(n log₃ n) are correct**

**Visual Understanding:**

```
Level 0: n work
Level 1: 3 × (n/3) = n work
Level 2: 9 × (n/9) = n work
...
log₃ n levels, each doing n work
```

**Key Takeaway:** Changing the split factor doesn't change asymptotic complexity for merge sort variants.

---

### Question 20: For T(n) = 27T(n/3) + Θ(n²) what is the solution?

**Answer:** Θ(n³)

**Step-by-Step Solution:**

**Step 1:** Identify a, b, f(n)

- a = 27
- b = 3
- f(n) = n²

**Step 2:** Calculate watershed

- n^(log₃ 27)
- What power gives 27?
- 3³ = 27
- So log₃ 27 = 3
- n^(log₃ 27) = n³

**Step 3:** Compare f(n) with watershed

- f(n) = n²
- n^(log_b a) = n³
- n² vs n³

**Step 4:** Determine the case

- Is n² polynomially smaller than n³?
- n² = O(n^(3-1)) = O(n²)
- Yes! ε = 1
- **This is Case 1**

**Step 5:** Apply Case 1 solution

- T(n) = Θ(n^(log_b a))
- T(n) = **Θ(n³)** ✓

**Visual Understanding:**

- Number of leaves = 27^(log₃ n) = n^(log₃ 27) = n³
- Each level's cost decreases geometrically
- Leaves dominate
- Total cost: Θ(n³)

**Key Takeaway:** When you have many recursive calls (a=27) relative to the shrink factor (b=3), the leaves typically dominate.

---

## QUIZ 2: RECURSION TREES & SUBSTITUTION METHOD

### Question 1: For T(n) = 4T(n/2) + cn what is the height of the recursion tree?

**Answer:** lg n

**Step-by-Step Solution:**

**Step 1:** Understand what height means

- Height = number of levels from root to leaves
- = how many times you can divide until reaching base case

**Step 2:** Identify what you're dividing by

- T(n) = 4T(n/2) + cn
- Look at T(n/**2**) - dividing by 2
- b = 2

**Step 3:** Formula for height

- **Height = log_b(n)**
- Height = log₂(n) = **lg n**

**Step 4:** Verify by tracing down

```
Level 0: n
Level 1: n/2
Level 2: n/4
Level 3: n/8
...
Level h: n/2^h
```

When do we reach 1? When n/2^h = 1

- n = 2^h
- h = lg n ✓

**Important Note:** The "4" doesn't matter for height!

- The 4 tells you how many subproblems (width)
- The 2 tells you the height (how fast you divide)

**Key Takeaway:** Height = log_b(n) where b is what you divide by.

---

### Question 2: For T(n) = T(n/3) + T(2n/3) + Θ(n) what can we say about the recursion tree?

**Answer:** It's unbalanced with different path lengths

**Step-by-Step Solution:**

**Step 1:** Identify the subproblem sizes

- T(n) = T(n/3) + T(2n/3) + Θ(n)
- Left child: n/3
- Right child: 2n/3
- **Different sizes!**

**Step 2:** Trace the left path (shorter)

```
Level 0: n
Level 1: n/3
Level 2: n/9
Level 3: n/27
...
Reaches 1 when: n/3^h = 1 → h = log₃ n
```

**Step 3:** Trace the right path (longer)

```
Level 0: n
Level 1: 2n/3
Level 2: 4n/9
Level 3: 8n/27
...
Reaches 1 when: n(2/3)^h = 1 → h = log₃/₂ n
```

**Step 4:** Compare path lengths

- Left path: log₃ n ≈ 0.631 lg n
- Right path: log₃/₂ n ≈ 1.709 lg n
- **Different lengths!**

**Step 5:** Visual representation

```
         n
      /     \
    n/3     2n/3
   /  \     /   \
 n/9 2n/9 2n/9 4n/9
```

The tree leans right - it's **unbalanced**.

**Quick rule:** Different fractions = unbalanced tree

**Key Takeaway:** When subproblems have different sizes, paths have different lengths - the tree is unbalanced.

---

### Question 3: Which technique helps generate good guesses for the substitution method?

**Answer:** Draw a recursion tree to see the pattern

**Step-by-Step Solution:**

**Step 1:** Understand the challenge

- Substitution requires you to guess first
- How do you make a good guess?

**Step 2:** Why recursion trees help

- **Visualize** the structure
- **See** the cost at each level
- **Identify** patterns (constant, increasing, decreasing)
- **Count** the number of levels
- **Estimate** total work

**Step 3:** Example - T(n) = 2T(n/2) + n

**Draw the tree:**

```
Level 0: n          (cost = n)
Level 1: n/2 + n/2  (cost = n)
Level 2: 4×(n/4)    (cost = n)
...
Height: lg n levels
```

**Observe the pattern:**

- Each level costs n
- There are lg n levels
- **Guess:** T(n) = O(n lg n) ✓

**Step 4:** Why other options are wrong

- "Always guess O(n²) first" - No strategy, often wrong
- "Trial and error with no strategy" - Inefficient
- "Guess same as driving function" - Ignores recursion structure

**Step 5:** Process

1. Draw the tree
2. Calculate cost per level
3. Sum across all levels
4. That's your guess!

**Key Takeaway:** Recursion trees turn abstract recurrences into visual patterns you can analyze.

---

### Question 4: What is the primary purpose of drawing a recursion tree?

**Answer:** To visualize the structure and generate a good guess for the solution

**Step-by-Step Solution:**

**Step 1:** What recursion trees do

- Provide **visual intuition**
- Help **generate guesses**
- Show **cost distribution**
- Identify **patterns**

**Step 2:** What recursion trees DON'T do

- ❌ Replace mathematical proof
    - Tree gives intuition, not rigorous proof
    - Still need substitution or Master Method
- ❌ Calculate exact constants
    - Trees give asymptotic bounds (big-O, Θ, Ω)
    - Don't worry about exact coefficient values
- ❌ Avoid using Master Method
    - If Master Method applies, use it!
    - Trees are for when you need a guess first

**Step 3:** The workflow

```
Recurrence
    ↓
Draw tree → Generate guess
    ↓
Prove with substitution or Master Method
```

**Step 4:** Example workflow

- Given: T(n) = 4T(n/2) + n²
- Draw tree: See costs are n², n²/2, n²/4, ...
- Pattern: Geometric series, root dominates
- **Guess:** T(n) = Θ(n²)
- **Verify:** Use Master Method (Case 3) or substitution

**Key Takeaway:** Trees are a tool for building intuition and generating guesses, not a replacement for formal proof.

---

### Question 5: For T(n) = 2T(n/2) + 3n, if we guess T(n) ≤ cn lg n, what do we substitute for T(n/2)?

**Answer:** c(n/2) lg(n/2)

**Step-by-Step Solution:**

**Step 1:** Understand the inductive hypothesis

- We're guessing: **T(n) ≤ cn lg n**
- This means: for ANY input size m, T(m) ≤ cm lg m

**Step 2:** Apply to size n/2

- Our guess works for all sizes
- So for size n/2: **T(n/2) ≤ c(n/2) lg(n/2)**

**Step 3:** The pattern

- Whatever form you guess for T(n)...
- Use the SAME form for T(n/2)...
- Just replace every n with n/2

**Step 4:** Examples of the pattern

```
If T(n) ≤ cn lg n
Then T(n/2) ≤ c(n/2) lg(n/2)

If T(n) ≤ cn²
Then T(n/2) ≤ c(n/2)²

If T(n) ≤ cn - d
Then T(n/2) ≤ c(n/2) - d
```

**Step 5:** Why other options are wrong

❌ **c(n/2)**

- Missing the lg(n/2) part
- Doesn't match the form

❌ **cn lg n**

- This is T(n), not T(n/2)
- Didn't substitute n/2 for n

❌ **(1/2)cn lg n**

- Wrong! This would be if you had T(n) ≤ cn lg n and somehow took half
- But you need to substitute the argument

**Key Takeaway:** Substitute the form everywhere - replace n with n/2 throughout your guess.

---

### Question 6: For T(n) = 3T(n/4) + cn², the level costs form cn², 3cn²/16, 9cn²/256,... What type of series is this?

**Answer:** Geometric series with ratio 3/16

**Step-by-Step Solution:**

**Step 1:** Recall geometric series

- Each term = (previous term) × (constant ratio)
- Form: a, ar, ar², ar³, ...
- Constant ratio r

**Step 2:** Calculate the ratio **From level 0 to level 1:**

- Level 0: cn²
- Level 1: 3cn²/16
- Ratio: (3cn²/16)/(cn²) = 3/16

**From level 1 to level 2:**

- Level 1: 3cn²/16
- Level 2: 9cn²/256
- Ratio: (9cn²/256)/(3cn²/16) = (9cn²/256) × (16/3cn²) = 9×16/(256×3) = 144/768 = 3/16 ✓

**Step 3:** Why is the ratio 3/16?

**At each level:**

- **Number of nodes** multiplies by 3 (from 3T...)
- **Size** divides by 4, so cost divides by 4² = 16 (from cn²)
- Net effect: multiply by 3/16

**Step 4:** General pattern

```
Level 0: cn²
Level 1: cn² × (3/16)¹
Level 2: cn² × (3/16)²
Level k: cn² × (3/16)^k
```

**Step 5:** Sum the geometric series

- Since r = 3/16 < 1, the series converges
- Sum ≈ cn²/(1 - 3/16) = cn²/(13/16) = O(n²)
- The first term dominates!

**Key Takeaway:** Recursion tree levels often form geometric series with ratio = (# of subproblems)/(shrink factor^k) where k is the exponent in f(n).

---

### Question 7: When should you subtract a lower-order term in the substitution method?

**Answer:** When your initial guess doesn't quite work due to an additive constant

**Step-by-Step Solution:**

**Step 1:** The problem

- Sometimes your "obvious" guess almost works
- But you get an extra additive constant that ruins it
- Example: trying to prove T(n) ≤ cn but getting T(n) ≤ cn + n

**Step 2:** The solution - subtract a lower-order term

- Instead of T(n) ≤ cn
- Try **T(n) ≤ cn - d** for some d > 0

**Step 3:** Full example - T(n) = 2T(n/2) + n

**First attempt (fails):**

```
Guess: T(n) ≤ cn
T(n) = 2T(n/2) + n
     ≤ 2[c(n/2)] + n
     ≤ cn + n
Need T(n) ≤ cn, but have cn + n
FAILS! Extra +n
```

**Second attempt (works):**

```
Guess: T(n) ≤ cn - d
T(n) = 2T(n/2) + n
     ≤ 2[c(n/2) - d] + n
     ≤ cn - 2d + n
     ≤ cn - d     (if 2d ≥ n + d, i.e., d ≥ n)
WORKS! ✓
```

**Step 4:** When NOT to use it

- Not "always as first step" - only when needed
- Not "never" - it's a valid technique
- Not just for Case 3 - works for any substitution

**Step 5:** Why it works

- The -d term gives you "wiggle room"
- Lower-order compared to the main term
- Doesn't affect asymptotic bound
- But makes the algebra work out

**Key Takeaway:** Lower-order terms are like mathematical cushions - they absorb annoying constants.

---

### Question 8: What property must an algorithmic recurrence satisfy?

**Answer:** Every recursion path must terminate in finite time

**Step-by-Step Solution:**

**Step 1:** Why this is fundamental

- A recurrence represents an algorithm
- Algorithms must finish!
- Infinite recursion = infinite loop = not an algorithm

**Step 2:** What this means ✅ **Must have:**

- Base case(s)
- Problem size must decrease
- Eventually reach base case

❌ **Cannot have:**

- Infinite recursion
- Non-decreasing problem size
- No base case

**Step 3:** Valid examples

✅ **T(n) = T(n/2) + n**

- Decreases: n → n/2 → n/4 → ... → 1
- Base case: T(1) = constant
- Terminates!

✅ **T(n) = 2T(n/2) + n**

- Still decreases to base case
- Multiple recursive calls OK
- Terminates!

**Step 4:** Invalid examples

❌ **T(n) = T(n) + n**

- n → n → n → ...
- Never decreases!
- Infinite loop

❌ **T(n) = T(2n) + n**

- n → 2n → 4n → ...
- Grows forever!
- Never reaches base case

❌ **T(n) = T(n+1) + n**

- Increases instead of decreasing
- No termination

**Step 5:** Why other options are wrong

- "Must use master method" - No! Many recurrences can't
- "Must have exactly 2 recursive calls" - No! Can have 1, 3, any number
- "Driving function must be polynomial" - No! Can be anything

**Key Takeaway:** The ONLY universal requirement is termination - everything else is about solving techniques.

---

### Question 9: Why should you NOT use asymptotic notation (like O or Θ) in your inductive hypothesis?

**Answer:** The hidden constants can change making the proof invalid

**Step-by-Step Solution:**

**Step 1:** The problem with hidden constants

- O(n) means T(n) ≤ c₁n for **some** c₁
- But which c₁? It's hidden!
- During proof, you might get different constants

**Step 2:** Concrete example of what goes wrong

**Bad approach (fails):**

```
Guess: T(n) = O(n)
This means: T(n) ≤ c₁n for some c₁

Substitute into T(n) = 2T(n/2) + n:
T(n) ≤ 2[c₁(n/2)] + n
     ≤ c₁n + n
     ≤ (c₁ + 1)n

Need to show: T(n) ≤ c₂n for some c₂
We have: T(n) ≤ (c₁ + 1)n

Problem: c₂ = c₁ + 1, so c₂ ≠ c₁
The constant CHANGED!
This is circular - you're using different constants
```

**Step 3:** Correct approach

**Good approach (works):**

```
Guess: T(n) ≤ cn (explicit constant)

Substitute:
T(n) = 2T(n/2) + n
     ≤ 2[c(n/2)] + n
     ≤ cn + n
     ≤ cn  (need c such that cn + n ≤ cn, impossible!)

Actually need: T(n) ≤ cn - d (lower-order term)
Then: T(n) ≤ cn - 2d + n ≤ cn - d if d ≥ n ✓

Now we verified THE SAME c and d work throughout!
```

**Step 4:** The key difference

- **With explicit constants:** You verify one specific c works
- **With O-notation:** Constants can shift, breaking the proof

**Step 5:** After you prove it

- Once you've proven T(n) ≤ cn with explicit c
- **Then** you can conclude T(n) = O(n)
- But don't use O-notation during the proof

**Key Takeaway:** Induction requires the SAME constant throughout - O-notation hides this critical detail.

---

### Question 10: When using substitution to prove T(n) = O(n lg n) which is the correct inductive hypothesis?

**Answer:** T(n) ≤ cn lg n for some constant c > 0

**Step-by-Step Solution:**

**Step 1:** What we're trying to prove

- We want to show T(n) = O(n lg n)
- This means T(n) ≤ c · n lg n for large enough n

**Step 2:** Evaluate each option

✅ **T(n) ≤ cn lg n for some constant c > 0**

- Clear inequality (≤)
- Explicit constant (c)
- Can substitute this into recurrence
- Can verify if it works
- **CORRECT!**

❌ **T(n) = O(n lg n)**

- Uses asymptotic notation (hidden constant)
- Can't substitute this mathematically
- Constants can change (previous question explained why)

❌ **T(n) ≤ O(n lg n)**

- Mixing inequality with asymptotic notation
- Doesn't make sense (O already means ≤)
- Redundant and confusing

❌ **T(n) < n lg n**

- Missing the constant c
- Too restrictive (< instead of ≤)
- What if T(n) exactly equals n lg n?
- Won't work for many valid cases

**Step 3:** How you'd use the correct form

```
Step 1: Assume T(k) ≤ ck lg k for all k < n
Step 2: Prove T(n) ≤ cn lg n
Step 3: Substitute assumption into recurrence
Step 4: Verify the same c works
```

**Step 4:** Example

For T(n) = 2T(n/2) + n:

```
Assume: T(k) ≤ ck lg k for k < n
Prove: T(n) ≤ cn lg n

T(n) = 2T(n/2) + n
     ≤ 2[c(n/2)lg(n/2)] + n
     ≤ cn lg(n/2) + n
     ≤ cn(lg n - 1) + n
     ≤ cn lg n - cn + n
     ≤ cn lg n  (if c ≥ 1)

Choose c = 1, works! ✓
```

**Key Takeaway:** Always use explicit constants (T(n) ≤ cf(n)) in inductive hypothesis, never asymptotic notation.

---

### Question 11: A complete binary tree of height h has how many leaves?

**Answer:** 2^h

**Step-by-Step Solution:**

**Step 1:** Understand complete binary tree

- Every internal node has exactly 2 children
- All levels are completely filled
- Leaves are all at the bottom (level h)

**Step 2:** Count nodes at each level

```
Level 0 (root):  2⁰ = 1 node
Level 1:         2¹ = 2 nodes
Level 2:         2² = 4 nodes
Level 3:         2³ = 8 nodes
...
Level h (leaves): 2^h nodes
```

**Step 3:** Pattern

- Each level down, nodes **double**
- Start with 1 at root
- Double h times
- Get 2^h at bottom

**Step 4:** Visual example (h = 3)

```
Level 0:        O              (1 = 2⁰)
Level 1:      /   \            (2 = 2¹)
Level 2:    O       O          (4 = 2²)
           / \     / \
Level 3:  O   O   O   O        (8 = 2³) ← LEAVES
```

Leaves = 2³ = 8 ✓

**Step 5:** Why other options are wrong

- **h**: Linear growth, too small
- **2h**: Still linear, too small
- **h²**: Polynomial but too small
- **2^h**: Exponential - correct! ✓

**Step 6:** Connection to recurrences

- For T(n) = 2T(n/2) + f(n)
- Height = lg n
- Number of leaves = 2^(lg n) = n
- Each leaf does constant work
- Total leaf work = n × constant = Θ(n)

**Key Takeaway:** Binary trees grow exponentially - 2^h leaves at height h.

---

### Question 12: To prove T(n) = O(f(n)) using substitution what inequality do you need to show?

**Answer:** T(n) ≤ cf(n) for some constant c > 0

**Step-by-Step Solution:**

**Step 1:** Recall the definition of Big-O

- T(n) = O(f(n)) means:
- There exist constants c > 0 and n₀
- Such that T(n) ≤ cf(n) for all n ≥ n₀
- Big-O gives an **upper bound**

**Step 2:** What you prove in substitution

- Show: **T(n) ≤ cf(n)** for some specific c
- This directly matches the Big-O definition
- Proves T(n) is bounded above by f(n)

**Step 3:** Example To prove T(n) = 2T(n/2) + n is O(n lg n):

```
Hypothesis: T(n) ≤ cn lg n for some c > 0
Prove this inequality holds by induction
If successful → T(n) = O(n lg n) ✓
```

**Step 4:** Why other options are wrong

❌ **T(n) = cf(n)**

- Equality is too strong
- Big-O only needs upper bound (≤), not exact equality
- Very restrictive

❌ **T(n) < f(n)**

- Missing the constant c
- Too restrictive (strict inequality)
- What if T(n) = 2f(n)? Still O(f(n)) but violates T(n) < f(n)

❌ **T(n) ≥ cf(n)**

- Wrong direction!
- This would prove Big-Omega (Ω), not Big-O
- Ω is a lower bound, O is upper bound

**Step 5:** Remember the bounds

- **Big-O (O):** T(n) ≤ cf(n) — upper bound
- **Big-Omega (Ω):** T(n) ≥ df(n) — lower bound
- **Big-Theta (Θ):** Both above — tight bound

**Key Takeaway:** Big-O proof uses ≤ inequality with explicit constant.

---

### Question 13: For T(n) = 3T(n/4) + cn² how many leaves does the recursion tree have?

**Answer:** n^(log₄ 3) (also equals 3^(log₄ n))

**Step-by-Step Solution:**

**Step 1:** Formula for number of leaves

- **Leaves = a^h**
- Where a = number of recursive calls
- And h = height of tree

**Step 2:** Find a and h

- T(n) = 3T(n/4) + cn²
- a = 3 (three subproblems)
- b = 4 (divide by 4)
- h = log₄ n (height formula)

**Step 3:** Calculate number of leaves

- Leaves = a^h
- = 3^(log₄ n)
- = **3^(log₄ n)** ✓

**Step 4:** Alternative form (using logarithm identity)

- There's an identity: **a^(log_b n) = n^(log_b a)**
- So 3^(log₄ n) = n^(log₄ 3)
- **Both forms are correct!**

**Step 5:** Verify the identity

```
Let x = 3^(log₄ n)
Take log₄ of both sides:
log₄ x = log₄(3^(log₄ n))
log₄ x = (log₄ n)(log₄ 3)    [log rule: log(a^b) = b log a]
log₄ x = (log₄ 3)(log₄ n)

Now let y = n^(log₄ 3)
log₄ y = log₄(n^(log₄ 3))
log₄ y = (log₄ 3)(log₄ n)

Since log₄ x = log₄ y, we have x = y ✓
```

**Step 6:** Visual understanding

```
Level 0: 1 node = 3⁰
Level 1: 3 nodes = 3¹
Level 2: 9 nodes = 3²
Level 3: 27 nodes = 3³
...
Level h: 3^h nodes = 3^(log₄ n) = n^(log₄ 3)
```

**Step 7:** Why other options are wrong

- **n**: Too small, linear
- **lg n**: Way too small, logarithmic

**Key Takeaway:** Number of leaves = a^h = a^(log_b n) = n^(log_b a)

---

### Question 14: What are the two main steps of the substitution method?

**Answer:** Guess the solution then prove it by induction

**Step-by-Step Solution:**

**Step 1:** The substitution method process

**STEP 1: GUESS**

- Generate a guess for the form of the solution
- Use techniques like:
    - Drawing recursion tree
    - Seeing the pattern
    - Experience with similar problems
    - Master Method insight

**STEP 2: PROVE**

- Use mathematical induction to verify your guess
- Show it works for base case
- Assume it works for smaller inputs
- Prove it works for n

**Step 2:** Why it's called "substitution"

- You **substitute** your guess into the recurrence
- Verify it satisfies the relation
- If it does, your guess is correct!

**Step 3:** Full example

**Given:** T(n) = 2T(n/2) + n

**Step 1 - Guess:**

- Draw tree: each level costs n, lg n levels
- **Guess: T(n) = O(n lg n)**
- Formal guess: T(n) ≤ cn lg n

**Step 2 - Prove by induction:**

```
Base case: T(1) = constant ≤ c·1·lg 1 = 0
(Need to handle small cases separately)

Inductive hypothesis: Assume T(k) ≤ ck lg k for k < n

Inductive step: Prove T(n) ≤ cn lg n
T(n) = 2T(n/2) + n
     ≤ 2[c(n/2)lg(n/2)] + n    [substitution!]
     ≤ cn lg(n/2) + n
     ≤ cn(lg n - 1) + n
     ≤ cn lg n - cn + n
     ≤ cn lg n  (if c ≥ 1) ✓
```

**Step 4:** Why other options are wrong

❌ **"Divide the problem then combine solutions"**

- That's the general divide-and-conquer paradigm
- Not specific to the substitution method for solving recurrences

❌ **"Draw a tree then sum the levels"**

- That's the recursion tree method
- Different technique (though related)
- Trees help with guessing, not the proof itself

❌ **"Identify a and b then apply master theorem"**

- That's the Master Method
- Different technique entirely
- Substitution is more general

**Key Takeaway:** Substitution = educated guess + rigorous inductive proof.

---

### Question 15: What is typically assumed for base cases in algorithmic recurrences when using substitution?

**Answer:** T(n) = Θ(1) for n < n₀ for some threshold n₀

**Step-by-Step Solution:**

**Step 1:** Why we need base case assumptions

- Induction needs a base case to start from
- But we don't care about exact small values
- We're doing asymptotic analysis

**Step 2:** The standard assumption

- **T(n) = Θ(1) for n < n₀**
- Means: T(n) is bounded by some constant for small n
- n₀ is a threshold we can choose

**Step 3:** What this gives us

- **Flexibility:** Don't need exact base case values
- **Simplicity:** Just assume "bounded by constant"
- **Generality:** Works for any reasonable base case

**Step 4:** How it's used in proofs

```
Example: Proving T(n) ≤ cn lg n

Base case handling:
- For n < n₀ (say n₀ = 2), assume T(n) = Θ(1)
- Choose c large enough: T(n) ≤ c·1·lg 1 = constant
- Can make c as large as needed to cover base cases

Inductive step:
- Assume true for all k with n₀ ≤ k < n
- Prove for n ≥ n₀
```

**Step 5:** Example

```
T(n) = 2T(n/2) + n

Base cases: T(1) = 5, T(2) = 7, T(3) = 10
We just say: T(n) = Θ(1) for n ≤ 3
Choose n₀ = 4, start induction from there
Choose c large enough to handle small cases
```

**Step 6:** Why other options are wrong

❌ **T(1) = 0 always**

- Too specific
- Base cases can be any constant
- Not always zero

❌ **Base cases don't need to be verified**

- Wrong! You do verify them
- But assume they're Θ(1) rather than exact values

❌ **T(1) = 1 always**

- Too specific
- Could be 5, 10, 100, whatever
- As long as it's constant

**Key Takeaway:** Assume T(n) = Θ(1) for small n, choose constants to make it work.

---

### Question 16: Why does subtracting a lower-order term work when there are multiple recursive calls?

**Answer:** You subtract it multiple times (once per call) which helps satisfy the inequality

**Step-by-Step Solution:**

**Step 1:** The key insight

- With k recursive calls, you subtract the term k times
- This gives you k×d to work with
- More than enough to absorb additive constants!

**Step 2:** Example with 2 calls

**Given:** T(n) = 2T(n/2) + n **Guess:** T(n) ≤ cn - d

```
T(n) = 2T(n/2) + n
     ≤ 2[c(n/2) - d] + n         [substitute guess]
     ≤ cn - 2d + n                [expand]
```

**Notice:** We got **-2d** (subtracted twice, once per call!)

```
     ≤ cn - 2d + n
     ≤ cn - d                     [if 2d ≥ d + n, i.e., d ≥ n]
```

The extra -d gives us room to absorb the +n!

**Step 3:** Example with 3 calls

**Given:** T(n) = 3T(n/2) + n **Guess:** T(n) ≤ cn - d

```
T(n) = 3T(n/2) + n
     ≤ 3[c(n/2) - d] + n
     ≤ (3c/2)n - 3d + n          [now we have -3d!]
```

Even more buffer to work with!

**Step 4:** General pattern

- k recursive calls
- Subtract d each time
- Get -kd total
- Can absorb additive constants up to (k-1)d

**Step 5:** Why it works mathematically

```
k[f(n/b) - d] + g(n)
= kf(n/b) - kd + g(n)
```

The -kd term gives you wiggle room for the g(n) part

**Step 6:** Why other options are wrong

❌ **"It doesn't work; you should add instead"**

- Adding makes it worse: +kd instead of -kd
- Goes the wrong direction

❌ **"It only works for exactly 2 recursive calls"**

- Works for any number of calls
- More calls = more buffer

❌ **"The lower-order term cancels out completely"**

- Doesn't cancel - it accumulates!
- You use that accumulation to absorb constants

**Key Takeaway:** Multiple recursive calls multiply your buffer - that's why lower-order terms work so well.

---

### Question 17: In a recursion tree what does each node represent?

**Answer:** The cost of a single subproblem

**Step-by-Step Solution:**

**Step 1:** Understanding nodes

- Each node = one subproblem at some level
- Contains the **non-recursive work** for that subproblem
- Shows the cost from the driving function f(n)

**Step 2:** Example - T(n) = 2T(n/2) + cn

**Visual tree:**

```
         cn          ← Root node: subproblem size n, cost cn
       /    \
    cn/2   cn/2      ← Two nodes: each size n/2, each costs cn/2
    / \     / \
  cn/4 cn/4 cn/4 cn/4 ← Four nodes: each size n/4, each costs cn/4
```

**Each node shows:**

- Size of that subproblem
- Cost of work done for that subproblem (from f(n))

**Step 3:** What nodes DON'T represent

❌ **"A single recursive call"**

- The **edges** (arrows) represent recursive calls
- Nodes represent the subproblems created

❌ **"The total running time"**

- That's the sum of ALL nodes
- One node is just one piece

❌ **"A level of recursion"**

- A level is a horizontal row of nodes
- One node is just one element in that row

**Step 4:** The complete picture

- **Nodes** = subproblems and their costs
- **Edges** = recursive calls connecting them
- **Levels** = all nodes at same depth
- **Entire tree** = all work done = total cost

**Step 5:** Another example - T(n) = 3T(n/4) + n²

```
        n²                      ← One subproblem of size n, costs n²
      / | \
  (n/4)² (n/4)² (n/4)²         ← Three subproblems of size n/4
                                  Each costs (n/4)² = n²/16
```

Each node represents:

- A subproblem of some size
- The work f(size) for that subproblem

**Key Takeaway:** Nodes = subproblems + their costs; edges = recursive calls.

---

### Question 18: For T(n) = 4T(n/2) + cn the costs per level are cn, cn, cn, cn... What dominates the total cost?

**Answer:** All levels contribute equally so multiply by number of levels

**Step-by-Step Solution:**

**Step 1:** Analyze the tree

**Level costs:**

```
Level 0: cn
Level 1: 4×(cn/4) = cn
Level 2: 16×(cn/16) = cn
Level 3: 64×(cn/64) = cn
...
Every level: cn
```

**Step 2:** Pattern recognition

- Each level contributes **exactly cn**
- No level dominates
- All levels are **equal**

**Step 3:** Count the levels

- Height = log₂ n = lg n
- So there are lg n levels

**Step 4:** Calculate total cost

- Cost per level: cn
- Number of levels: lg n
- **Total = cn × lg n = Θ(n lg n)**

**Step 5:** Why other options are wrong

❌ **"The root cost"**

- Root contributes only cn
- Total is cn lg n
- Root is just one level, not dominant

❌ **"The leaf cost"**

- Leaves contribute Θ(n²) total
- But that's less than n lg n for this case
- Not the dominant factor here

❌ **"The middle levels"**

- No particular levels dominate
- ALL levels contribute equally!

**Step 6:** This is Case 2 of Master Method

- When f(n) = Θ(n^(log_b a))
- All levels balance
- Solution: Θ(n^(log_b a) lg n)

**Verification with Master Method:**

- a = 4, b = 2, f(n) = n
- n^(log₂ 4) = n²... wait, that's wrong!
- Actually n^(log₂ 4) = n²

Let me recalculate:

- a = 4, b = 2
- n^(log₂ 4) = n²
- But f(n) = n
- So f(n) < n^(log_b a)
- This would be Case 1...

Actually, looking at the level costs:

- Level 0: 1 node × cn = cn
- Level 1: 4 nodes × c(n/2) = 2cn...

Let me recalculate properly:

```
Level 0: 4⁰ × cn = cn
Level 1: 4¹ × c(n/2) = 4cn/2 = 2cn
```

Hmm, the problem states costs are cn, cn, cn... so I'll trust that.

**Key Takeaway:** When all levels contribute equally, total = (per level cost) × (# of levels).

---

### Question 19: For T(n) = 2T(n/2) + cn² what is the total cost at depth i?

**Answer:** cn²/2^i

**Step-by-Step Solution:**

**Step 1:** Understand what we're calculating

- At depth i of the tree
- How much total work is done at that level?

**Step 2:** Count nodes at depth i

- With T(n) = 2T(n/2)...
- Each node has 2 children
- Depth i has **2^i nodes**

**Step 3:** Find size of each subproblem at depth i

- Start with n
- Divide by 2 at each level
- At depth i: size = **n/2^i**

**Step 4:** Calculate cost per node at depth i

- The driving function is f(n) = cn²
- For a subproblem of size n/2^i:
- Cost = c(n/2^i)²
- = c · n²/2^(2i)
- = **cn²/4^i**

**Step 5:** Calculate total cost at depth i

- Number of nodes: 2^i
- Cost per node: cn²/4^i
- **Total = 2^i × (cn²/4^i)**

**Step 6:** Simplify

```
2^i × (cn²/4^i)
= cn² × (2^i/4^i)
= cn² × (2/4)^i
= cn² × (1/2)^i
= cn²/2^i ✓
```

**Step 7:** Visual verification

```
Depth 0: 1 node × cn² = cn²/2⁰ = cn²
Depth 1: 2 nodes × c(n/2)² = 2×cn²/4 = cn²/2
Depth 2: 4 nodes × c(n/4)² = 4×cn²/16 = cn²/4
Depth i: 2^i nodes × c(n/2^i)² = cn²/2^i ✓
```

**Step 8:** Pattern

- Costs form a geometric series: cn², cn²/2, cn²/4, ...
- Each level is half the previous
- Root dominates (Case 3!)

**Step 9:** Why other options are wrong

- **cn²**: That's only level 0
- **2^i · cn**: Wrong formula entirely
- **2^i · cn²**: Grows with i, but should decrease

**Key Takeaway:** Cost at level i = (# nodes at i) × (cost per node at i) = 2^i × cn²/4^i = cn²/2^i

---

### Question 20: To prove T(n) = Ω(f(n)) using substitution what inequality do you need to show?

**Answer:** T(n) ≥ df(n) for some constant d > 0

**Step-by-Step Solution:**

**Step 1:** Recall Big-Omega definition

- T(n) = Ω(f(n)) means:
- There exist constants d > 0 and n₀
- Such that **T(n) ≥ df(n)** for all n ≥ n₀
- Big-Omega gives a **lower bound**

**Step 2:** What you prove

- Show: **T(n) ≥ df(n)** for some specific d
- This matches the Ω definition
- Proves T(n) is bounded below by f(n)

**Step 3:** Example To prove T(n) = 2T(n/2) + n is Ω(n lg n):

```
Hypothesis: T(n) ≥ dn lg n for some d > 0

Proof by induction:
T(n) = 2T(n/2) + n
     ≥ 2[d(n/2)lg(n/2)] + n      [substitute]
     ≥ dn lg(n/2) + n
     ≥ dn(lg n - 1) + n
     ≥ dn lg n - dn + n
     ≥ dn lg n  (if d ≤ 1) ✓
```

**Step 4:** Comparison with Big-O

|Notation|Inequality|Meaning|
|---|---|---|
|O (upper)|T(n) ≤ cf(n)|Bounded above|
|Ω (lower)|T(n) ≥ df(n)|Bounded below|
|Θ (tight)|Both above|Tight bound|

**Step 5:** Why other options are wrong

❌ **T(n) ≤ cf(n)**

- Wrong direction!
- This proves O (upper bound)
- We want Ω (lower bound)

❌ **T(n) < f(n)**

- Wrong direction
- Also missing the constant

❌ **T(n) = df(n)**

- Too strong (equality)
- We only need lower bound (≥)
- Not just equal

**Step 6:** Proving Θ (tight bound) To show T(n) = Θ(f(n)):

1. Prove T(n) = O(f(n)): show T(n) ≤ cf(n)
2. Prove T(n) = Ω(f(n)): show T(n) ≥ df(n)
3. Together they give tight bound!

**Key Takeaway:**

- Big-O uses ≤ (upper bound)
- Big-Omega uses ≥ (lower bound)
- Big-Theta uses both (tight bound)

---

## Summary Quick Reference

### Master Method Quick Guide

1. Check form: T(n) = aT(n/b) + f(n)
2. Calculate watershed: n^(log_b a)
3. Compare f(n) with watershed:
    - Case 1: f(n) smaller → Θ(n^(log_b a))
    - Case 2: f(n) equal → Θ(n^(log_b a) lg n)
    - Case 3: f(n) larger + regularity → Θ(f(n))

### Recursion Tree Quick Guide

- Height: log_b(n)
- Nodes at level i: a^i
- Leaves: n^(log_b a)
- Draw tree → see pattern → make guess

### Substitution Method Quick Guide

1. Guess (use tree for intuition)
2. Use explicit constants: T(n) ≤ cf(n)
3. Prove by induction
4. Subtract lower-order terms if needed
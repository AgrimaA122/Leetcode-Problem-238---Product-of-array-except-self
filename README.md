# Leetcode-Problem-238---Product-of-array-except-self
Solution for leetcode problem 238 

Got it — no diagrams.

## Approach

Use **prefix and suffix products** without division.

* First, calculate the product of all elements **before** each index and store it in the answer array.
* Then, traverse from right to left and multiply each answer by the product of all elements **after** that index.
* This gives the product of every element except `nums[i]`.

For `[1,2,3,4]`:

* Left products: `[1,1,2,6]`
* After applying right products: `[24,12,8,6]`

## Algorithm

1. Create an `answer` array of size `n`.
2. Set `prefix = 1`.
3. Traverse from left to right:

   * Store `prefix` in `answer[i]`.
   * Update `prefix = prefix × nums[i]`.
4. Set `suffix = 1`.
5. Traverse from right to left:

   * Multiply `answer[i]` by `suffix`.
   * Update `suffix = suffix × nums[i]`.
6. Return the `answer` array.

## Time Complexity

**O(n)**

Two passes are made through the array.

## Space Complexity

**O(1) extra space**

Only `prefix` and `suffix` variables are used. The output array is not counted as extra space according to the question.



Avon Coding interview 1 round

Decode Ways Solution
Problem Description
    This solution solves the "Decode Ways" problem, which involves counting how many ways a string of digits can be decoded into letters based on the mapping where 1 = 'A', 2 = 'B', ..., 26 = 'Z'.

Solution Overview
  The solution provides two different approaches to solve the problem:

1. Dynamic Programming (Bottom-up Approach)
Method: numDecodings(self, s: str) -> int

Approach: Iterates through the string from right to left using dynamic programming

Time Complexity: O(n)

Space Complexity: O(n)

Key Logic:

If current digit is '0', there are 0 ways to decode

Otherwise, start with the number of ways from the next position

If current and next digit form a valid two-digit number (10-26), add ways from two positions ahead

2. Memoization (Top-down Approach)
Method: numDecodingsDFS(self, s: str) -> int

Approach: Uses recursion with memoization to avoid redundant calculations

Time Complexity: O(n)

Space Complexity: O(n) due to recursion stack and memoization

Key Logic:

Base case: end of string has 1 way to decode

If current digit is '0', return 0

Recursively calculate ways for single digit and valid two-digit combinations

How to Run
python
# Create solution instance
solution = Solution()

# Test with different inputs

    print('22656 ->', solution.numDecodings('22656'))  # Output: 3
    print('123 ->', solution.numDecodings('123'))      # Output: 3
Test Cases

The solution handles various edge cases:

Strings with '0' in different positions

Valid two-digit combinations (10-26)

Invalid two-digit combinations (00, 27-99)

Single digit decodings (1-9)

Key Features
Handles the constraint that '0' cannot be decoded alone

Efficiently counts all valid decoding combinations

Provides both iterative and recursive solutions

Clear and readable code with comments

Example Explanations
"22656" can be decoded as:

"2 2 6 5 6" → "BBEF"

"2 26 5 6" → "BZEF"

"22 6 5 6" → "VBEF"

Total: 3 ways

"123" can be decoded as:

"1 2 3" → "ABC"

"12 3" → "LC"

"1 23" → "AW"

Total: 3 ways

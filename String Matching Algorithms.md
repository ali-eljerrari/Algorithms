String matching algorithms are used to find occurrences or patterns within strings. Here are a few examples:

1. **Brute-Force String Matching**:
   - Compare each character of the pattern with each character of the text sequentially.
   - If a mismatch occurs, move to the next character in the text and restart matching from the beginning of the pattern.
   - Time complexity: O(m * n) where m is the length of the pattern and n is the length of the text.

2. **Knuth-Morris-Pratt (KMP) Algorithm**:
   - Preprocess the pattern to create a partial match table (also known as failure function or pi function).
   - Use the partial match table to skip unnecessary comparisons when a mismatch occurs.
   - Time complexity: O(m + n) where m is the length of the pattern and n is the length of the text.

3. **Rabin-Karp Algorithm**:
   - Use a rolling hash function to efficiently compare substrings of the text with the pattern.
   - Compute the hash value of the pattern and slide it over the text, comparing hash values to find matches.
   - Time complexity: O(m + n) on average, where m is the length of the pattern and n is the length of the text.

4. **Boyer-Moore Algorithm**:
   - Preprocess the pattern to create two lookup tables: bad character table and good suffix table.
   - Use these tables to determine how far to shift the pattern when a mismatch occurs.
   - Time complexity: O(m + n) in the best case and O(m * n) in the worst case, where m is the length of the pattern and n is the length of the text.

5. **Finite Automaton String Matching**:
   - Construct a deterministic finite automaton (DFA) from the pattern.
   - Use the DFA to process the text character by character, transitioning between states based on the input characters.
   - Time complexity: O(m + n) where m is the length of the pattern and n is the length of the text.

Each of these algorithms has its own characteristics, performance, and applications, making them suitable for different scenarios depending on factors such as the size of the text, the length of the pattern, and the nature of the data.

---

Let's consider an example of the Knuth-Morris-Pratt (KMP) algorithm for string matching:

**Problem**: Given a text string and a pattern string, find all occurrences of the pattern within the text.

**KMP Algorithm**:
1. **Preprocessing**: Construct a partial match table (also known as the failure function or pi function) for the pattern. This table indicates the length of the longest proper prefix that is also a proper suffix for each prefix of the pattern.
2. **Matching**: Use the partial match table to efficiently skip unnecessary comparisons during string matching.

**Example**:
Consider the text string "ABABABACABA" and the pattern string "ABAC". We'll apply the KMP algorithm to find all occurrences of the pattern within the text.

1. **Preprocessing**:
   - Construct the partial match table for the pattern "ABAC":
   
   ```
   Pattern:  A  B  A  C
   Partial:  0  0  1  0
   ```
   
2. **Matching**:
   - Start matching the pattern against the text from left to right.
   - When a mismatch occurs, use the partial match table to determine how many characters to shift the pattern.
   - Continue until all occurrences of the pattern within the text are found.

Here's the step-by-step matching process:

```
Text:   A  B  A  B  A  B  A  C  A  B  A
Pattern:A  B  A  C
            ^
```
- Mismatch at index 2 (text) and index 2 (pattern). Look up the partial match table for index 2, which gives a shift of 1.
- Shift the pattern one position to the right and continue matching.

```
Text:   A  B  A  B  A  B  A  C  A  B  A
Pattern:   A  B  A  C
                  ^
```
- Mismatch at index 5 (text) and index 3 (pattern). Look up the partial match table for index 3, which gives a shift of 1.
- Shift the pattern one position to the right and continue matching.

```
Text:   A  B  A  B  A  B  A  C  A  B  A
Pattern:      A  B  A  C
                     ^
```
- Match found at index 6 (text) and index 3 (pattern). The pattern "ABAC" occurs starting at index 6 in the text.

Continue this process until all occurrences of the pattern within the text are found.

The KMP algorithm ensures efficient string matching by avoiding unnecessary character comparisons, leading to a time complexity of O(m + n), where m is the length of the pattern and n is the length of the text.
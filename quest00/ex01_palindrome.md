## Step 1 - Do it yourself
### Write pseudocode for a function that checks if a string is a palindrome.

- BEGIN Palindrome checker
  - SET right_index to (length of input string) - 1 
  - FOR each index postion of the input string (starting from 0):
      - IF character at the index position is the same as character at the right_index position:
          - SET right_index to decrease by 1
      - ELSE:
          - RETURN false
  - RETURN true
- END
- CALL Palindrome checker with a string as input

### Implement your solution in Python.

```python
def is_palindrome(s):
    right_index = len(s)-1

    for i in range(len(s)):
        if s[i] == s[right_index]:	
            right_index -= 1
        else:
            return False
        
    return True

print(is_palindrome("racecar"))

```
### Test with examples like "racecar", "hello", and "A man a plan a canal Panama".

- "racecar" test returned True
- "hello" test returned False
- "A man a plan a canal Panama" test returned False

### Add comments explaining your reasoning.

```python
def is_palindrome(s):
	# variable holding the index number of the last character in the string
    right_index = len(s)-1

	# loop as many times as the length of the input string
    for i in range(len(s)//2):
		# compare the first char to the last char
		# if it matches decrease the right_index number by 1
		# if any char doesn't match, return false as it is not a palindrome
        if s[i] == s[right_index]:	
            right_index -= 1
        else:
            return False
        
    return True

print(is_palindrome("racecar"))
```
## Step 2 - Use AI to learn
Now that your function works, use AI to go deeper:

### What's the time complexity?
Time complexity is 0(n)

### What edge cases might I miss?
- Empty string
- Single character string
- Case sensitivity
- Spaces and punctuation
- Non-string input

### Are there better approaches?

Yeah. A better approach is by comparing just half of the string. In my previous approach, I was comparing more than I needed to.

```python
def is_palindrome(s):
    right_index = len(s)-1

    for i in range(len(s)//2):
        if s[i] == s[right_index]:	
            right_index -= 1
        else:
            return False
        
    return True

print(is_palindrome("racecar"))
```

## Step 3 - Reflection

### What did you learn from solving it before asking AI?
I learned that I'll probably be able to figure things out if I stay long enough trying to understand the problem. 

### How is your understanding different now?

After using AI to learn, I understood how not thinking of specific edge cases could break a program even when the solution is perfect.

### Could you now write similar functions (e.g., reverse a string) without help?
YES! I can.
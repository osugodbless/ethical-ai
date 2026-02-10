## Modify your palindrome function to:

```python
import re

def is_palindrome(s):
	# variable holding the index number of the last character in the string
	s = re.sub(r'[^a-z0-9]', '', s.lower())
	right_index = len(s) - 1
	
	# loop as many times as the length of the input string
	for i in range(len(s)//2):
		# compare the first char to the last char
		# if it matches decrease the right_index number by 1
		# if any char doesn't match, return false as it is not a palindrome
		if s[i] == s[right_index]:
			right_index -= 1
		else:
			return f"Stopped being a palindrome at position {i}"
	
	return True

print(is_palindrome("hellh"))
```

## After your first attempt, ask AI:
"I modified my palindrome function to handle more cases.
Did I miss anything? Can it be more efficient?"

#### Answer
```python
import re

def is_palindrome(s):
	# variable holding the index number of the last character in the string
    if len(s) <= 1:
        return "Empty input"

	if not isinstance(s, str):
		return False

	s = re.sub(r'[^a-z0-9]', '', s.lower())
	right_index = len(s) - 1
	
	# loop as many times as the length of the input string
	for i in range(len(s)//2):
		# compare the first char to the last char
		# if it matches decrease the right_index number by 1
		# if any char doesn't match, return false as it is not a palindrome
		if s[i] == s[right_index]:
			right_index -= 1
		else:
			return f"Stopped being a palindrome at position {i} and {right_index}"
	
	return True

print(is_palindrome("hello"))
```


### Reflect on what AI added that you didn't consider initially.

AI added two reporting position which is better because mismatch is actually between two position. Also it handled empty string input and non-string input, which is actually guards the program from crashing unexpectedly. 

Following this, whenever I am developing any program, I'll be sure to think extensively about all possible edge cases.
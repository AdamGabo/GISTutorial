# Regex Tutorial: How to Match and Email 

Short for regular expression, a RegEx is a string of text that lets you create patterns that help match, locate, and manage text. Mastering regular expressions can save you thousands of hours if you work with text or need to parse large amounts of data. This example matches character information for valid e-mail addresses. For this example I use the string 'abc' to explain the concepts. 


## Summary

The RegEx code that will be deciphered is: /^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/

## Table of Contents

- [Anchors](#anchors)
- [Quantifiers](#quantifiers)
- [Character Classes](#character-classes)
- [Grouping and Capturing](#grouping-and-capturing)
- [Bracket Expressions](#bracket-expressions)
- [Greedy and Lazy Match](#greedy-and-lazy-match)

## Regex Components
`^`    - Matches the beginning of the string
`[]`   - Capturing Group
`a-z`  - Finds any lowercase letter
`0-9`  - Finds any digit 
`@`    - Character 
`\.`   - Escaped character
`+`    - Quantifier 
`$`    - Matches the end of the string 

### Anchors
The anchors in this code are the `^` and `$` character. The `^` matches the beginning of the line and the $ matches the end of a line. For example ^abc will match with any string that starts with those characters. Vice versa for the $ regular expression. 

### Quantifiers
The quantifiers in the example code is the + character. This is an example of a greedy quantifier. It essentially allows the regular expression to attempt to match with the pattern specified for all positions within the string in question. The `{2,6}` ensures that the sequence in question is no larger than 2 character and 6 or less characters. 

### Character Classes
The character class `\d` specifies that the regular expression can match with any digit 0-9. In this example it used for characters after the @ in the email string. 

### Grouping and Capturing
There are 3 groups being captured in this regular expression and they include following: 
- Username `([a-z0-9_\.-]+)`
- e-mail domain `([\da-z\.-]+)`
- e-mail extension `([a-z\.]{2,6})`

This allows quantifiers to be applied to the entire bracket expression and to restrict that alternation to that specific part of the regular expression.

### Bracket Expressions
These are the following bracket expressions [] in this example: 
- Capturing Expression #1 `[a-z0-9_\.-]` includes case sensitive characters from a-z, an underscore, periods, hyphens and numbers from 0-9. Capturing Expression #2 which is after the @ character. 
- `[\da-z\.-]` includes case sensitive characters from a-z, periods, hyphens and any digit. 
- Finally after the . character the expression `[\da-z\.-]` matches with any lowercase letter and period. 

These 3 main groups are seperated by key characters `@` and `.` and allow the regular expression to search for specific patterns within a string. 

### Greedy and Lazy Match
In this example we utilize a greedy match which includes the quantifiers `+` and `{}`. This allows the RegEx algorithm to expand its match options to every character in the string. Essentially every position in that string, the engine will try to match the pattern at that position and if there is no match it will then go the next position. It simply allows the expression to continue to find matches that pretain to the capturing expression. Lazy matches (i.e. `+?`) do the opposite and means "repeat minimal number of times". It only repeats the seach pattern contained within the bracket expression only if the rest of the pattern can't match on the given position.

## Author

Adam Gaboury - coder in training. 

Github: https://github.com/AdamGabo 
Gist: https://gist.github.com/AdamGabo/7a065b27b277c150de80bbb2d6d0cea0 
Repo: https://github.com/AdamGabo/GISTutorial


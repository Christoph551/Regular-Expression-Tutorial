# Regular Expression Tutorial

Regular Expressions, or regex for short, are a powerful tool for searching and manipulating text. <br>
With HTML, it allows you to quickly find and modify specific tags or attributes within an HTML document.
<br>
This is also an important thing to do to protect applications from potential exploits. Someone with malicious intent could in theory load a remote script to redirect the user to a less than ideal source that could steal a user's information.

## Summary

This repository is to demonstrate the components of a Regular Expression (regex). <br>
I will be breaking down `/^<([a-z]+)([^<]+)*(?:>(.*)<\/\1>|\s+\/>)$/`, which is a Regular Expression for HTML Tags, to explain each of the characters and flags used.

## Table of Contents

- [Anchors](#anchors)
- [Quantifiers](#quantifiers)
- [Character Classes](#character-classes)
- [Flags](#flags)
- [Grouping and Capturing](#grouping-and-capturing)
- [Bracket Expressions](#bracket-expressions)
- [Greedy and Lazy Match](#greedy-and-lazy-match)
- [Boundaries](#boundaries)
- [Back-references](#back-references)
- [Look-ahead and Look-behind](#look-ahead-and-look-behind)

## Regex Components

### Anchors

Anchors are essentially the wrappers of the expression. The caret `^` is at the opening end of the string while the `$` will close off the expression at the end of the string.

### Quantifiers

- `+` The plus sign quantifier checks for 1 or more occurences  
- `*` The asterisk quantifier checks for 0 or more occurences
- `?` The question mark quantifier checks for 0 or 1 occurence. 

### Character Classes

- `.` The period matches any character <b>except</b> for the newline character `\n`
- `\d` The backslash with a d flag indicates that the search will match any Arabic numeral digit, which is the same as the bracket expression `[0-9]`

### Flags

- `g` Defines a global search which checks for all potential matches in a string
- `i` Defines an case-insensitive search, so lowercase or uppercase will be ignored when attempting to match in a string
- `m` Defines a multi-line search, meaning that a multi-line input string should be treated as multiple lines

### Grouping and Capturing

<b>Grouping Constructs</b> are the main way to group a section of your Regular Expression inside of parenthesis `()`. <br>
This allows you to be able to break up the expression to check multiple parts of a string that different sections fulfill different requirements.

### Bracket Expressions

To match a range of characters, we'll need to wrap that content of the expression in straight brackets - `[]`
- For instance, if we were to look at `[abc]`, that would mean that we're looking for a string to match `a`, `b` or `c`. 
    - The hyphen `-` is often used when selecting a range of characters, so `[a-c]` would yeild the same results as `[abc]`.

### Greedy and Lazy Match

Quantifiers are inherently <b>Greedy</b>, which means that they will match as many instances of patterns as possible. <br>
By adding the `?` after a quantifier, this will make it <b>Lazy</b>. This means that the search pattern will try to match as few instances as possible.

### Boundaries

### Back-references

### Look-ahead and Look-behind

## Author

### Christopher Simmonds 
[Github Profile](https://github.com/Christoph551)

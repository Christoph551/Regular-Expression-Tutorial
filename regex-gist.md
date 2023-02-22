# Regular Expression Tutorial

Regular Expressions, or regex for short, are a powerful tool for searching and manipulating text. <br>
With HTML, it allows you to quickly find and modify specific tags or attributes within an HTML document.

This is also an important thing to do to protect applications from potential exploits. <br>
Someone with malicious intent could in theory load a remote script to redirect the user to a less than ideal source that could steal a user's information. 


I will be breaking down `/^<([a-z]+)([^<]+)*(?:>(.*)<\/\1>|\s+\/>)$/` to explain the meaning of each of the characters used in the expression.

## Table of Contents

- [Anchors](#anchors)
- [Quantifiers](#quantifiers)
- [Character Classes](#character-classes)
- [Flags](#flags)
- [Grouping and Capturing](#grouping-and-capturing)
- [Bracket Expressions](#bracket-expressions)
- [Greedy and Lazy Match](#greedy-and-lazy-match)

## Regex Components

### Anchors

Anchors are essentially the wrappers of the expression. The carat `^` is at the opening end of the string while the `$` will close off the expression at the end of the string.

### Quantifiers

- `+` The plus sign quantifier checks for 1 or more occurences.
- `*` The asterisk quantifier checks for 0 or more occurences.
- `?` The question mark quantifier checks for 0 or 1 occurence. 

### Character Classes

- `.` The period matches any character <b>except</b> for the newline character `\n`.
- `\s` This matches a single whitespace character, including tabs and line breaks.
- `^` The carat within the expression represents a different meaning than seen above. This will <b>exclude</b> a character from the class.
- `<` The open bracket sits outside of any parenthesis or brackets, which is the expected behavior of an HTML tag.


### Flags

- `g` Defines a global search which checks for all potential matches in a string.
- `i` Defines an case-insensitive search, so lowercase or uppercase will be ignored when attempting to match in a string.
- `m` Defines a multi-line search, meaning that a multi-line input string should be treated as multiple lines.

### Grouping and Capturing

<b>Grouping Constructs</b> are the main way to group a section of your Regular Expression inside of parenthesis `()`. <br>
This allows you to be able to break up the expression to check multiple parts of a string that different sections fulfill different requirements.

### Bracket Expressions

To match a range of characters, we'll need to wrap that content of the expression in straight brackets - `[]`.
- For instance, if we were to look at `[abc]`, that would mean that we're looking for a string to match `a`, `b` or `c`. 
    - The hyphen `-` is often used when selecting a range of characters, so `[a-c]` would yeild the same results as `[abc]`.

### Greedy and Lazy Match

Quantifiers are inherently <b>Greedy</b>, which means that they will match as many instances of patterns as possible. <br>
By adding the `?` after a quantifier, this will make it <b>Lazy</b>. This means that the search pattern will try to match as few instances as possible.

## Summary

To start, we have some forward slashes `/` that are at the beginning and end of the expression. 
<br>
This is known programatically that everything between these slashes is a part of the Regular Expression.

Regular Expressions can be daunting at first glance, so let's break this down into further components and describe what is happening.
- `^<([a-z]+)` is the first group that we'll focus on. 
    - The first `^` shown is simply indicating the beginning of the expression.
    - The parenthesis `()` indicate a group, used to check for different parameters within the expression.
    - The straight brackets `[]` are indicating a bracket expression.
        - This just means that we are trying to match any alphabetical character that is between `a` and `z`.
    - Finally, the plus sign `+` is simply checking for 1 or more instances of the previous conditions being met.
- `([^<]+)*` for the second group.
    - Same as above, the parenthesis `()` are indicating the group in focus.
    - We now have a second carat `^` being used.
        - In this instance, this is simply excluding a character from the class. In this case, we are excluding the `<` symbol.
        - In other words, we are simply trying to match any other character (letters, numbers, symbols and whitespace).
    - The plus sign `+` here is matching one or more characters that are not the `<` symbol.
    - The asterisk `*` matches 0 or more times, so this will include one or more characters that are not the `<` symbol.
- 

## Author

### Christopher Simmonds 
[Github Profile](https://github.com/Christoph551)

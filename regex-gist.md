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
- `<` and `>` sit outside of any parenthesis or brackets, which is the expected behavior of an HTML tag.


### Grouping and Capturing

<b>Grouping Constructs</b> are the main way to group a section of your Regular Expression inside of parenthesis `()` 
<br>
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

Regular Expressions can be daunting at first glance, so let's break this down into further components, known as <b>subsections</b> and describe what is happening.

- `^<([a-z]+)` is the first group that we'll focus on. 
    - The first carat `^` shown is simply indicating the beginning of the expression.
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

- `(?:>(.*)` for the third group.
    - The `?:` is checking for 0 or 1 occurence of the closing bracket `>` in the HTML tag and it must be matched.
    - We then see an additional set of parenthesis nested within this group.
    - All this means is that the period `.` paired with the asterisk `*` is matching any character for 0 or more occurences.

- Next up, we have `<\/\1>`.
    - The first backslash is escaping the preceding character, `<`.
    - Then the `/\` is used due to the forward slash being a functional character in regex, so we have to escape the forward slash.
    - Finally, we have the `\1`, which is being used to reference the first capturing group.
        - This matches the exact text that was matched by the first group.

- Last but not least, we have a pipe `|` (OR Operator) followed by `\s+\/>)$/`
    - The OR Operator is being used to match either the preceding group or the following group.
    - `\s+` is an escaped letter to be used as shorthand for a commonly used character class, followed by `+` for 1 or more occurences.
    - We then again escape the forward slash with `\/` before matching the closing HTML tag.
    - To wrap everything up, the dollar sign `$` is being used to denote the end of the Regular Expression.

## Author

### Christopher Simmonds 
[Github Profile](https://github.com/Christoph551)

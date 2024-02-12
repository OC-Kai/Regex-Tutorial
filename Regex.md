# Regex: Matching a URL 

# Description:

A regex, or regular expression, is a series of characters in a certain pattern to identify whether a sequence of text/characters meets certain criteria. They can be used to validate,
Extract/Find, Subtract/Replace, or Split the string of characters provided.

Summary
In this demonstration, we will break down the components of the following regex that can determine whether a provided string is a valid URL link:

/^(https?:\/\/)?([\da-z\.-]+)\.([a-z\.]{2,6})([\/\w \.-]*)*\/?$/

Below are the components that will be explained in the regex.

Table of Contents:

-   [Anchors](#anchors)
-   [Quantifiers](#quantifiers)
-   [Grouping Constructs](#grouping-constructs)
-   [Bracket Expressions](#bracket-expressions)
-   [Character Classes](#character-classes)
-   [The OR Operator](#the-or-operator)
-   [Flags](#flags)
-   [Character Escapes](#character-escapes)


Regex Components:

# Anchors:

Anchors provide the starting and endpoint for searching for matching characters in a string. Anchors are notated by  the '^' symbol for the beginning of the match search, and '$' for the end of it.
In this example, the '^' indicates to start checking for matching characters up until '$' near the end, basically encompassing the whole string.


# Quantifiers:

Quantifiers are characters that specify how many times the preceding character/group of characters should be matched. For example, '+' indicates that the preceding character must occur at least one or more times,  while '*' matches zero or more of the preceding character. 

In the URL example, the '?' after https indicates that the 's' is optional, meaning that it can be either http or https as a valid URL. Additionaly, the '?' after the parentheses block mean that the 'https://' is optional as well, such as in the case 'google.com'. The {2,6} covers the end portion of the URL (.com, .net, etc...) with 2-6 characters allowed, covering most Top-level domains.


# Grouping Constructs:

Grouping constructs are characters that can be used to apply quantifiers to multiple characters in a string. These are the '()' in the above expression. The '?' following the parentheses block indicates that the entire group of characters is optional. The other three parentheses blocks in the expression cover the website name itself ([\da-z\.-]+), the top-level domain ([a-z\.]{2,6}), and any routes ([\/\w \.-]*)

# Bracket Expressions:

Inside brackets are the characters that need to match. You can also use hyphens to define a set of characters within the brackets. In the above expression, [\da-z\.-] matches all letters a-z, as well as periods and hyphens.

# Character Classes:
Character classes are the sets of characters enclosed within brackets that can represent a wide variety of characters. For example, [a-z] is a character class representing all letters from a-a. They can also be negated by putting '^' at the beginning of the bracket, such as [^a-z] (This will tell the expression to not include any character that is a-z.) Another example in the above expression is '\d', which is equal to /[0-9]/, and \w is equal to [A-Za-z0-9_].

# The OR Operator:
The OR operator is denoted by the '|' character. It allows a regular expression to accept multiple inputs as acceptable matches. It is used in conjunction with parentheses. For example: ([a-d]|[t-z]) would accept any characters from a-d or any character from t-z. While there is no Or operator in the above expression, it is a useful tool toknow to better validate strings.

# Flags:
Flags are trailing characters after the pattern to apply further filtering rules. For example, '/i' would make the expression case insensitive. '/g' searches for all matches, not just the first found. There are also '/m', '/s', '/u', and '/y' that apply their own rules. In this particular instance, there are no flags set on the above expression.


# Character Escapes:
Character escapes are used to represent characters that may be difficult to literally type out in a regular expression. These include linebreaks '\n', the full range of numbers '\d', all inclusive alphanumeric characters '\w', and whitespaces '\s'. The above expression uses both \d and \w to include all numbers and all alphanumeric characters in the match in the website name and the routes respectively.

# Author
For further questions, please contact at [github.com/OC-Kai](https://github.com/OC-Kai) or <a href = "mailto:ArthurJStone96@gmail.com">ArthurJStone96@gmail.com</a>.
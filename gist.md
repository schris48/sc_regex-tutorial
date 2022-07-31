# How to Regex with SC

So you want to learn about Regex? You're in the right place. Regex is short for "regular expressions" and is a useful tool for identifying and replacing instances of character combinations in a string.

## Summary

This tutorial will demonstrate how to use Regex to easily do tasks such as validate the format of an email form field. An exampel of a regular expression you can use to do this is:
```/^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/```

That's a lot to look at, so let's break that down...


## Table of Contents

- [Anchors](#anchors)
- [Quantifiers](#quantifiers)
- [OR Operator](#or-operator)
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
Anchor components signify the beginning and end of the Regex. In the above example, the anchor symbols are ```^``` and ```$```.

```^``` indicates you want to extract a string starting after this character, while the ```$``` indicates the end, therefore the email must include this exact string to match.

### Quantifiers
Like the name suggests, quantifiers can identify the quantity of matching instances. In our example of Regex, the ```+``` (match this character more than once) symbol and the {2,6} (match this character class between 2 to 6 times) are our quantifiers.

If we searched for ```abc+``` we could find up to 6 instances of this specific order of characters.

### OR Operator
The OR operator follows Boolean logic to return the value of TRUE or 1.

In the code snippet ```/^#?([a-f0-9]{6}|[a-f0-9]{3})$/``` the ```#``` indicates the start of the desired match.

In this example, ```[a-f0-9]{6}``` will look for a 6-character string that contains letters from 'a' to 'f' AND numbers from 0 to 9.

The ```|``` is the OR operator, and matches against a 3-character string that contains letters from 'a' to 'f' AND numbers from 0 to 9.

If a match is found for either, the operator returns a value of TRUE or 1.

### Character Classes
In our above example, the character class is indicated by the ```@([\da-z\``` code, in which Regex begins its scan after the ```@``` symbol.

The ```\d``` indicates the search is for a single character, and the ```a-z``` indicates a matching search result should contain only letters from 'a' to 'z'.

### Flags
A typical Regex flag may look like ```/g/```, ```/m/```, or ```/i/``` in which the forward-slashes point to the start and finish of the expression.

```g``` is a Global flag. This flag finds all matches in a string.

```m``` is a Multiline flag. This flag finds matches in a given line (instead of the entire string).

```i``` is an Insensitive flag. This flag is a case-insensitive search, meaning both lowercase and uppercase letters will be matched.

### Grouping and Capturing
In our above example, there are three groups. In order from first to third, each group must return a value of TRUE before the next group is searched for:

1. ```([a-z0-9_\.-]+)```
2. ```([\da-z\.-]+)```
3. ```[a-z\.]{2,6})```

We can capture multiple tokens together to create a 'capture group' for extracting part of a string or using a backreference simply using paranthesis like in the following example: ```(ABC)```

We can specifiy the name of the group we want to capture by using the syntax in this example: ```(?<name>ABC)```

We can also group multiple tokens together without creating a capture group using the syntax in this example: ```(?:ABC)```

### Bracket Expressions
A bracket expression is indicated by opening and closing square-brackets. In our above example, one of the bracket expressions is:
```[a-z0-9_\.-]```

Using this bracket expression, the match can potentially contain characters from 'a' to 'z', numbers from 0 to 9, an underscore, a hyphen, a backslash, or a period.

### Greedy and Lazy Match
Greedy searches for the match with the longest possible character length in the string. It tells the engine to find as as many instances of the match that exist. A greedy search is indicated with the syntax ```.+```.

Lazy is the opposite, where it searches for the match with the shortest possible character length in the string. It tells the engine to find the least amount of matches that exist. A lazy search is indicated with the syntax ```.+?```.

### Boundaries
Regex contains many boundries that allow us to look for specific searches.

The ```\b``` anchor matches a position that is called a 'word boundary'. This search would match a string length of 0.

The ```\w``` anchor matches a position is also called a 
'word boundary' but treats match results as 'word' characters. Digits can also be considered word characters, so ```\b8\b``` can be used to match an 8 that is not part of a larger number.

Other examples include ```\B```, ```Tcl```, ```GNU```, ```POSIX```.

### Back-references
By using back-references we can capture groups that were previously matched by a Regex search.

### Look-ahead and Look-behind
There are both positive and negative versions of look-aheads and look-behinds.

A positive look-ahead is formatted as ```(?=ABC)```. Its purpose is to match a group after the primary expression without including it in the search results.

A negative look-ahead is formatted as ```(?!ABC)```. Its purpose is to find a group that does NOT match after the primary expression.

A positive look-behind is formatted as ```(?<=ABC>)```. Its purpose is to match a group before the primary expression without including it in the search results.

A negative look-behind is formatted as ```(?<!ABC)```. Its purpose is to find a group that does NOT match after the primary expression.


## Author

Sharon Christensen is a full-stack web developer. Find her on GitHub, https://github.com/schris48.

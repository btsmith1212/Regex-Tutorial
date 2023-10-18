# Regex: Matching an Email

This tutorial will guide the user through using a regular expression(regex) to match emails, which can be particularly useful when maintaining email lists and collecting user data.

## Summary

A regex is a sequence of characters that specifies a match pattern in text. This guide will explain how to use a regex to match email addresses utilizing the expression `/^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/`.

## Table of Contents

- [Anchors](#anchors)
- [Quantifiers](#quantifiers)
- [Character Classes](#character-classes)
- [Grouping and Capturing](#grouping-and-capturing)
- [Bracket Expressions](#bracket-expressions)
- [Greedy and Lazy Match](#greedy-and-lazy-match)

## Regex Components

### Anchors

Anchors set the start and end point of a regex. The anchors used for matching an email are: `^` for the beginning, and `$` for the ending.

### Quantifiers

Quantifiers specify how many instances of a character, group, or character class must be present in the input for a match to be found. Quantifiers in this regex include the `+` and `{x,x}`. `+` is a connector that combines the user's email name with their email service and domain extension (eg `.com`). `{x,x}` is an expression that will force a match of x-x characters for the character set of `[a-z\.]` (eg {2-6} would force a match range of 2-6 characters).

### Character Classes

A character class specifies the characters that will successfully match a single character from a given input string, in this case the operator `\d` which will match a single character that is a digit from 0-9.

### Grouping and Capturing

Capturing groups are a way to treat multiple characters as a single unit. This regex captures the first group `([a-z0-9_\.-]+)`, which matches the user's email 'name'. The second group captured is `([\da-z\.-]+)`, which matches the user's email service. Lastly `([a-z\.]{2,6})` captures the user's domain extension.

### Bracket Expressions

Bracket expressions match a specific set of single characters. This regex `[a-z0-9_\. -]` matches any lowercase letter between a to z `a-z` as well as any number from 0 to 9 `0-9` (please note that letters are case sensitive). Other common characters used in emails are also included; `_` and `-`.
These bracket expressions are broken up by a `.` based on what part of the email are being matched; the first matching to the username, second to the provider, third to the domain extension.

### Greedy and Lazy Match

A greedy match uses quantifiers to match as many instances of its specified quantity as possible. The quantifier used in the first two segments, `+`, matches as many times as needed. The quantifier used in the domain extension, `{2,6}`, matches between 2 and 6 letters in that segment. See [Quantifiers](#quantifiers).

No lazy matches are used in this regex.

## Author

Blake Smith https://github.com/btsmith1212

# CxLos17-Regex-Tutorial
```
Hello and welcome to the CxLos17 Regex Tutorial! Here we will explain what exactly is a regex, how to use it, and why we use it.
```
## Summary

> Regular Expressions are a sequence of characters that we use to define a search. In this tutorial, we will be going over how to use a Regex to search for emails. Below is a code snippet of what it would look like.

> Email Search: `/^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/`

> The series of special characters above checks to see if a string fulfills the requirement of a legitimate email. The first portion of the string can only contain lower-case letters from a-z, any number between 0-9, can contain a `-` , `_` , or `.`, followed by the `@` symbol. and then the next set of parentheses will take us into our next subexpression where it will match any arabic number, any lower-case letter a-z, a `'.'` , followed by a `+` sign, which we will explain later in the tutorial, and then the last section is the portion of the email after the period `'.'` where we will match with any letter a-z, with a length between 2 - 6 characters. This may seem like a lot of information, but we will break everything down into more detail in this tutorial.

## Table of Contents

- [Anchors](#anchors)
- [Quantifiers](#quantifiers)
- [Grouping Constructs](#grouping-constructs)
- [Bracket Expressions](#bracket-expressions)
- [Character Classes](#character-classes)
- [The OR Operator](#the-or-operator)
- [Flags](#flags)
- [Character Escapes](#character-escapes)

## Regex Components

> Regex Components are the 'components' of a regex expression. basically everything that is included between the two forward slashes `'/'`. Please read the sections on each component below:

### Anchors

> The characters we use at the beginning and end of search. `‘^’` signifies a string that begins with the characters that follow it. `‘$’` signifies that the string ends with the characters that precede it. Basically all searches start with `‘/^’` and end with `‘$/’`.

### Quantifiers

> Sets the limits of the string that your regex matches and must be contained in curly brackets `'{}'`. Frequently include the minimum and maximum number of characters that your regex is looking for. Quantifiers are inherently Greedy, meaning that they match as many occurrences of particular patterns as possible. Below are examples of some quantifiers:

> * `‘*’` – matches the pattern `0` or more times
> * `‘+’` – matches the pattern `1` or more times
> * `‘?’` – matches the pattern `0` or `1` time, Aka making the search `‘lazy’`, meaning it will match the search with as few occurrences as possible.
> * `‘{ }’` – establish `3` different ways to set limits for a match:
>   * `‘{ n }’` – matches the pattern exactly `n` number of times.
>   * `‘{ n, }’` – matches the pattern at least `n` number of times.
>   * `‘{ n, x }’` – matches the pattern from a minimum of `n` number of times to a maximum of `x` number of times. A range.

### Grouping Constructs

> Used to check multiple parts of a string to make sure that different sections fulfill different requirements. To break these up, you must include them inside of parentheses ( ). Grouping constructs have 2 main categories:

> * Capturing: capture matched character sequences for possible re-use (including a numbered backreference).
> * Non-capturing: do not. Grouping construct can be made non-capturing by adding ‘?:’ at the beginning of an expression inside parentheses.

### Bracket Expressions

> We include every single thing we want to search for within brackets `[ ]`. Can also be referred to as 'positive character group. for example, if we want to match `'[41zh8]'`, the following would all match, regardless of the length of the string: `'41'`, `'888'`, `'hi'` etc..

### Character Classes

> Defines a set of characters, any one of which can occur in an input string to fulfill a match. Below are some examples of character classes.

> * `‘/’` – Regex literals. Encapsulates entire search. Basically the search starts and ends with forward slash.
> * `‘\d’` – Any Arabic number `0-9`. Can be inversed with `‘\D’`
> * `‘.’` – Any character except the newline character `‘\n’`.
> * `‘\w’` – Matches any alphanumeric character from the basic Latin alphabet, including `‘_’`. Can be inversed with `‘\W’`.
> * `‘\s’` – Matches a single whitespace character including tabs and line breaks. Can be inversed with `‘\S’`.
> * `‘.*’` – Matches literally everything. like a wildcard.
> * `‘[ ]’` – Bracket expression. Include here everything it is that you want to search for.
> * `‘( )’` – Subexpression. Grouping construct to make sure different parts of a string fulfill different requirements.
> * `‘|’` – OR operator.
> * `‘\’` – Character escape. Escapes a character that would be interpreted literally.
> * `‘^’` – Anchor that signifies a string begins with the characters that follow it. Also a negative. Meaning it will find anything that does NOT contain any of the characters specified.
> * `‘$’` – Anchor that signifies a string that ends with the characters that precede it.

### The OR Operator

> Makes search less literal. So instead of finding literally what is included in a set of parentheses, such as `'(fgh)'` adding `'|'` will make it search for `f` or `g` or `h`.

### Flags

> Placed at the end of a regex, after the second slash, and define additional functionality or limits for the regex. There are 6 flags that can be used either separately or together in any order. 3 most common:

> * `‘g’` – Global search: regex should be tested against all possible matches in a string.
> * `‘i’` – Case sensitive search: case should be ignored while attempting a match in a string.
> * `‘m’` -  Multi-line search: a multi-line input string should be treated as multiple lines.


### Character Escapes

> Escapes a character that would be interpreted literally. `{` is how we would normally begin a quantifier, but if you were to write `\{` it will now search for the actual curly bracket character itself.

## Author

[Carlos Bautista](https://github.com/CxLos/) 

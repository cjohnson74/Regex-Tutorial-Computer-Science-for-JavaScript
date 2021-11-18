# Computer Science for JavaScript: Matching an IP Address with Regex Tutorial

Have you ever needed to find an IP address in a body of text, within code, in an API or Database? Probably not, but after going through this tutorial you will know how to just using [regex](https://www.computerhope.com/jargon/r/regex.htm). After this tutorial you will also be able to utilize regular expressions to find and search anything, by creating your own patterns.

## Summary

For the record I did not come up with this regex pattern myself. I will be using this regex pattern as a teaching example. By breakdown this regex down character for character I will be able to show you the different parts and pieces of a regex.

Now lets get into it, here is the pattern we will be decunstructing:

```javascript
/^(?:(?:25[0-5]|

2[0-4][0-9]|[01]?[0-9][0-9]?)

\.){3}(?:25[0-5]|2[0-4][0-9]|

[01]?[0-9][0-9]?)$/
```
![IP_Regex](https://user-images.githubusercontent.com/52815609/142356111-d4501b58-3c05-4230-b4eb-e9c87203be78.jpeg)

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

Remember that a regex [regular expression](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Regular_Expressions) is considered a [literal](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Grammar_and_types#regexp_literals). This means that the regex pattern must be within slash characters ( **/** ).

### Anchors

The characters **^** and **$** are both considered anchors.

| Character | Definition                                                           | Example      | Matches  |
| :-------: | :------------------------------------------------------------------: | :----------: | :------: |
|   **^**   |  Signifies a string that begins with the characters that follow it.  | ^The  | "The" or "The person" not "the person" or "the" |
|   **$**   |  Signifies a string that ends with the characters that precede it    | .com$ | "webite.com" or "email@gmail.com" |

### Quantifiers

### Grouping Constructs

### Bracket Expressions

### Character Classes

### The OR Operator

### Flags

### Character Escapes

## Author

A short section about the author with a link to the author's GitHub profile (replace with your information and a link to your profile)

<h1 align="center">Computer Science for JavaScript:</h1>
<h1 align="center">Matching an IP Address with Regex Tutorial </h1>

Have you ever needed to find an IP address in a body of text, within code, in an API or Database? Probably not, but after going through this tutorial you will know how to just using [regex](https://www.computerhope.com/jargon/r/regex.htm). After this tutorial you will also be able to utilize regular expressions to find and search anything, by creating your own patterns.

## Summary

For the record I did not come up with this regex pattern myself. I will be using this regex pattern as a teaching example. By breakdown this regex down character for character I will be able to show you the different parts and pieces of a regex.

Now lets get into it, here is the pattern we will be deconstructing:

```javascript
/^(?:(?:25[0-5]|

2[0-4][0-9]|[01]?[0-9][0-9]?)

\.){3}(?:25[0-5]|2[0-4][0-9]|

[01]?[0-9][0-9]?)$/
```
<p align="center">
<img id="ip-example" src="https://user-images.githubusercontent.com/52815609/142356111-d4501b58-3c05-4230-b4eb-e9c87203be78.jpeg" />
</p>

## Table of Contents

- [Summary](#summary)
- [Table of Contents](#table-of-contents)
- [Regex Components](#regex-components)
  - [Anchors](#anchors)
  - [Quantifiers](#quantifiers)
  - [Grouping Constructs](#grouping-constructs)
  - [Bracket Expressions](#bracket-expressions)
  - [Character Classes](#character-classes)
  - [The OR Operator](#the-or-operator)
- [Author](#author)

## Regex Components

Remember that a regex [regular expression](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Regular_Expressions) is considered a [literal](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Grammar_and_types#regexp_literals). This means that the regex pattern must be within slash characters ( ```/``` ). These slashers are called [delimiters](https://www.computerhope.com/jargon/d/delimite.htm) and they are required for every regular expression.

### Anchors

The characters ```^``` and ```$``` are both considered [anchors](https://www.regular-expressions.info/anchors.html). As you can see in the IP regex the ```^``` marks the beginning of the line. Then the ```$``` is just before the final forward slash to mark the end of the line.

| Character |                              Definition                             | Example |                      Matches                    |
| :-------: | :-----------------------------------------------------------------: | :-----: | :---------------------------------------------: |
|   ``^``   |  Signifies a string that begins with the characters that follow it. | ``^The``| "The" or "The person" not "the person" or "the" |
|   ``$``   |  Signifies a string that ends with the characters that precede it   |``.com$``| "website.com" or "email@gmail.com"               |

### Quantifiers

A [quantifier](https://docs.microsoft.com/en-us/dotnet/standard/base-types/quantifiers-in-regular-expressions) is a character that says how many of a character, group, or character class needs to be there in order for the regex to find a match. There are a few different types of quantifying characters, here is a list of the ones that are use in our [IP address example](#ip-example) with some additional characters:

| Character |       Definition         |    Example     |                    Example Description                |        Matches        |
| :-------: | :----------------------: | :------------: | :---------------------------------------------------: | :-------------------: |
|   ``*``   | Match zero or more times |     ``91*``    | Matches a "9" followed by zero or more "9" characters.| ``'9', '911', '9111'``|
|   ``+``   | Match one or more times  |     ``91+``    | Matches a "9" followed by one or more "1" characters. | ``'91', 911, '91111'``|
|   ``?``   | Match zero or one time   |    ``[01]?``   | Matches '01' one or zero times                        |          ``01``       |
| ``{ n }`` | Matches exactly 'n' times|  ``[0-5]{3}``  | Matches '0-5' exactly 3 times                         |``'152', '341', '111'``|

### Grouping Constructs

A [group construct](https://docs.microsoft.com/en-us/dotnet/standard/base-types/grouping-constructs-in-regular-expressions) allows you to do many apply  to a [subexpression](https://support.smartbear.com/loadcomplete/docs/ref/misc/using-subexpressions.html) in your regular expression. Here are a couple examples of using grouping constructs in the [IP address example](#ip-example). you can tell they are grouping constructs because of the parenthesis that capture the many subexpressions within them:

```javascript
(?:(?:25[0-5]|2[0-4][0-9]|[01]?[0-9][0-9]?)\.)
```
```javascript
(?:25[0-5]|2[0-4][0-9]|[01]?[0-9][0-9]?)
```
In the first example you can see it is followed by a {3} in our [IP address example](#ip-example), this is matching the entire group construct, subexpressions and everything between the parenthesis, exactly 3 times. This is just one demonstration of how powerful grouping constructs can be.

### Bracket Expressions

I [bracket expression](https://www.gnu.org/software/grep/manual/html_node/Character-Classes-and-Bracket-Expressions.html) is a group or characters, numbers, or letters that are enclosed by ```[``` and ```]```. There are many different types of bracket expressions that we are going to take a look at that go along with the [character classes](#character-classes). In this section I will show you some rules to bracket expressions that my save you some trial and error. The following rules for your bracket expressions to work properly in regular expressions:

| Example | Rule                                                                                                                                                            |
| :-----: | :-------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| ```]``` | If you want to include the bracket as a list item you must put it first.                                                                                        |
|```[:``` | The open character class symbol should be followed by a valid class name.                                                                                       |
|```:]``` | The closed character class symbol should follow the class name.                                                                                                 |
|```-```  | The hyphen represents the range. If you want to include it as a list item you mush put it first or last.                                                        |
| ```^``` | The caret represents what is not included in the list. If you want to include it as a list item you may put it anywhere in the bracket expression except first. |

Bracket expressions are used many times throughout our [IP address example](#ip-example) to show the ranges of numbers that could potentially match our regex expression.
### Character Classes

Now that we know how to use [bracket expressions](#bracket-expressions) from the previous section we are able to take a look at [character classes](https://www.gnu.org/software/grep/manual/html_node/Character-Classes-and-Bracket-Expressions.html). The most useful character classes that are not included in our [IP address example](#ip-example) are named classes, which are predefined:

|     Example    | Matches                                    |
| :------------: | :----------------------------------------- |
|```[:alnum]```  | Alphanumeric characters: ```[0-9A-Za-z]``` |
|```[:alpha:]``` | Alphabetic characters: ```[A-Za-z]```      |
|```[:blank:]``` | Blank characters: space, tab, etc.         |
|```[:lower:]``` | Lowercase characters: ```[a-z]```          |
|```[:digit:]``` | Digits characters: ```[0-9]```             |
|```[:upper:]``` | Upper characters: ```[A-Z]```              |
|```[:xdigit:]```| Hexadecimal digits: ```[0-9A-Fa-f]```      |

### The OR Operator

The [OR](https://kodejava.org/how-do-i-use-logical-or-operator-in-regex/) operator ( | ) is used if you want your regular expression to match the characters or expression to the left or the right of the operator. In our [IP address example](#ip-example) there is a three OR operators being used. The first OR is being used so that the regex, in this case, doesn't match the string "25" followed by a number between 0 and 5 OR the string "2" with a number between 0 and 4, followed by a number between 0-9.

```javascript
(?:25[0-5]|2[0-4][0-9]
```

## Author

A short section about the author with a link to the author's GitHub profile (replace with your information and a link to your profile)

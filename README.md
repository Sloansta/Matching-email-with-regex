# Matching an Email with Regex

## Summary

As a web developer, I am sure that we have all gone through the trouble of trying to figure out what exactly the user is trying to input into the text boxes we give them
on the user interface. Will what they write break my application? What if they type in something that causes my web app break? Are they really going to put in a valid phone
number? What about their email? 
Today, I will be answering a fix that can be done with regex. Specifically, how to check if the email that the user inputted into your text box is actually in email format.

The regular expression that makes it all work looks liked this: `/^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/`
But how does this string of what appears to be nonsense really work? Let's break it down.

## Table of Contents

- [Grouping and Capturing](#grouping-and-capturing)

- [Character Sets](#character-sets)

- [Quantifiers](#quantifiers)

- [Bracket Expressions](#bracket-expressions)

## Regex Components

### Grouping and Capturing
This technically isn't capturing a group, but you will see `/^` at the start of a regular expression and `$/` at  the end of a regular expresion.
These, while technically not considered group capturing, mark the start, and the end of a regular expression, respectfully. 
I thought that it was worth mentioning here because this is where we will be talking about grouping and capturing.

Grouping occurs when the `()` are used. This indicates a group, a section if you will, of the string that is being compared to the regular expression.
For instance in our email regular expression, `/^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/`, there are three groups. 
Group 1, being the first `([a-z0-9_\.-]+)` indicating anything before the @ symbol. This is the first part of the email address that the user types.
Group 2, being the second, `([\da-z\.-]+)` indicating everything before the period before group 3 starts (gmail, yahoo, comcast etc)
Lastly, we have group 3. Group 3 `([a-z\.]{2,6})`, is the group that comes after the period, and is limited to 2-6 characters. (com, org, gov, edu)

### Character Sets
Character sets are held within groups (mentioned above), and are denoted with `[]`. 
What follows is typically either `a-z` if it's allowing only letters, or it can be seen mixed with `0-9` indicating that numbers are also acceptable within
the string that the regular expression is parsing. Other characters can include `_`, Escaped characters like `\.` indicating that periods are valid in the group, and `-`. All indicating that these symbols are fair use within said group.

### Quantifiers
Quantifiers specify how many instances of a character, group, or character class must be present in the input for a match to be found.
For example, `+` is added to the groups indicating that this and more will be expected in the string that the regular expression is attempting to parse.

### Bracket Expressions
While also technically being a Quantifier, bracket expressions can also be used to indicate expected ranges for string lengths. Take `{2,6}` in Group 3. This indicates that this group is expected to be no less than 2, no greater than 6 characters in order to be valid and acceptable for this regular expression.

## Author

Sloan is a Fullstack Web Developer based in Michigan. 
Github: https://github.com/sloansta
Website: https://sloansta.github.io/sloan-page/

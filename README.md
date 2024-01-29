# My Matching Hex Value Regex Tutorial

Hello there! Today, we're rolling up our sleeves to explore the intricacies of hex color codes. Those six or three characters after a '#' might seem straightforward, but let's dissect them and build a regex that stands up to the challenge.

# Breaking Down Matching Hex Value

Our regex for matching hex color values will be the centerpiece of our discussion:

` ^#?([a-f0-9]{6}|[a-f0-9]{3})$`

As we dissect this regex, we'll touch on each of the elements mentioned below, providing practical examples along the way.

- [Anchors](#anchors)
- [Quantifiers](#quantifiers)
- [OR Operator](#or-operator)
- [Character Classes](#character-classes)
- [Grouping and Capturing](#grouping-and-capturing)
- [Bracket Expressions](#bracket-expressions)
- [Greedy and Lazy Match](#greedy-and-lazy-match)

### Anchors

In Regex, an anchor is a metacharacter that represents a specific position within the text. Anchors are used to assert where a pattern should occur in relation to the start or end of a line or word.

In the regex pattern `^#?([a-f0-9]{6}|[a-f0-9]{3})$`, the `^` and `$` symbols are anchors.

`^`: This anchor asserts the position at the beginning of the line and where the pattern should start. 

`$`: This anchor asserts the position at the end of the line and where the pattern should end

So, combined, these anchors `^` and `$` ensure that the entire line should match the specified pattern, ensuring that it starts with an optional # symbol followed by either six or three characters from the set `a-f0-9`. 

### Quantifiers
 Quantifiers specify the quantity of characters or sets to match in a pattern. It essentially allows you to define how many times a specific element should appear in the text

There is one quantifier being used here:

Curly Braces: `{6}`and `{3}` are being used to specify that the preceding character class `[a-f0-9]` should be repeated exactly 6 times or 3 times.

### OR Operator

In regular expressions, the OR operator is represented by the vertical bar `|`. It allows you to specify multiple alternatives within a pattern. The OR operator functions as a logical "OR," meaning that the pattern will match if either of the alternatives is found in the text. 

Let's break down the relevant part of the pattern:
`([a-f0-9]{6}|[a-f0-9]{3})`

1. `[a-f0-9]{6}`: This part matches exactly six alphanumeric characters (0-9, a-f).
2. `|`: The vertical bar serves as the OR operator, indicating an alternative option.
3. `[a-f0-9]{3}`: This part matches exactly three alphanumeric characters (0-9, a-f).

Just like in hex code you can input 6 characters or 3 characters and you will still get a color!

### Character Classes

We also have character classes used within square brackets. Character classes define a set of characters, and the pattern matches any single character that belongs to that set. Let's break down the relevant part of the pattern:

`a-f`: This is a character class that matches any single character that is a lowercase letter from 'a' to 'f'.
`0-9`: This is a character class that matches any single character that is a digit from '0' to '9'.

### Grouping and Capturing

Grouping and capturing is a functionality provided by the `()`. In the pattern `#?([a-f0-9]{6}|[a-f0-9]{3})$` we can see the use of grouping and capturing. 

`([a-f0-9]{6}|[a-f0-9]{3})`: This is a capturing group that includes two alternatives separated by the OR operator |.
`[a-f0-9]{6}`: The first alternative matches exactly six alphanumeric characters (0-9, a-f).
`[a-f0-9]{3}`: The second alternative matches exactly three alphanumeric characters (0-9, a-f).

### Bracket Expressions

Bracket expressions define a set of characters, and the pattern matches any single character that is part of that set.

Here's the relevant part of the pattern:
`[a-f0-9]`: This is a bracket expression that matches any single character that is a lowercase letter from 'a' to 'f' or a digit from '0' to '9'.

### Greedy and Lazy Match

In our pattern `^#?([a-f0-9]{6}|[a-f0-9]{3})$`, there is an implicit use of greedy matching. Greedy matching is the default behavior of regular expressions, where the pattern matches as much as possible while still allowing the entire regex to match successfully.

Let's consider the part of the pattern that involves quantifiers:

`([a-f0-9]{6}|[a-f0-9]{3})`
In this part, the quantifiers `{6}` and `{3}`are inherently greedy. They try to match as many characters as possible that satisfy the pattern while still allowing the overall regex to match successfully. This is the default behavior of quantifiers in regular expressions.

If you want to make a quantifier lazy (matching as few characters as possible), you can add a `?` after the quantifier. For example:

`([a-f0-9]{6}?|[a-f0-9]{3}?)`
The `?` after the quantifiers `{6}` and `{3}` makes them lazy, and they will match as few characters as possible while still allowing the overall regex to match.

Although in our pattern this is not necessary, as the default greedy behavior will ensure that the entire pattern can match a valid hex color code.

## Author

My name is Charles W. Gillespie, a UCONN boot camp student passionate about web development. You can find more about me and my projects here on [GitHub](https://github.com/CharlesWGillespie?tab=overview&from=2024-01-01&to=2024-01-29).


# regex-tutorial

### Definition
A sequence of characters that define a search pattern.


### Basic topics

##### Anchors `^` and `$`
|         |            | Example |
| --------|------------| --------|
|`^The` | matches any string that starts with The |  [Try it!](https://regex101.com/r/I9rM8i/1) |
|`end$` | matches a string that ends with end | [Try it!](https://regex101.com/r/qvTmIl/1) |
|`^exact$` | exact string match | [Try it!](https://regex101.com/r/KfWmjq/1) |

##### Quantifiers `* + ? and {}`
|         |            | Example |
| --------|------------| --------|
| `abc*` | matches a string that has ab followed by zero or more c | |
| `abc+` | matches a string that has ab followed by one or more c | |
| `abc?` | matches a string that has ab followed by zero or one c | |
| `abc{2}` | matches a string that has ab followed by 2 c | |
| `abc{2,}` | matches a string that has ab followed by 2 or more c | |
| `abc{2,5}` | matches a string that has ab followed by 2 up to 5 c | |
| `a(bc)*` | matches a string that has a followed by zero or more copies of the sequence bc | |
| `a(bc){2,5}` | matches a string that has a followed by 2 up to 5 copies of the sequence bc | |


#### OR operator `|` or `[]`
|         |            | Example |
| --------|------------| --------|
| `a(b\|c)` | matches a string that has a followed by b or c (and captures b or c) | |
| `a[bc]`  | same as previous, but without capturing b or c | |
*when `-` is not the first charecter inside `[]` it is used as a range like `[a-z]`*
*when `^` is the first charecter inside `[]` it is used as a nagation `[^a-z]`*


#### Character classes  `\d` `\w` `\s` and `.`
|         |            | Example |
| --------|------------| --------|
| `\d` | matches a single character that is a digit
| `\w` | matches a word character (alphanumeric character plus underscore) | |
| `\s` | matches a whitespace character (includes tabs and line breaks) | |
| `.`  | matches any character | |

*`\d`, `\w` and `\s` also present their negations with `\D`, `\W` and `\S` respectively.* 

#### Escape metacharacter  `\`
|         |            | Example |
| --------|------------| --------|
| `\$\d` | matches a string that has a $ before one digit | |

#### Flags
|         |            | Example |
| --------|------------| --------|
| `g` | global | |
| `m` | multi-line | |
| `i` | case-insensitive | |

#### Boundaries `\b` and `\B`
|         |            | Example |
| --------|------------| --------|
| `\babc\b` | performs a "whole words only" | [Try it!](https://regex101.com/r/cO8lqs/25) |
| `\Babc\B` | negation | [Try it!](https://regex101.com/r/cO8lqs/26) |


`colou?rs?` - all colours 
`(\(\d{2}\)\s)?\d{5}[-.\s]\d{4}` - phone numbers




### Intermediate topics
#### Greedy and Lazy match
The quantifiers `*`, `+` `{}` are greedy operators, so they expand the match as far as they can through the provided text.

For example, `<.+>` matches `<div>simple div</div>`

In order to catch only the div tag we can use a ? to make it lazy like `<.+>`

Notice that a better solution should avoid the usage of `.` in favor of a more strict regex is `<[^<>]+>`

#### Grouping and capturing `()`
|         |            | Example |
| --------|------------| --------|
| `a(bc)` | parentheses create a capturing group with value bc | |
| `a(?:bc)*` | using ?: we disable the capturing group | |
| `a(?<foo>bc)` | using ?<foo> we put a name to the group | |
  

Example to convert markdown links in html anchors  
`\[(.*?)\]\((.*?)\)`

```
[Google](https://www.google.com)
[Google BR](https://www.google.com.br)
```


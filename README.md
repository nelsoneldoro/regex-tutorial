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

#### Character classes  `\d` `\w` `\s` and `.`
|         |            | Example |
| --------|------------| --------|
| `\d` | matches a single character that is a digit -> Try it!
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

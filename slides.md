## RegEx
### Crash Course

---

#### Why RegEx?

  - Unbelievably Powerful
  - highly reusable and highly portable
  - Solve countless day to day problems
  - Widely Supported

---

#### What is RegEx?

A pattern matching language. Yes, a language!

A regex is a string. For instance, `foo` is a regex. so is `[A-Z+:\d+]`

There's a beautiful language behind that obfuscated mess of characters.

---

#### Simple Expressions

Let us start with basic patterns without weird characters.

`abc`

a thing, followed by another thing, followed another thing!

---

#### Simple Expressions

| pattern | matches |
| --- | --- |
| `abc` | `abc,abcd,zabc` |
| 123 |   `1234,abc123,za234123bc` |
| `a1` | `a1,a1bc,a12b2c` |

---

#### Meta characters

Characters with special meaning to them.

`^ [] () {} . * \ | + ? $` and sometimes `-`

---

#### Match Any Character with `.`

Matches any character. (Wild card)

`s.n` matches `san`, `sun`, `son` and etc.

---

#### Line Anchors: `^` and `$`

`^` - Start of Line; `$` - End of Line

| pattern | matches |
| --- | --- |
| `^Hi` | line starts with `Hi` |
| `Hello$` | line ends with `Hello` |
| `^san$` | line that has only `san` |
| `^$` | Empty line |

---

#### Character Class: `[]`

match any one of several characters.

gr[ea]y - "`g`, followed by `r`, followed by **either an `e` or an `a`**, followed by y."

If you use `[^...]` instead of `[...]`, the class matches any character that's not in the character class.

---

#### Character Class Metacharacter: `-`

specify range between two characters

| pattern | matches |
| --- | --- |
| `[a-c]` | Any of `a b c` |
| `[0-9]` | Any of `0 1 2 3 4 5 6 7 8 9` |
| `[A-Za-z]` | Any of the English alphabet |

`[012345abcedfABCDEF]` is same as `[0-5a-fA-F]`

---

#### Alternation Metacharacter: `|`

`|` means `either` - combines two expressions into one

`Mike` and `Michael` are separate, but `Mike|Micheal` is one that matches either.

---

#### Matching Optional Items: `?`

placed after a character that is allowed, but not required, at a certain position in an expression.

`flavou?r` - matches flavor (US), flavour (UK)

"`f`, followed by `l`, followed by `a`, followed by `v`, followed by `o`, followed by an `optional u`, followed by `r`."

---

#### Other Quantifiers: `+` and `*`

number of times the preceding character can appear in an expression

| Character | Meaning |
| --- | --- |
| `?` | `0` or `1` |
| `+` | `1` or more |
| `*` | `0` or more |

---

#### Interval Quantifier: `{}`

`{min,max}` metasequence specifies number of times an item can match

**TODO**: add example

---

#### Escape Character: `\`

`\` escapes metacharacters so you can match those in patterns.

**TODO**: add example

---

#### Paranthesis for Grouping: `()`

`http://([^/]+)` - matches the domain part alone.

`http://github.com/sanspace`

`github.com`

`[^/]+` is grouped as subportion of the expression

---

#### Examples - Username

Requirements
  - Alphanumeric
  - No special characters except underscore
  - Minimum 8 characters, Maximum 16 characters

`^[a-zA-Z0-9_]{3,16}$` <!-- .element: class="fragment" -->

---

#### Match an IP address

169.254.169.254

---

#### Not so fast

> Some people, when confronted with a problem, think "I know, I'll use regular expressions." Now they have two problems.

---

#### Not so fast

> not that regular expressions are evil, per se, but that __overuse__ of regular expressions is evil.

---

#### Not so fast

  - Know the flavors of different programming languages
  - Know what you are doing
  - RegEx could be slow for complex patterns

---

#### References

- [Interactive Tutorial](http://regexone.com/)
- [Playground (dojo)](https://regex101.com/)

---

#### Credits

- [Coding Horror Blog](https://blog.codinghorror.com/regular-expressions-now-you-have-two-problems/)
- [Bare Minimum Every Programmer Should Know](http://web.archive.org/web/20090226052234/http://immike.net/blog/2007/04/06/the-absolute-bare-minimum-every-programmer-should-know-about-regular-expressions/)

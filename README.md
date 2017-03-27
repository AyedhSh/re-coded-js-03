# JavaScript Challenge #3
For this assignment, you are tasked with creating a simple JavaScript linter, a program that checks your code for syntax errors.

Your function, `lint`, should accept a string of JavaScript code. If the code has no syntax errors, your function should return `true`. If the function encounters a syntax error — a missing closing punctuation mark or an extra opening punctuation mark — it should exit and return the offending punctuation mark as well as its position within the string.

## Level 1
|      Every opening...     | Must have a closing... |
|---------------------------|------------------------|
|            `(`            |          `)`           |
**Note that simply counting up the number of opening and closing parentheses is *not* good enough. If we just checked that the code has the same number of `(`s and `)`s, this code would pass the linter's tests: `)))))(((((`.**

## Level 2
|      Every opening...     | Must have a closing... |
|---------------------------|------------------------|
|            `(`            |          `)`           |
|            `{`            |          `}`           |
|            `[`            |          `]`           |
**Your linter should check that the punctuation marks are ordered in a logical way. `([)]` does not make any sense. `()[]`, `[]()`, `([])`, and `[()]` all do make sense.**

## Level 3
|      Every opening...     | Must have a closing... |
|---------------------------|------------------------|
|            `(`            |          `)`           |
|            `{`            |          `}`           |
|            `[`            |          `]`           |
|            `'`            |          `'`           |
|            `"`            |          `"`           |
|          `` ` ``          |        `` ` ``         |
**Here, order matters everywhere *except* inside quotation marks. `["(]'}"]` is perfectly valid code.**

When provided the following string with no syntax errors:
```js
const code = "function () { return [\"first\", 'second', `third`]; }";

lint(code);
=> true
```

When provided a string of code with 1+ syntax errors:
```js
const code = "function () { return [\"first\", second', `third`]; }";

lint(code);
=> Syntax error: ', character 38.
```
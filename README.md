# JavaScript Challenge #3
For this assignment, you are tasked with creating a simple JavaScript linter, a program that checks your code for syntax errors.

You will need to create three functions, one to grab the current content of the `<textarea>`, one to check whether the basic syntax of that content is correct, and one to add the result to the DOM.

If the code has no syntax errors, your linter should add a congratulatory message to the `#result` div. If your `lintCode()` function encounters a syntax error — a missing closing punctuation mark or an extra opening punctuation mark — it should return the incorrect punctuation mark as well as its position within the code (line and character number).

## Level 1
|      Every opening...     | Must have a closing... |
|---------------------------|------------------------|
|            `(`            |          `)`           |

**Note that simply counting up the number of opening and closing parentheses is *not* good enough. If we just checked whether the code contains the same number of `(`s and `)`s, this code would pass the test: `)))))(((((`.**

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

When provided the following code with no syntax errors...
```js
function () {
  return ["first", 'second', `third`];
}
```
...your linter should return a congratulatory message to the user.

When provided a string of code with one or more syntax errors...
```js
function () {
  return ["first", 'second', `third`];]
}
```
...your linter should return a message to the user that contains the incorrect mark (`]`) and its position within the code (line 2, character 37).
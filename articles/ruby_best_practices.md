# Ruby best practices

- Use soft-tabs with a two space indent.
- Limit each line of code to a readable length. Unless you have a reason to, keep lines to a maximum of 118 characters. Why 118? That's the width at which the pull request diff UI needs horizontal scrolling (making pull requests harder to review).
- Configure your editor to:
  - Never leave trailing whitespace.
  - End each file with a newline.
- Naming:
  - Use `snake_case` for methods and variables.
  - Use `CamelCase` for classes and modules.
  - Keep acronyms like HTTP, RFC, XML uppercase.
  - Use `SCREAMING_SNAKE_CASE` for other constants.
  - The names of predicate methods (methods that return a boolean value) should end in a question mark. (i.e. `Array#empty?`).
  - The names of potentially "dangerous" methods (i.e. methods that modify `self` or the arguments, `exit!`, etc.) should end with an exclamation mark. Bang methods should only exist if a non-bang method exists. ([More on this](http://dablog.rubypal.com/2007/8/15/bang-methods-or-danger-will-rubyist)).
- Prefer string interpolation instead of string concatenation.
- Use `def` with parentheses when there are arguments. Omit the parentheses when the method doesn't accept any arguments.
- Never use `for`, unless you know exactly why. Most of the time iterators should be used instead. `for` is implemented in terms of `each` (so you're adding a level of indirection), but with a twist - `for` doesn't introduce a new scope (unlike `each`) and variables defined in its block will be visible outside it.
- The `and` and `or` keywords are banned. It's just not worth it. Always use `&&` and `||` instead.
- Don't use `||=` to initialize boolean variables. (Consider what would happen if the current value happened to be `false`.)
- Do not commit old pieces of code as inline comments. They will make your project look messy. If you need to review a previous version of your code, you can always use git history.

------

_If you spot any bugs or issues in this activity, you can [open an issue with your proposed change](https://github.com/microverseinc/curriculum-transversal-skills/blob/main/git-github/articles/open_issue.md)._

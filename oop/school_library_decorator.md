# OOP school library: decorate a class

## Learning objectives
- Implement composition (as an example of the design pattern).
- Run a program using the command line.

### Estimated time: 2h

## Description
In this project, you will use the Decorator design pattern to validate and correct the names of people.

*IMPORTANT NOTE: Read **all** requirements before you start building your project.*

### General requirements

- Make sure that there are [no linter errors](https://github.com/microverseinc/linters-config).
- Make sure that you used correct [Gitflow](https://github.com/microverseinc/curriculum-transversal-skills/blob/main/git-github/articles/gitflow.md).
- Make sure that you documented your work [in a professional way](https://github.com/microverseinc/curriculum-transversal-skills/blob/main/documentation/articles/professional_repo_rules.md).

### Ruby requirements
- Follow our list of [best practices for Ruby](https://github.com/microverseinc/curriculum-ruby/blob/main/articles/ruby_best_practices.md).

### Project requirements
- Create a class `Corrector` with a method `correct_name` that does the following:
  - Make sure the first letter of the given name is a capital letter.
  - Make sure that the name has a maximum of 10 characters. If it's longer it should trim the word.
- Set an instance of `Corrector` in `Person` on initialization.
- In `Person` add a method `validate_name` that uses the `Corrector` instance to validate and save the corrected name.

### Need a big picture?

Remind me about [the big picture of this project](./sneak_peek.md).


## Work and submission mode

- You should submit this activity **individually.**

## Code review

Follow [these steps](https://github.com/microverseinc/curriculum-transversal-skills/blob/main/code-review/articles/how_to_ask_for_a_code_review.md) to request a code review of your project.

## Submit your project

After the final approval from a code reviewer, you need to submit your project.
[Read this FAQ for a reminder on how to submit your project.](https://microverse.zendesk.com/hc/en-us/articles/360061344234)
Now go to your Student Dashboard and submit your project.

------

_If you spot any bugs or issues in this activity, you can [open an issue with your proposed change](https://github.com/microverseinc/curriculum-transversal-skills/blob/main/git-github/articles/open_issue.md)._

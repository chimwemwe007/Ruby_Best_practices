# Create your own Enumerable

## Learning objectives
- Use Ruby syntax for basic programming operations.
- Apply Ruby best practices and language style guides in code.

### Estimated time: 2h

## Description
In this project you will learn how to use a module inside your class. For this you will create a class `MyList` and a module `MyEnumerable`. Your module `MyEnumerable` will implement a subset of the functionality of [Enumerable](https://ruby-doc.org/core-3.0.0/Enumerable.html).

*IMPORTANT NOTE: Read **all** requirements before you start building your project.*

### General requirements

- Make sure that there are [no linter errors](https://github.com/microverseinc/linters-config).
- Make sure that you used correct ([GitHub Flow](https://github.com/microverseinc/curriculum-transversal-skills/blob/main/git-github/articles/github_flow.md).
- Make sure that you documented your work [in a professional way](https://github.com/microverseinc/curriculum-transversal-skills/blob/main/documentation/articles/professional_repo_rules.md).

### Ruby requirements
- Follow our list of [best practices for Ruby](https://github.com/microverseinc/curriculum-ruby/blob/main/articles/ruby_best_practices.md).

### Project requirements

- Check offical documentation about the following 3 methods in [Enumerable](https://ruby-doc.org/core-3.0.0/Enumerable.html). Make sure that you understand what they are doing.
  - [description of #all? method](https://ruby-doc.org/core-3.0.0/Enumerable.html#method-i-all-3F)
  - [description of #any? method](https://ruby-doc.org/core-3.0.0/Enumerable.html#method-i-any-3F)
  - [description of #filter method](https://ruby-doc.org/core-3.0.0/Enumerable.html#method-i-filter)
- Create a class `MyList` that has an instance variable `@list`.
- In `MyList` implement a method `#each` that yields successive members of `@list` and uses the `MyEnumerable` module.
- Create a module `MyEnumerable` that implements the following methods (they should have the same funcionality as methods in [Enumerable](https://ruby-doc.org/core-3.0.0/Enumerable.html)):
  - `#all?`
  - `#any?`
  - `#filter`
- Each class and module should has a separate .rb file.
- Verify your solution:
```ruby
# Create our list
irb> list = MyList.new(1, 2, 3, 4)
=> #<MyList: @list=[1, 2, 3, 4]>

# Test #all?
irb> list.all? {|e| e < 5}
=> true
irb> list.all? {|e| e > 5}
=> false

# Test #any?
irb> list.any? {|e| e == 2}
=> true
irb> list.any? {|e| e == 5}
=> false

# Test #filter
irb> list.filter {|e| e.even?}
=> [2, 4]
```


## Work and submission mode

- You should implement the above requirements only in **one repository** in your pair-programming group.
- You should ask for a review and submit this activity **on behalf of your pair-programming group.**


## Code review

Follow [these steps](https://github.com/microverseinc/curriculum-transversal-skills/blob/main/code-review/articles/how_to_ask_for_a_code_review.md) to request a code review of your project.

## Submit your project

After the final approval from a code reviewer, you need to submit your project.
[Read this FAQ for a reminder on how to submit your project.](https://microverse.zendesk.com/hc/en-us/articles/360061344234)
Now go to your Student Dashboard and submit your project.

# Additional requirements

*These are all optional, but if you're interested in exploring this topic further, feel free to implement them. Any exploration here should be done outside program time.*

*If you decide to implement these requirements you should do it in a separate pull request. As always, remember to clearly document your decision in GitHub comments.*

- For `MyEnumerable` implement:
  - [#max](https://ruby-doc.org/core-3.0.0/Enumerable.html#method-i-max)
  - [#min](https://ruby-doc.org/core-3.0.0/Enumerable.html#method-i-min)
  - [#sort](https://ruby-doc.org/core-3.0.0/Enumerable.html#method-i-sort)

------

_If you spot any bugs or issues in this activity, you can [open an issue with your proposed change](https://github.com/microverseinc/curriculum-transversal-skills/blob/main/git-github/articles/open_issue.md)._

# Ruby - features that are not so obvious

## Learning objectives

- Apply Ruby best practices and language style guides in code.

### Estimated time: 0.5h

## Description

All languages have features that are not immediately obvious or even taught to all new developers. You learn them through interaction with other developers rather than working by yourself.

### Why are these features important?

Knowing about these features will help you prevent bugs in your code, make your code more maintainable, and give you tools to write better code.

### Conditional variable initialization

Most languages have self-assignment operators like `+=` and `-=`, but Ruby takes this to another level by giving you a variant for pretty much all operators.

A particular case of this is `||=`, which we can use like `a ||= b` and is equivalent to `a = a || b`. Thanks to Ruby's `||` in which it returns the first truthy value we can use `||=` for conditional initialization, which is a fancy way of saying that we can give a value to the variable if it doesn't have one.

**Learn more about conditional initialization:**

- Read [Conditional initialization](https://rubystyle.guide/#double-pipe-for-uninit) from Ruby Style Guide.
- Take the [self-assignment](https://rubystyle.guide/#self-assignment) from Ruby Style Guide.

### Modules

In Ruby, modules are somewhat similar to classes: they are defining methods, just like classes do. However, modules can not be instantiated.
Instead modules can be included into classes, and this makes their methods available on the class. 

- Read [Modules](http://ruby-for-beginners.rubymonstas.org/advanced/modules.html)

### `yield`

On your journey learning Ruby you have most likely used methods that ask you to pass a block, but have you ever wondered how that works? Well the short answer is: `yield`.

`yield` is a keyword in Ruby and it is used to run a block received by the method where it is used, returning the value of the block. Think of it as a dynamic way of calling a function instead of hardcoding an actual call.

**Guiding questions:**

- Check the methods in the Enumerable module like [any?](https://ruby-doc.org/core-3.0.1/Enumerable.html#method-i-any-3F) and try to think how they use the block you pass and how they use `yield`.
- How does `yield` help build more adaptable methods?

**Learn more about `yield`:**

- [Guide to blocks](https://www.rubyguides.com/2016/02/ruby-procs-and-lambdas/).
- [Understanding yield](https://www.rubyguides.com/2019/12/yield-keyword/).
- [Short overview of using yield](https://stackoverflow.com/a/3066939).

### Safe navigation operator `&.`

You have probably been faced with the problem of chaining method calls, but one of the methods might return `nil` so you have to check for that.

```ruby
foo.bar.baz   # bar returns nil so this causes an exception

# You end up writing something like this
if foo.bar
  foo.bar.baz
end
```

Doing these checks can get tedious and error-prone, but thankfully Ruby comes to our rescue again with the safe navigation operator `&.`. This operator works just the same as `.`, but with the great property that if it has been called by `nil` it doesn't do the method call, instead it returns `nil`. With this in mind, we can rewrite our example to:

```ruby
foo&.bar&.baz
```

**Guiding questions:**

- When would using `&.` make your code easier to understand?
- What errors could it hide? When should you avoid using it?

**Learn more about `&.`:**

- [Safe navigation operator](https://ruby-doc.org/core-2.6/doc/syntax/calling_methods_rdoc.html#label-Safe+navigation+operator).
- [Safe navigation](https://rubyinrails.com/2017/11/17/safe-navigation-operator-ampersand-dot-in-ruby/).

------

_If you spot any bugs or issues in this activity, you can [open an issue with your proposed change](https://github.com/microverseinc/curriculum-transversal-skills/blob/main/git-github/articles/open_issue.md)._

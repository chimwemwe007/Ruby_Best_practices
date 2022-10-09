# Puts or print or maybe p?

There is not an only one way of printing in Ruby.

The most common methods are:
- print
- puts
- p

You could ask, what is the difference between them, and when you should use one over the another?

First `puts` always adds a new line character at the end of our message.
If you do not want to have new line just use print.

```ruby
puts "Hello"
puts "World!"

"Hello"
"World!"
```

```ruby
print "Hello"
print " World!"

"Hello World!"
```

Puts also displays array elements one per line:

```ruby
puts ["a", "b", "c"]
a
b
c
```

### What about `p`?
P in comparison to puts and print prints raw version of message. It can be useful while debugging our programs.
Simply `p` always return object that was passed as an argument.

```ruby
puts "Hello\n"
Hello
 => nil
```

```ruby
p "Hello\n"
"Hello\n"
 => "Hello\n"
```

------

_If you spot any bugs or issues in this activity, you can [open an issue with your proposed change](https://github.com/microverseinc/curriculum-transversal-skills/blob/main/git-github/articles/open_issue.md)._

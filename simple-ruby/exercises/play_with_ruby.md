# Play with Ruby

## Learning objectives
- Use Ruby syntax for basic programming operations.

### Estimated time: 1h

## Exercise

In this exercise you will try to execute a set of Ruby commands based on the syntax that you have learned in the previous lesson.

Do you remember the first script that we ran in IRB?

```ruby
> print "Hello World"
Hello World => nil
```

### Instructions

1. Open IRB.
2. Type the following expressions and check their results (press *enter* after typing each one):
- `2+2`
- `10/3`
- `10/3.0`
- `"Happy" + "coding"`
- `"Happy" + "\n" +  "coding"`
- `print "Happy" + "\n" +  "coding" + "\n"`
3. Now let's try to play with variables, type the following (press *enter* after typing each one):
- `a = 3`
- `a`
- `a = "Hello"`
- `a`
- `b = "World!"`
- `puts(a + b)`
4. As IRB is an Interactive Ruby Shell, we can use the full power of Ruby here to write more complex scripts. Let's start playing with that:
- Create the following method:
```ruby
irb(main)> def hello(name)
irb(main)>   puts("Hello #{name}!")
irb(main)> end
=> :hello
```
- Use the method (e.g `hello("David")`).
5. Write a method `add`, it takes 2 arguments (`a` and `b`), and it returns the addition of the two arguments.

### Submit your exercise
[Read this FAQ for a reminder on how to submit your exercise.](https://microverse.zendesk.com/hc/en-us/articles/360061344234)
Now go to your Student Dashboard and submit your exercise.

------

_If you spot any bugs or issues in this activity, you can [open an issue with your proposed change](https://github.com/microverseinc/curriculum-transversal-skills/blob/main/git-github/articles/open_issue.md)._

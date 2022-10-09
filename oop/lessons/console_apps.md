# Get user input and make file executable

## Learning objectives
- Build interactive console apps.

### Estimated time: 1h

## Description
In this lesson, you will learn how to turn Ruby script into an executable command-line program, what the difference between print and puts is, and how to get user input from the console.

### Why is it important?
You should know how to prepare Ruby scripts that can be used in the terminal without invoking Ruby, which can help you automate your work. These scripts could ask a user for inputs, for example, asking for the user's consent to perform some action.

## How to make Ruby script executable

First, you should know that there are several ways of running a script on your computer.
We can run scripts interactively in the interpreter -  IRB in the case of Ruby.
We also can add a filename as an argument to interpreter like: `ruby filename.rb`
Here our `filename.rb` does not have to be an executable file because the content of this file is loaded as input for the interpreter.
Finally, the most common way of running a script in Unix-based systems is to create an `executable file` and execute it.
How is this file different from typical files that we have on our computer? It starts with the magic line that begins with `#!` and then we have an absolute path to the interpreter. It simply tells the system which program to use to execute the remaining lines of the file.
That is not all! We also have to change the permissions on the file to make it executable. We can achieve this by running the following code in our terminal:

```bash
chmod 755 filename.rb
```

You can find a tutorial on how to make Ruby script executable [here](https://commandercoriander.net/blog/2013/02/16/making-a-ruby-script-executable/).

## How to print messages in the console

There are a few ways of displaying messages in your Ruby code. Read about them in the ["Puts or print or maybe p?" article](../articles/puts_print.md).

## How to get user input

Let's talk about our Hello World example once again. We will ask the user to input his or her name and then print the "Hello name" message on the user's screen.
We will use the `gets.chomp` function to achieve this. While processing `gets.chomp` Ruby will prompt the user for input and it stops flow execution until the user hits enter. After hitting enter Ruby will take whatever they entered and be able to use it going forward in its execution flow.

```ruby
puts "What is your name?"
name = gets.chomp
puts "Hello #{name}!"
```

## Console app entry-point

Different from other programming languages, Ruby doesn't have a `main` function (a predefined entry point when executing a binary). So how is a Ruby script executed? Top-to-bottom, everything is executed as it appears.

Because of this, it is a good practice when making scripts and console apps to not put code outside of class's and method's declaration. Everything goes inside a method and the last method is a `main` method which is immediately called by the script on the last line.

Example of a bad `main.rb`:
```ruby
def my_function(foo)
  ...
end

def save(bar)
  ...
end

a = 4
b = my_function(a)
save(b)
```

Example of a good `main.rb`:
```ruby
def my_function(foo)
  ...
end

def save(bar)
  ...
end

def main
  a = 4
  b = my_function(a)
  save(b)
end

main()
```

Another good practice is to create an `App` class to hold the state of your app and the run logic. Using your App class, transform your main.rb to something like this:

```ruby
class App
  ...
end

...

def main
  app = App.new()
  app.run()
end

main()
```

------

_If you spot any bugs or issues in this activity, you can [open an issue with your proposed change](https://github.com/microverseinc/curriculum-transversal-skills/blob/main/git-github/articles/open_issue.md)._

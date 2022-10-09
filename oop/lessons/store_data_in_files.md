# Store data in files

## Learning objectives
- Store data in files.

### Estimated time: 2h

## Description
Eventually you are going to create programs that will need some way to persist data between uses. One way to persist data is to just store it in a file. In this lesson, you will learn how to do this.

### Why is storing data in files important?
Because it's the only true way of persisting data. You might think about databases or other things as ways to persist data as well, but all those things eventually write to files, because, as mentioned, it is the only way to truly persist data in software.

**Guiding questions:**

*Think about these questions as you learn about storing data in files.*

- How would you preserve information gathered by a script so later calls can know about that information?
- How do you store data without overwriting previous data?

### Storing data in files
Eventually you will need to preserve data from your program. In this case writing to a file is a good choice. Before actually writing your data you will have to figure out how to represent it in the file and how to read it back into your application.

For example, if your application is storing lists of names your format can be to put one name per line in the file. This means that when writing you put a newline after every name and when reading the file you know that names are separated by a newline.

To learn more about storing data in files read the following articles:
- [IO in Ruby](https://thoughtbot.com/blog/io-in-ruby)
- [Using File class with examples](https://www.rubyguides.com/2015/05/working-with-files-ruby/)

## Additional materials
**These are all optional, but if you're interested in exploring this topic further, here are some resources to help you. Any exploration here should be done outside program time.**

- [Data serialization](https://devopedia.org/data-serialization)
- [Choosing the right serialization format](https://www.sitepoint.com/choosing-right-serialization-format/)

------

_If you spot any bugs or issues in this activity, you can [open an issue with your proposed change](https://github.com/microverseinc/curriculum-transversal-skills/blob/main/git-github/articles/open_issue.md)._

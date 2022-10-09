# Class vs object: examples

In this article, we'll go through the process of creating a class (`Animal`) and the creation of objects of it (instances). Also, we'll see how you can define a constructor and instance variables for the class.

Ideally, you should follow along in an IRB console and observe the different steps and outputs.

### Class definition

First, let's create the class `Animal` and make some instances of it.

```ruby
class Animal
end

animal_1 = Animal.new
animal_2 = Animal.new

animal_1
animal_2
```

### Constructor and instance vars

Next, we will create our constructor (in Ruby it is the `initialize` method) and declare some instance variables that we want in our `Animal` class:
- An `id` which is going to be a random integer between 1 and 1000
- A `name`, for now, it will always be `"Rex"`
- The `number_of_legs`, for now, it will be set to `4`

```ruby
class Animal
  def initialize
    @id = Random.rand(1..1000)
    @name = "Rex"
    @number_of_legs = 4
  end
end

animal_1 = Animal.new
animal_2 = Animal.new

animal_1
animal_2
```

### Constructor with parameters

As you saw we had some hardcoded values for `@name` and `@number_of_legs`, which is less than ideal because animals can have different names and numbers of legs. So now let's modify our constructor to accept parameters and use them.

```ruby
class Animal
  def initialize(name, number_of_legs)
    @id = Random.rand(1..1000)
    @name = name
    @number_of_legs = number_of_legs
  end
end

animal_1 = Animal.new("Rex", 4)
animal_2 = Animal.new("Bob", 8)

animal_3 = Animal.new
animal_4 = Animal.new("Rex")


animal_1
animal_2
```

### Constructor with optional parameters

Sometimes parameters have pretty much the same value every time or you just don't know what to send at the moment. To solve this we can use an optional parameter in our constructor for `name`.

```ruby
class Animal
  def initialize(number_of_legs, name = "Unknown")
    @id = Random.rand(1..1000)
    @name = name
    @number_of_legs = number_of_legs
  end
end

animal_1 = Animal.new(4, "Rex")
animal_2 = Animal.new(8)


animal_1
animal_2
```

### Method definition

Finally, let's add a method so our animals can `speak`

```ruby
class Animal
  def initialize(number_of_legs, name = "Unknown")
    @id = Random.rand(1..1000)
    @name = name
    @number_of_legs = number_of_legs
  end

  def speak
    "Bla bla bla"
  end
end

animal_1 = Animal.new(4, "Rex")
animal_2 = Animal.new(8)

animal_1.speak
animal_2.speak
```

------

_If you spot any bugs or issues in this activity, you can [open an issue with your proposed change](https://github.com/microverseinc/curriculum-transversal-skills/blob/main/git-github/articles/open_issue.md)._

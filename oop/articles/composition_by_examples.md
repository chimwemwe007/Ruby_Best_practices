# Composition by example

In this article, we are going to build on top of what we did in ["OOP: four principles by example"](./oop_principles_examples.md) and add some functionality following a composition design.

While reading this article, create your files with classes and try some code in your IRB console. Keep the files you create saved for upcoming lessons.

### What are we composing?
We are going to add the following two features to our objects by composing them:
- a method to reduce the number of legs by one.
- a method to tell if the animal likes a type of food or not.

### Composable classes

> Method to reduce the number of legs by one.

Let's create a class called `Remover` (in a file `remover.rb`) that will receive the number of legs and optionally how many to reduce them by.

```ruby
class Remover
  def decrease(number, step = 1)
    number -= step
  end
end
```

So, how can we use this? Well, we can use this directly in a method in our `Animal` class, but remember to add the `require` for file `remover.rb`.

```ruby
require "./remover.rb"

class Animal
  ...

  def remove_leg
    remover = Remover.new()
    @number_of_legs = remover.decrease(@number_of_legs)
  end

  ...
end
```

Great! Now you can reduce `@number_of_legs` if needed. Now on to the next feature.

<details>
<summary>Try it out in your IRB console</summary>

```ruby
require "./animal.rb"
require "./dog.rb"
require "./spider.rb"

animal = Animal.new("lion", 4, "Rex")
dog = Dog.new("black", "Rex")
spider = Spider.new(85, "Wilma")

animal.number_of_legs
dog.number_of_legs
spider.number_of_legs

animal.remove_leg()
dog.remove_leg()
spider.remove_leg()

animal.number_of_legs
dog.number_of_legs
spider.number_of_legs
```

</details>

> Method to tell if the animal likes a type of food or not

For this we are going to create some classes (`NoFood`, `DogFood`, and `SpiderFood`) that will have a list of foods and a method to tell you if one is on the list or not (abstraction!).

You can create the classes in a single file called `foods.rb`.

```ruby
class NoFood
  def is_liked?(food)
   false
  end
end

class DogFood
  def is_liked?(food)
   ["meat", "vegetable", "fruit"].member?(food)
  end
end

class SpiderFood
  def is_liked?(food)
   ["insect", "bug"].member?(food)
  end
end
```

Next, we modify our classes to set `@liked_food`.

Modify `dog.rb` to require `foods.rb` and set `DogFood` as `@liked_food`.

```ruby
...
require "./foods.rb"

class Dog < Animal
  def initialize(color, name = "Unknown")
    super("dog", 4, name)
    @color = color
    @liked_food = DogFood.new()
  end

  ...
end
```

Modify `spider.rb` to require `foods.rb` and set `SpiderFood` as `@liked_food`.

```ruby
...
require "./foods.rb"

class Spider < Animal
  def initialize(web_strength_level, name = "Unknown")
    super("spider", 8, name)
    @web_strength_level = web_strength_level
    @liked_food = SpiderFood.new()
  end

  ...
end
```

And finally, modify `animal.rb` to require `foods.rb` and set `NoFood` as `@liked_food`. Also, we need to add a method `likes_food?` that uses `@liked_food` and will be inherited by `Dog` and `Spider`

```ruby
...
require "./foods.rb"

class Animal
  def initialize(type, number_of_legs, name = "Unknown")
    ...
    @liked_food = NoFood.new()
  end

  ...

  def likes_food?(food)
    @liked_food.is_liked?(food)
  end
end
```

Excellent, now you can tell what food your animal likes and in the future you can make it changeable!

<details>
<summary>Try it out in your IRB console</summary>

```ruby
require "./animal.rb"
require "./dog.rb"
require "./spider.rb"

animal = Animal.new("lion", 4, "Rex")
dog = Dog.new("black", "Rex")
spider = Spider.new(85, "Wilma")

animal.likes_food?("meat")
dog.likes_food?("meat")
spider.likes_food?("meat")

animal.likes_food?("bug")
dog.likes_food?("bug")
spider.likes_food?("bug")
```

</details>

------

_If you spot any bugs or issues in this activity, you can [open an issue with your proposed change](https://github.com/microverseinc/curriculum-transversal-skills/blob/main/git-github/articles/open_issue.md)._

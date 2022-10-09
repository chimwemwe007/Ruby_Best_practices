# Ruby group capstone - Catalog of my things

## Learning objectives
- Insert and query data in SQL.
- Use primary key & foreign key mechanisms for joining tables.
- Understand the different types of relationships between tables.
- Query multiple tables.
- Prepare complex queries that answer analytical questions.
- Run a program using the command line.
- Use Ruby syntax for basic programming operations.
- Apply Ruby best practices and language style guides in code.
- Describe the SOLID principles of OOP.
- Implement classes and objects in Ruby.
- Understand the four main principles of OOP.
- Implement encapsulation and inheritance with Ruby.
- Create a UML class diagram.
- Explain the difference between associations, aggregations, and composition in OOP.
- Set up associations between classes and objects.
- Store data in files.
- Build interactive console apps.
- Recognize the value of making equal contributions to group projects to produce the best outcome. 

### Estimated time: 19h

## Description

In this project, you will create a console app that will help you to keep a record of different types of things you own: books, music albums, movies, and games.
Everything will be based on the UML class diagram presented below. The data will be stored in JSON files but you will also prepare a database with tables structure analogical to your program's class structure.

### How to build the "Catalog of my things" app

"Catalog of my things" should be a simple console app that allows users to manage collections of the things they own. It should be based on the following UML class diagram.

<p align="center">
  <img src="./images/catalog_of_my_things.png" alt="C=UML class diagram for catalog of things" />
</p>

*IMPORTANT NOTE: Read **all** requirements before you start building your project.*

### General requirements

- Make sure that there are [no linter errors](https://github.com/microverseinc/linters-config).
- Make sure that you used correct [Gitflow](https://github.com/microverseinc/curriculum-transversal-skills/blob/main/git-github/articles/gitflow.md).
- Make sure that you documented your work [in a professional way](https://github.com/microverseinc/curriculum-transversal-skills/blob/main/documentation/articles/professional_repo_rules.md).

### Ruby requirements

- Follow our list of [best practices for Ruby](https://github.com/microverseinc/curriculum-ruby/blob/main/articles/ruby_best_practices.md).

### Project requirements

#### Logic

- Each class from the [UML class diagram](./images/catalog_of_my_things.png) should be created in a separate .rb file.
- All associations (1-to-many relationships) and aggregations (parent-child relationships) between classes should be implemented.
- All properties visible in the diagram should be defined and set up in the constructor method. _Exception: properties for the 1-to-many relationships should NOT be set in the constructor method. Instead, they should have a custom setter method created._
- All methods visible in the diagram should be implemented:
    - add_item method (in all classes that have that method)
        - should take an instance of the Item class as an input.
        - should add the input item to the collection of items.
        - should add self as a property of the item object (by using the correct setter from the item object).
    - can_be_archived?() in the Item class
        - should return true if published_date is older than 10 years.
        - otherwise, it should return false.
    - move_to_archive() in the Item class
        - should reuse can_be_archived?() method.
        - should change the archived property to true if the result of the can_be_archived?() method is true.
        - should do nothing if the result of the can_be_archived?() method is false.
    - can_be_archived?() in the Book class
        - should override the method from the parent class.
        - should return true if parent's method returns true OR if cover_state equals to "bad".
        - otherwise, it should return false.
    - can_be_archived?() in the MusicAlbum class
        - should override the method from the parent class.
        - should return true if parent's method returns true AND if on_spotify equals true.
        - otherwise, it should return false.
    - can_be_archived?() in the Movie class
        - should override the method from the parent class.
        - should return true if parent's method returns true OR if silent equals true.
        - otherwise, it should return false.
    - can_be_archived?() in the Game class
        - should override the method from the parent class.
        - should return true if parent's method returns true AND if last_played_at is older than 2 years.
        - otherwise, it should return false.
- Add unit tests for all implemented methods.

#### User interface

- Create a main.rb file that will serve as your console app entry-point.
- Your console app, at the start, should:
    - Present the user with a list of options to perform.
    - Let users choose an option.
    - If needed, ask for parameters for the option.
    - Have a way to quit the app.
- The following options should be available:
    - List all books
    - List all music albums
    - List all movies
    - List of games
    - List all genres (e.g 'Comedy', 'Thriller')
    - List all labels (e.g. 'Gift', 'New')
    - List all authors (e.g. 'Stephen King')
    - List all sources (e.g. 'From a friend', 'Online shop')
    - Add a book
    - Add a music album
    - Add a movie
    - Add a game
 - All data should be preserved by saving collections in .json files.

### Database
- Create a schema.sql file with tables that will be analogical to the structure of the classes in your app. As you cannot implement inheritance in the database tables - add all properties and associations from the parent Item class as table columns to all tables based on the child classes. Thanks to that it can be used to store data in the future.

### Project documentation

Once you have finished the development of the project, you should record a video presenting the features of the project you built. It is a video with a **maximum length of 5 minutes**. The content of the video should include:

- A description of the project.
- A demo of the project features.
- You should also highlight some interesting piece of code or something you built that you are very proud of.
- You all should appear in the video and talk about the project.

For recording the video you can use the Zoom recording features while in a call with your peers.

### Workload distribution

In order to tackle this challenge, we created an almost empty [Kanban board template](https://github.com/microverseinc/curriculum-ruby/projects/1) -  you can see only the task's placeholders. However, we grouped the above requirements into [lists for each member of your team](catalog_of_my_things_divided.md). You will create your own copy of that template Kanban board **and you will create tasks on your own** in the separate activity. 

You will be working in this way:
- The group tasks (e.g., set up repo) will be divided among all of you or completed as a team (pair programming).
- The other tasks related to the project will be developed individually. Every student will own tasks that will give a chance to practice a variety of skills.
- All tasks should be based on the cards from your Kanban board.


## Work and submission mode

- You should implement the above requirements only in **one repository** in your group.
- You should ask for a review and submit this activity **on behalf of your group.**

## Code review

You will give and receive code reviews from your teammates. Each task should have a separate pull request that is reviewed by one of your teammates.
Once the entire project is ready, one of your team members will request a code review on behalf of your group.
For both processes follow [these steps](https://github.com/microverseinc/curriculum-transversal-skills/blob/main/code-review/articles/code_review_flow_group_projects.md).

## Submit your project

After the final approval from a code reviewer, you need to submit your project.
[Read this FAQ for a reminder on how to submit your project](https://microverse.zendesk.com/hc/en-us/articles/360061344234).

Now go to your Student Dashboard and submit your project.

## Additional requirements

*These are all optional, but if you're interested in exploring this topic further, feel free to implement them. Any exploration here should be done outside program time.*

*If you decide to implement these requirements you should do it in a separate pull request. As always, remember to clearly document your decision in GitHub comments.*

- Think about other options you might implement in your console app, e.g:
    - remove a selected book
    - add genre to selected book
    - ...

------

_If you spot any bugs or issues in this activity, you can [open an issue with your proposed change](https://github.com/microverseinc/curriculum-transversal-skills/blob/main/git-github/articles/open_issue.md)._

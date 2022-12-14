# Ruby group capstone - Catalog of my things: divided requirements

This document should help you to translate the project requirements into specific tasks and split them between team members.
Please analyze how each item on this list corresponds to the original list of requirements.

### Group task
- Create Item class in a separate .rb file.
- All Item class properties visible in the diagram should be defined and set up in the constructor method. _Exception: properties for the 1-to-many relationships should NOT be set in the constructor method. Instead, they should have a custom setter method created._
- Add all methods visible in the diagram.
- Implement methods:
    - can_be_archived?() in the Item class
        - should return true if published_date is older than 10 years
        - otherwise, it should return false
    - move_to_archive() in the Item class
        - should reuse can_be_archived?() method
        - should change the archived property to true if the result of the can_be_archived?() method is true
        - should do nothing if the result of the can_be_archived?() method is false
 - Create a main.rb file that will serve as your console app entry-point.
 - Implement startup actions:
    - Present the user with a list of options to perform.
    - Let users choose an option.
    - If needed, ask for parameters for the option.
    - Have a way to quit the app.

### Team member #1
- Create a Book class in a separate .rb file.
- Create a Label class with an association to the Item class (in a separate .rb file).
- All Book class properties visible in the diagram should be defined and set up in the constructor method.
- All Label class properties visible in the diagram should be defined and set up in the constructor method.
- Implement methods:
    - add_item method in the Label class
        - should take an instance of the Item class as an input
        - should add the input item to the collection of items
        - should add self as a property of the item object (by using the correct setter from the item object)
    - can_be_archived?() in the Book class
        - should override the method from the parent class
        - should return true if parent's method returns true OR if cover_state equals to "bad"
        - otherwise, it should return false
- Add unit tests for all implemented methods.
- The following options should be available:
    - List all books
    - List all labels (e.g. 'Gift', 'New')
    - Add a book
- All data should be preserved by saving collections in .json files.
- Create a schema.sql file with tables that will be analogical to the structure of the classes that you created:
    - books table (add all properties and associations from the parent Item class as table columns)
    - labels table

### Team member #2
- Create MusicAlbum class in a separate .rb file.
- Create Genre class with an association to the Item class (in a separate .rb file).
- All MusicAlbum class properties visible in the diagram should be defined and set up in the constructor method.
- All Genre class properties visible in the diagram should be defined and set up in the constructor method.
- Implement methods:
    - add_item method in the Genre class
        - should take an instance of the Item class as an input
        - should add the input item to the collection of items
        - should add self as a property of the item object (by using the correct setter from the item object)
    - can_be_archived?() in the MusicAlbum class
        - should override the method from the parent class
        - should return true if parent's method returns true AND if on_spotify equals true
        - otherwise, it should return false
 - Add unit tests for all implemented methods.
 - The following options should be available:
    - List all music albums
    - List all genres (e.g 'Comedy', 'Thriller')
    - Add a music album
 - All data should be preserved by saving collections in .json files.
 - Create a schema.sql file with tables that will be analogical to the structure of the classes that you created:
    - music_albums table (add all properties and associations from the parent Item class as table columns)
    - genres table

### Team member #3 (if the team has 2 members - divide these tasks between yourselves)
- Create a Game class in a separate .rb file.
- Create an Author class with an association to the Item class (in a separate .rb file).
- All Game class properties visible in the diagram should be defined and set up in the constructor method.
- All Author class properties visible in the diagram should be defined and set up in the constructor method.
- Implement methods:
    - add_item method in the Author class
        - should take an instance of the Item class as an input
        - should add the input item to the collection of items
        - should add self as a property of the item object (by using the correct setter from the item object)
    - can_be_archived?() in the Game class
        - should override the method from the parent class
        - should return true if parent's method returns true AND if last_played_at is older than 2 years
        - otherwise, it should return false
- Add unit tests for all implemented methods.
- The following options should be available:
    - List of games
    - List all authors (e.g. 'Stephen King')
    - Add a game
 - All data should be preserved by saving collections in .json files.
 - Create a schema.sql file with tables that will be analogical to the structure of the classes that you created:
    - games table (add all properties and associations from the parent Item class as table columns)
    - authors table

### Team member #4 (if your team has 3 members - skip those requirements)
- Create Movie class in a separate .rb file.
- Create Source class with an association to the Item class (in a separate .rb file).
- All Movie class properties visible in the diagram should be defined and set up in the constructor method.
- All Source class properties visible in the diagram should be defined and set up in the constructor method.
- Implement methods:
    - add_item method in the Source class
        - should take an instance of the Item class as an input
        - should add the input item to the collection of items
        - should add self as a property of the item object (by using the correct setter from the item object)
    - can_be_archived?() in the Movie class
        - should override the method from the parent class
        - should return true if parent's method returns true OR if silent equals true
        - otherwise, it should return false
- Add unit tests for all implemented methods.
- The following options should be available:
    - List all movies
    - List all sources (e.g. 'From a friend', 'Online shop')
    - Add a movie
- All data should be preserved by saving collections in .json files.
- Create a schema.sql file with tables that will be analogical to the structure of the classes that you created:
    - movies table (add all properties and associations from the parent Item class as table columns)
    - sources table

------

_If you spot any bugs or issues in this activity, you can [open an issue with your proposed change](https://github.com/microverseinc/curriculum-transversal-skills/blob/main/git-github/articles/open_issue.md)._

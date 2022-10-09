# Classes - association, aggregation, composition

## Learning objectives
- Explain the difference between associations, aggregations, and composition in OOP.
- Set up associations between classes and objects.

### Estimated time: 1.5h

## Description
In this lesson, you will learn about associations, aggregations, and composition. These are some of the possible relationships that classes in OOP can have between them.

### Why are association, aggregation, and composition important?
Because understanding these relationships and their representation in UML will allow you to correctly implement the designed solution.

### Association, aggregation, and composition
An association represents a relationship between two objects, but neither is the "owner" of the other. They each exist on their own and can be related eventually.

An aggregation is a specialized association in which both objects maintain their independence, but there is an owner of one over the other.

A composition is a specialized aggregation, with the difference that the child's class life depends on the parent. If the parent (owner) is deleted the child is deleted as well, but the reverse is not true.

To learn more about association, aggregation, and composition, read the following articles:
- [Association, aggregation, and composition](https://www.infoworld.com/article/3029325/exploring-association-aggregation-and-composition-in-oop.html#:~:text=Association%20in%20object%20oriented%20programming,and%20there%20is%20no%20owner)
- [Understanding OOP relationships](https://shouts.dev/understanding-oop-concepts-association-composition-aggregation)
- [Association, aggregation, and composition by examples](../articles/oop_relationships_by_examples.md)

------

_If you spot any bugs or issues in this activity, you can [open an issue with your proposed change](https://github.com/microverseinc/curriculum-transversal-skills/blob/main/git-github/articles/open_issue.md)._

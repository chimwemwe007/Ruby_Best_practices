# Do's and don'ts while working with a team

## Learning objectives
- Use git responsibly in a team.
- Grow skills in using Kanban boards and understand strategies for their effective use.

### Estimated time: 1h

## Description
In this lesson, you will read about a few rules that can make collaboration with your team better.

### Why is it important?
You already experienced working on a group project. You are practicing collaboration skills in many other activities.
Because you will soon be working in a larger group, we would like to present you with a handy list of tips that are based on the lessons you already took.
Please reflect on them before you meet with your team and remember to use them while working on the next project.

### Do's and don'ts while working with a team

### Managing workload
- Use a Kanban board to divide tasks and to track the progress.
- When dividing the task, think about the way that will enable team members to get as much as possible done independently and autonomously. Look for the areas of the requirements that can be grouped and implemented by the same person.
- Use self and team views in your Kanban board - to track the progress of the entire team and individual people. In the GitHub project, you can do it by [filtering cards](https://docs.github.com/en/issues/organizing-your-work-with-project-boards/tracking-work-with-project-boards/filtering-cards-on-a-project-board) by the assignee.

### Managing overlapping tasks

- Proactively communicate with your teammates if your task can influence others' tasks.
- In the case of any conflicts between your code and someone's else code - discuss it together to decide which version should be the final one.

#### Making changes in your commits
- Rule number one: never change public commits (public = were pushed to the GitHub). If you change the commit that was already pulled by your teammates, you will have a hard time fixing it.
- The easiest and safest way is to change your last commit (while it is still only on your machine - see rule number one above). You can do it with the [`git commit --amend`](https://www.atlassian.com/git/tutorials/rewriting-history#git-commit--amend) command.
- At some point you might have to change older commits (again, make sure that none of the commits you want to change is public). In order to do that, you can use the [`git rebase -i`](https://www.atlassian.com/git/tutorials/rewriting-history#git-rebase-i) command. **Use `git rebase -i` only if you are 100% sure that you know what you are doing.**

------

_If you spot any bugs or issues in this activity, you can [open an issue with your proposed change](https://github.com/microverseinc/curriculum-transversal-skills/blob/main/git-github/articles/open_issue.md)._

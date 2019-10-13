## Commit messages

> What are they, and why are they important?

Every version control system has the facility to add a description message to your commit. These are commit messages.

The most important reason to write descriptive commit messages is so that, when the build breaks, you know who broke it and why. However this is not the only reason. Not writing descriptive commit messages normally occurs when:

- You have a complex problem under a tight deadline
- You have numerous bugs to fix under a tight deadline, and the commit message will not cover the scope of the changes (remedy for this is to make smaller commits)

A frequent scenario normally plays out like this:

- You find a bug that is because of a strange line of code
- You use version control to figure out who the commit author was, and when the line of code was modified
- The author of the commit is off on holiday or has gone home for the night, and left a commit message saying "fixed an obscure bug"
- You modify the line of code to what you believe the fix is
- Something else breaks
- You spend hours trying to get the application running again

A descriptive commit message could have saved you hours of debugging. Which is why they are so important.
### Git
- Git is an **open-source** distributed version control system created by Linus Torvalds in 2005.
- Git is a powerful and widely used **version control system** that helps developers track changes in their code, collaborate with others, and manage project history effectively.
- It enables multiple developers to work on the same project simultaneously. Changes can be merged seamlessly, and conflicts can be resolved easily.
- It allows us to create branches for new features or experiments without affecting the main branch.
- Each developer has a complete copy of the repository, including its history. This decentralization enhances collaboration and backup capabilities.

### Repositories

A repository (or repo) is a storage space where your project files and their history are kept. There are two types of repositories in Git:

- **Local Repository**: A copy of the project on your local machine.
- **Remote Repository**: A version of the project hosted on a server, often on platforms like GitHub, GitLab, or Bitbucket.



### Commits

A commit is a recorded snapshot of the project at a specific point in time. 

- **Unique Identifier (Hash)**: A SHA-1 hash that uniquely identifies the commit.
- **Commit Message**: A brief description of the changes made in that commit.
- **Author Information**: The name and email of the person who made the commit.
- **Timestamp**: The date and time when the commit was made.



### Branches

A branch is a parallel version of your repository, allowing you to work on different features or fixes independently. 

- **Default Branch**: Typically named main or master. This branch usually contains the stable, production-ready code.
- **Feature Branches**: Branches created to develop new features or make specific fixes. For example, you might create a branch named feature/login to work on a new login feature.



### Merging

Merging is the process of combining changes from one branch into another. This operation integrates different lines of development and resolves conflicts if changes overlap.

- **Fast-Forward Merge**: When the target branch is directly ahead of the source branch, Git simply moves the branch pointer forward.
- **Three-Way Merge**: When both branches have diverged, Git performs a three-way merge that includes changes from both branches and creates a new merge commit.



### Cloning

Cloning is the process of creating a local copy of a remote repository. This operation includes all the project files, commit history, and branches, allowing you to work with a complete and independent copy of the project.
``git clone <repository-url>``



### Pull and Push

- **Pull**: Fetches updates from the remote repository and merges them into your local repository. This command is used to synchronize your local work with the changes made by others.

``git pull``

- **Push**: Sends your local commits to the remote repository, making them available to others. This command updates the remote repository with your changes.

``git push``








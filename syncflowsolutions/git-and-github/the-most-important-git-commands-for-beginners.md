# Basic Git commands for beginners

Git is a version control system that allows developers to track changes in their code and collaborate with other developers. It is an essential tool for any software development project, and understanding the basics of Git is essential for any developer. Here are some of the most important Git commands that all beginners should understand:

1. git init: This command is used to initialize a new Git repository. It creates a hidden .git directory in the current working directory, which stores all of the version control information for the project. This command should be run once at the beginning of a new project.

Example:

```bash
git init
```

Output:

```bash
Initialized empty Git repository in /path/to/project/.git/
```

2. git add: This command is used to add files to the staging area of a Git repository. It allows developers to select which changes they want to include in the next commit.

Example:

```bash
git add filename.txt
```

3. git commit: This command is used to save changes to a Git repository. It takes all of the changes that have been added to the staging area and creates a new commit with those changes.

Example:

```bash
git commit -m "Commit message"
```

Output:

``` bash
[master (root-commit) 8f3d9a2] Commit message
 1 file changed, 1 insertion(+)
 create mode 100644 filename.txt
```

4. git push: This command is used to push changes from a local repository to a remote repository. It takes all of the commits that have been made locally and pushes them to the remote repository.

Example:

```bash
git push origin master
```

Output:

```bash
Counting objects: 3, done.
Delta compression using up to 4 threads.
Compressing objects: 100% (2/2), done.
Writing objects: 100% (3/3), 294 bytes | 0 bytes/s, done.
Total 3 (delta 0), reused 0 (delta 0)
To <https://github.com/username/repo.git>
   8f3d9a2..f8b5c6e  master -> master
```

5. git pull: This command is used to pull changes from a remote repository to a local repository. It takes all of the commits that have been made remotely and pulls them into the local repository.

Example:

```bash
git pull origin master
```

Output:

```bash
From <https://github.com/username/repo>

* branch            master     -> FETCH_HEAD
Updating 8f3d9a2..f8b5c6e
Fast-forward
 filename.txt |    1 +
 1 file changed, 1 insertion(+)
```

These are just a few of the most important Git commands that all beginners should understand. For more information on Git and how to use it, check out the official documentation at <https://git-scm.com/doc>.

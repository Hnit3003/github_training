# Git pull

The `git pull` command is used to fetch and download content from a remote repository and immediately update the local repository to match that content. Merging remote upstream changes into your local repository is a common task in Git-based collaboration work flows. The `git pull` command is actually a combination of two other commands, git fetch followed by git merge. In the first stage of operation git pull will execute a git fetch scoped to the local branch that `HEAD` is pointed at. Once the content is downloaded, git pull will enter a merge workflow. A new merge commit will be-created and `HEAD` updated to point at the new commit.

You can think of `git pull` as Git's version of `svn update`. It’s an easy way to synchronize your local repository with upstream changes. The following diagram explains each step of the pulling process.

[<img src="./Git_pull_discussion_1.svg" width="600"/>](../media/shield_twisted_pair.png)

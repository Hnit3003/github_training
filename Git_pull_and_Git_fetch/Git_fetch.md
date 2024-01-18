# Git fetch

The `git fetch` command downloads commits, files, and refs from a **remote repository** into your **local repo**. Fetching is what you do when you want to see what everybody else has been working on. It’s similar to `svn update` in that it lets you see how the central history has progressed, but it doesn’t force you to actually merge the changes into your repository. Git isolates fetched content from existing local content; it has absolutely no effect on your local development work. Fetched content has to be explicitly checked out using the git checkout command. This makes fetching a safe way to review commits before integrating them with your local repository.

When downloading content from a remote repo, `git pull` and `git fetch` commands are available to accomplish the task. You can consider `git fetch` **the 'safe' version** of the two commands. It will download the remote content but not update your local repo's working state, leaving your current work intact. `git pull` is the more aggressive alternative; it will download the remote content for the active local branch and immediately execute git merge to create a merge commit for the new remote content. If you have pending changes in progress this will cause conflicts and kick-off the merge conflict resolution flow.

## Synchronize origin with git fetch

The following example walks through the typical workflow for synchronizing your local repository with the central repository's main branch.
`git fetch origin`

This will display the branches that were downloaded:
`a1e8fb5..45e66a4 main -> origin/main`
`a1e8fb5..9e8ab1c develop -> origin/develop`
`* [new branch] some-feature -> origin/some-feature`

To see what commits have been added to the upstream main, you can run a git log using origin/main as a filter:  
`git log --oneline main..origin/main`

To approve the changes and merge them into your local main branch use the following commands:
`git checkout main`
`git log origin/main`

Then we can use git merge origin/main:
`git merge origin/main`

The origin/main and main branches now point to the same commit, and you are synchronized with the upstream developments.

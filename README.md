# Git Good - Tips & Tricks w/ Git

## Intent
Share tips and tricks that I have found useful that I wish someone had shown me when I was first getting started.  And even after years of experience.
I'm hoping to keep this light on opinions and heavy on the tips and tricks.  I'll try, anyways... x\_x
This piece is assuming you have at minimum a general/working knowledge of git.

## Quick Overview
1. Brief history / comparison
1. Brief overview
1. Actual tips & tricks w/ live examples
1. Resources

## Brief History
Before there was git, there was....
- svn
- cvs
- rcs
- so so so many others

Okokokokokokokokok.  So why git?
- It's local.  You get the whole repo/world when you clone
- Distributed model.  Not a single point of failure.  Every copy of a repo is a complete repo on it's own
- can rewrite the history!  Ex/ squashing, rebasing, etc.
- Merging (from multiple sources) is a breeze
- Lots of handy functionality.  Some highlights on that below


## Quick Overview
- working copy
- staging area
- repository

## Visual Overview

Working in a git repo:
1. local changes (local, unstaged, uncommitted)
1. staging area (local, uncommitted)
1. repository (local, committed)
1. remote (non-local, committed)

```mermaid
flowchart TB
    subgraph wd[working directory]
        n1(local changes)
    end
    
    subgraph staging[staging area]
        n2(test)
    end

    subgraph repo[repository]
        n3(test)
    end

    subgraph origin[origin]
        n4('remote' named 'origin' </br> by convention)
    end

    wd -- git add --> staging
    staging -- git reset HEAD -- --> wd

    staging -- git commit --> repo
    repo -- it's complicated ... </br> git reset HEAD^ --> staging

    repo -- git push origin HEAD --> origin
    origin -- N/A --> repo
```

## Tips & Tricks
1. git aliases
    - simple ones
    - multi-command functions
    - etc.
1. git log
    - Use the git log !!!!!
    - Help make it more useful.  Craft better commit messages!  
    - Hopefully understanding what the log can do helps to show what makes a good commit message
    - only as good as you make it... squash your commits AND messages
    - filenames
    - search by string
    - graphs
    - skim/jump/etc commit messages
        - `git log` + `/${SEARCH_STRING}`
        - `git log --oneline`
        - `git log --patch`
        - `git show ${COMMIT}` # JUST that specific commit
        - `git diff origin HEAD` # 
        - `git apply ~/my-git-patch`
1. git reflog
    - recover lost branch, commits, etc.
    - recover unnitended changes
1. git cherry-pick
1. git patch + git apply
1. git rebase
    - `git rebase -i HEAD~4`
    - `git rebase -i HEAD^^^^`
        - `-i` for "interactive"
1. git diff
    - Diffs are human AND machine readable !
        - `git diff origin HEAD`
        - `git diff HEAD`
        - `git diff main`
        - `git diff origin/main`




## Resources
- [Tim Pope - A Not About Git Commit Messages](https://tbaggery.com/2008/04/19/a-note-about-git-commit-messages.html)
- [Github Blog - on commit messages](https://github.blog/2011-09-06-shiny-new-commit-styles/)
- [List of Version Control Software (Wikipedia)](https://en.wikipedia.org/wiki/List_of_version-control_software)


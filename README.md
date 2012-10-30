Git and Github for designers and developers

Objectives: at the end of this presentation the learners will have a basic knowledge of how to use git/github for both personal and team based projects. They will gain this knowledge through a combination of demonstrations, and by hands on activities.

Prerequisite: have a github account (preferably, with ssh keys set up on your local machine)

(5-10m) - Why use git?
  - collaboration
  - don’t lose work
  - view your history
  - attribute work to people
  - track down bugs

Git is the current standard in open source. Nice feature: every checkout has a complete history and can work offline, though this adds complexity. GitHub is a hugely popular commercial service that works with git.

Create an account on GitHub
  Later, to automate logging in:
https://help.github.com/articles/set-up-git#platform-mac
https://help.github.com/articles/generating-ssh-keys#platform-mac

Creating a new repo on Github
  - go to github, click ‘New Repository’ on right
  - give a name, choose public or private (requires paid account), click ‘Create’
  - In the ‘Quick Setup’ box, click ‘https’
  - If you don’t have a project to share, run ‘rails new foo’ to create one for this example.
  - $ cd foo
  - $ git init # only have to to once per project
  - $ git commit -am “initial commit” # we’ll explain this in a minute
  - $ git log # should show you five lines of output
  - $ git remote add origin https://github.com/pushcx/foo.git
  - $ git push -u origin master

How to add teammates:
  - Go to your repository on github (eg. http://github.com/pushcx/foo )
  - Click the ‘Admin’ tab
  - Click ‘Collaborators’ on the left
  - add their github usernames, one at a time

When added as a teammate:
  - Go to the repository on Github (eg. http://github.com/pushcx/foo )
  - Under the menu in the page, next to the button labeled HTTPS, copy the URL
  - $ git clone https://github.com/pushcx/foo.git

To save changes:
  - Edit your code as normal. For this example, edit the README to include your name.
  - $ git status # list of changed files
  - $ git diff # see all changes
  - $ git add --all # this will ‘stage’ all of your work, we’ll explain more options if we have time
  - $ git commit -m “add my name because Peter told me to” # say WHY you’re doing things

  - for multi-line messages, just type ‘git commit’. If you end up in vim, you can type :q<Enter> to quit.  To change your editor to something friendlier: git config --global core.editor “nano”

To share your work:
  - $ git push origin master
  - If you get a warning about ‘failed to push some refs’ and ‘Updates were rejected because the tip of your current branch is behind’, it means someone else has pushed up changes that you need to pull before you can push your code.

To pull others’changes:
  - $ git pull --rebase
  - This copies down all the changes your teammates have shared, and “rebases”, replays any changes you have made on top of this.
  - Every commit points to the commit that came before it, so this edits your work and you might get a scary “merge conflict”, when git is confused because you both edited the same code.

To deal with conflicts:
  - This happens because you and someone else edited the same code, and git can’t guess whose work to keep. It is your job to examine the conflict and sort it out. You will get a big scary message. This is OK, your work hasn’t been lost, and you can read it for a cheat sheet of how to fix things.
  - $ git status # to get a list of changes and see what needs to be done
  - Edit the files, look for <<<<<, which marks conflicts
  - When you’ve fixed all of them: $ git add -a # to stage your work
  - $ git rebase --continute # to finish the merge

To throw away your changes:
  - git reset --hard HEAD
  - This throws away all the work you’ve done and not commited. Dangerous!

How to set your username


More info: http://gitscm.com/documentation


-------


(extra time) Git tips and tricks
  1. aliases
  2. git help
  3. .gitignore
  4. git add -p
  5. git diff
  6. git revert
  7. git reset (how to unstage stuff)

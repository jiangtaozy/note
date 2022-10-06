- git log with date range or before after

      git log --after='2018-05-09'

- Git log for author

      git log --author='Your Name'

- .gitignore is not working

      # NOTE : First commit your current changes, or you will lose them.
      git rm -r --cached .
      git add .
      git commit -m "fixed untracked files"

- Remove untracked files from the working tree

      # show what will be deleted
      git clean -n
      # Clean Step - beware: this will delete files
      git clean -f
      # Remove untracked directories in addition to untracked files
      git clean -fd

- Undo a git add - remove files staged for a git commit

      git reset filename.txt

- Adding a remote

      git remote add origin https://github.com/user/repo.git
      git branch --set-upstream-to=origin/master master
      git push --set-upstream origin master

      // update remote
      git remote set-url origin git@github.com:ppreyer/first_app.git

- git diff on file in staging area

      git diff --staged

- Go to particular revision

      // This will detach your HEAD, that is, leave you with no branch checked out
      git checkout 0d1d7fc32

- Get back to most recent version

      git branch
      git checkout master

- Changing a remote's URL

      git remote set-url origin https://github.com/USERNAME/REPOSITORY.git

- Set git text editor

      git config --global core.editor "vim"

- Unstage a deleted file

      # this restores the file status in the index
      git reset -- <file>
      # then check out a copy from the index
      git checkout -- <file>

- Creating a new branch

      git branch develop

- Switching branches

      git checkout develop

- Listing branches

      git branch
      git branch -v
      git branch --merged
      git branch --no-merged

- Showing branch history

      git log --oneline --decorate --graph --all

- Push a branch to your remote repository

      git push origin develop

- Clone a remote branch and switch to it

      git checkout -b develop origin/develop

- git stash

      git stash
      git stash show
      git stash pop

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

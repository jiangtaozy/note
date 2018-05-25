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

- Undo a git add - remove files staged for a git commit

      git reset filename.txt

- git log with date range or before after

      git log --after='2018-05-09'

- Git log for author

      git log --author='Your Name'

- .gitignore is not working

      # NOTE : First commit your current changes, or you will lose them.
      git rm -r --cached .
      git add .
      git commit -m "fixed untracked files"

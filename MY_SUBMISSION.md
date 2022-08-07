# Git-exercise

## Scenario 1

Simply created a github repo with name git-exercise. With all the default README.md file and a main branch

## Scenario 2

Created a folder named "exercise" and inside added a "my_name.txt" file with content "My name is git exercise". Pushed the code to main branch commands used:

```
git add exercise
git commit -m "added my_name.txt file"
git push origin main
```

## Scenario 3

Create a new branch "exercise/conflict-resolution" and from main branch and edit the content to "My name used to be ..." commit and push the changes. Go to main branch edit the content to "My name has always been <Your Name>". commit and push the changes to respective branches and try merging..

Create a new branch and push the changes

```
git checkout -b exercise/conflict-resolution
git add .
git commit -m "updated my_name.txt file"
git push origin exercise/conflict-resolution
```

Move to main branch make changes and then push

```
git checkout main
git add .
git commit -m "updated my_name.txt file"
git push origin main
```

Now merging, since the code has conflicts there are many ways to solve this:

```
git pull origin exercise/conflict-resolution
*(changes will be aborted due to conflicts one has to manually merge, open vscode and accept the needing changes)
git add .
git commit -m "resolved merge conflicts"
git push origin main

```

## Scenario 4

Check the difference in branches using the diff command

```
git checkout -b exercise/diff-checker
*(make changes)
git add .
git commit -m "added new line in my_name file"

git diff main exercise/diff-checker
git diff exercise/diff-checker main
```

## Scenario 5

Push the previous branch and delete it locally and in server

```
git checkout exercise/diff-checker
git push origin exercise/diff-checker

git push -d origin exercise/diff-checker
git branch --delete exercise/diff-checker
```

## Scenario 6

Make changes in new branch and merge them using git stash

```
git checkout -b exercise/stash-scenario
*(make changes)
git stash push

git checkout main
git stash pop
*(merge the changes manually)
git add .
git commit -m "Files merged using git stash"
git push origin main
```

## Scenario 7

Create a hook

- Inside .git/hooks folder create a post-commit file and inside the file add the below code
- open terminal and type chmod +x post-commit
- Now the file is ready to execute
- Try committing any changes and you will see the message after successful commit

```
#!/usr/bin/env node

console.log("This is the first post-commit hook from git-exercise");

```

## Scenario 8

Push current files into a new repo

```
git remote add newRepo <repo_url>
git add .
git commit -m "Pushing files to new repo"
git push newRepo main
```

## Scenario 9

Create a tag

```
git tag 1.0.0
git push origin 1.0.0
```

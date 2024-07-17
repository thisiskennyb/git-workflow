# git-workflow

## Commiting a change
- Commiting often with a good descriptive message is important. Commits are snapshots of the code at a given time and can be referenced or reverted back to (this can get very messy if only working off of main)
- to view if their are changes ready to commit
```
git status
```
- If there are no changes to commit it will show `nothing to commit, working tree clean`

 Ex. Changes to commit output
 <br>
![image](https://github.com/user-attachments/assets/1db58480-c826-435d-8c40-f6c133c0f015)

1. Add the files to commit
```
git add .
```
or
```
git add name-of-file
```

2. Commit changes
```
git commit -m "write your message here"
```
- If wanting a longer message with a title and body you can open VIM
```
git commit
```

## Branching

create new branch
```
git checkout -b name-of-branch
```
- this creates a new branch and switches to that branch in the same command

move to new branch
```
git checkout name-of-branch
```


## Merging
**Before merging make sure the branch you are merging to is up-to-date
```
git pull origin main
```
1. Navigate to the branch that you want to merge your changes to
Ex. if merging changes to main
```
git checkout main
```
```
git merge name-of-branch
```

NOTE: This can also be accomplished on GitHub through a `pull request`

## Common Issues
What if I am trying to pull changes down from GitHub onto the main branch and it will not let me?
- This issue happens when the user forgets to make a new branch before begining work on a new feature or bug fix
- If changes have already been made on the main branch the user can make a new branch and switch to it which will carry those changes over
- To get the latest changes from github the user must stash their changes
```
git stash
```

## Branch Protection Rules
- Prevent users from making irrevocable changes to the protected branch (usually the main branch or production branch)
- When working in a team it is recommended to use branch protection rules
Advantages:
1. Enforces code quality standards
2. Prevents accidental changes
3. Audit trail and accountability
4. Conflict resolution

## Pull Requests
Click [here](https://www.zenduty.com/blog/pull-request-guide/) for more about pull requests
- This makes it easy to see what changes have been made and if there are any merge conflicts. Merge conflicts can be resolved in the GitHub GUI without the need for any additional software.
- Could set permissions to require approval from one or more users before allowing to merge
- A thread can be started for every PR allowing for good team communication regarding a feature or bug fix

## Ideal Workflow
- A branch protection is added to the main branch which will not allow anyone to push any changes directly to main
- A `pull request` is required before merging changes to the main branch
- Good team communication to prevent any merge conflicts (make sure you are not working in the same files)
Workflow:
1. Make sure main branch is up-to-date
```
git pull origin main
```
2. Create new branch and switch to it
- Try to be descriptive with the branch name
```
git checkout -b name-of-new-branch
```
3. Commit changes (the more often this is done, the more checkpoints you will have to revert back to if needed)
```
git add .
```
```
git commit -m "be descriptive in the message so you can determine what the code was like at this point in case you need to revert back"
```
3. Push branch up to GitHub
```
git push origin name-of-new-branch
```
4. Create a `Pull Request` in GitHub
- In the repository there is a `pull request` tab. Click on the tab and you should be prompted to create a new pull request
- Once the pull request is submitted it will alert the user if they are able to merge or if there are merge conflicts
- Merge conflicts can be solved right there in the GitHub GUI. It will show each conflict if there are multiple.
- You can review all changes that have been made in a pull request
- You can view all commits for a specific branch/PR

5. Merge pull request to main on GitHub
- This can be done by the person submitting the PR or it can be set up to require someone else to approve the PR before merging



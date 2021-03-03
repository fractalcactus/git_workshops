# Altering History

See Atlassian's excellent blog on [rewriting history]( https://www.atlassian.com/git/tutorials/rewriting-history).

Before doing these exercises, make sure that your Git editor is set to the editor of your choice. e.g:

`git config --global core.editor "vim" # set vim as the Git editor`

`git config --global core.editor "code --wait" set visual studio as the Git editor`

`git config --global core.editor "subl -n -w" # set sublime as the Git editor`

## Exercises

### 1. Alter the most recent commit's message
change the most recent commit message from "feat: run npm i" to "feat: run npm init"

### 2. Alter the most recent commit's files
- `git log` to see the logs. So far, so good. Note down the hash of the latest commit somewhere.
- inspect the changes introduced by the last commit with `git show` (`show` defaults to HEAD, but you can `show` any commit by passing the hash)
- omg I accidently added my `diary.txt` in that commit! panicpanicpanic

remove `diary.txt` from the previous commit, without altering the commit message.

### 3. Alter any commit message
change the second commit message from "feat: add fitignore" to "feat: add gitignore"

### 4. Merge commits together
Merge all the work in the last three commits into one commit, with the message "feat: add a styled homepage"



## Answers
Here are the solutions I came up with, but there's more than one way to shear a llama...

1. `git commit --amend -m "feat: run npm init"`
1. manually delete `diary.txt`, or run `rm diary.txt`

    ```
    git add diary.txt # The command 'add' can seem confusing here! This adds the CHANGE, i.e the removal of a file.
    git commit --amend --no-edit
    git show # note that the hash has changed, as the files in the commit changed
    ```
1. `git rebase -i HEAD~2`, follow the `reword` process:
    ```
    TODO: add screenshots
    ```

1. `git rebase -i HEAD~3`, follow the `squash` process:
    ```
    TODO: add screenshots
    ```
 # More About Git
 
 ### What is Origin ?
 > In Git, "origin" is a shorthand name for the remote repository that a project was originally cloned from. More precisely, it is used instead of that original repository's URL - and thereby makes referencing much easier.
 > 

    how to know the current origin? 

    -$git remote show origin 
    
    how to change the origin URL?
      1- cd /path/to/repository
      2- git remote -v
      3- git remote set-url <remote-name> <remote-url>
- How to merge between 2 branches?
> 
    1- git checkout <branch1> (you will switch to branch <branch1>)
    2- git merge <branch2> 
    (this will merge all changes from branch <branch2> into branch <branch1>)

- What would happen if you do git merge master current-branch?
> It will merge the code in the master to the current branch we checked-out to.



---

       
    
### Different uses of $ git reset

  ![](https://i.imgur.com/Qf9hAFQ.jpg)
  
  
* ***soft*** is discarding last commit, 
* ***mix*** is discarding last commit and add, 
* ***hard*** is discarding last commit,add and any changes you made in the code.



---

 ### How to use $ git stash and $ git stash pop

***$ git stash:***
>The command saves your local modifications away and reverts the working directory to match the HEAD commit.
      
    $git stash <stash-name>

***$ git stash pop:***
>Remove a single stashed state from the stash list and apply it on top of the current working tree state

    $git stash pop <stash-name>
    
    

---

### Other useful line commands

 ***$git diff:***

>Show changes between the working tree and the index or between two trees or changes between two files on disk.

    $git diff . // or a specific file name.
    
***$git log***
>Log shows the history of our commits

    $git log
    
***$git fetch***
>fetch is the command that tells your local git to retrieve all the data from the repository without transfering files (more used to check on recent changes).
When downloading content from a remote repo, git pull and git fetch commands are available to accomplish the task. You can consider git fetch the 'safe' version of the two commands. It will download the remote content but not update your local repo's working state, leaving your current work intact.

 - Fetch all of the branches from the repository.
>
    $git fetch <remote>
    
- Only fetch the specified branch.
>
    $git fetch <remote> <branch>
    
-Fetches all registered remotes and their branches
>
    $git fetch --all


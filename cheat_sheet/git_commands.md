### Git commands repo

* rename branch on github  
  ```
  git branch -m old_branch new_branch         # Rename branch locally    
  git push origin :old_branch                 # Delete the old branch    
  git push --set-upstream origin new_branch   # Push the new branch, set local branch to track the new remote
  ```

* [squashing commits with rebase](http://gitready.com/advanced/2009/02/10/squashing-commits-with-rebase.html)  
  `git rebase -i HEAD~4`


* 
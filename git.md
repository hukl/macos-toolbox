```
git log -p                                                            # print log with diff
git log --stat                                                        # print with insert and delete stats for each changed                  
                                                                      # file
git log --oneline                                                     # print 
git branch --merged master | grep -v 'master$' | xargs git branch -d  # remove local branches which have been merged to master
```

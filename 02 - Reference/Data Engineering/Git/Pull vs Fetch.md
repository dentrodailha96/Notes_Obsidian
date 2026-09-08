git pull = git fetch + git merge

### Why don't use Pull all the time? 

When two users made changes parallel changing in the same time the main branch. Leading to the situation of [[Merge or Rebase]].

![[Pasted image 20240806180155.png]]

- git pull --ff-only 
	-exam the changes before pulling
+ git pull --ff
	-Save the changes parallel the new changes 
- git pull --rebase 
	-Copy the new commits in the top of the new change 

![[Pasted image 20240806180640.png]]
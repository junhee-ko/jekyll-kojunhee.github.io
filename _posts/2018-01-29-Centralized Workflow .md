---
layout: post
title:  "Centralized Workflow"
date:   2018-01-29
categories: git
image : https://github.com/KoJunHee/kojunhee.github.io/raw/master/img/48.png
---

## concept 

- Clone the central repository

	```
	git clone ssh://user@host/path/to/repo.git
	```

- Make changes and commit


	```
	git status # View the state of the repo
	git add <some-file> # Stage a file
	git commit # Commit a file</some-file>
	```
	
- Push new commits to central repository

	```
	git push origin master
	```
	
- Managing conflicts


## example

- John works on his feature

	-  edit, stage, and commit.

- Mary works on her feature

	- edit, stage, and commit.

- John publishes his feature

	```
	git push origin master
	```
	
- Mary tries to publish her feature

	```
	git push origin master
	```
	
	- error
	- Mary needs to pull John’s updates into her repository

- Mary rebases on top of John’s commit(s)


	```
	git pull --rebase origin master
	```

- Mary resolves a merge conflict

	- 충돌이 발생하면 다음과 같은 에러

	```
	CONFLICT (content): Merge conflict in <some-file>
	```
	
	- Unmerged paths section에서 conflict file이 무엇인지 확인 가능
	
	```
	git status 
	```
	
	```
	# Unmerged paths:
	# (use "git reset HEAD <some-file>..." to unstage)
	# (use "git add/rm <some-file>..." as appropriate to mark resolution)
	#
	# both modified: <some-file>
	```
	
	- 파일 수정 후

	```
	git add <some-file>
	git rebase --continue
	git rebase --abort
	git push origin master
	```
	
	
		

# prvpubtesting
remote = **private** repo on gitlab, upstream = **public** repo on github

the private repo is invite only; development can be shared there already to a select group;   
and when paid for, all is pushed upstream to the **public** repo on github

## steps
1. create new repo on github, as the **public** repo, here https://github.com/drandreaskrueger/prvpubtesting
1. gitlab import github https://gitlab.com/import/github/status (with token https://github.com/settings/tokens and repo scope)
1. gitlab project visibility **private** on https://gitlab.com/andreaskrueger/prvpubtesting/edit settings ... general ... permissions ... private ... save changes
1. clone from gitlab (with ssh key) `git clone git@gitlab.com:andreaskrueger/prvpubtesting.git`
1. `cd prvpubtesting/`
1. inspect the settings *before* the next step: `cat .git/config`
1. `git remote add upstream git@github.com:drandreaskrueger/prvpubtesting.git` to set github as **upstream**
1. inspect settings once more: `cat .git/config`
1. `git pull upstream master` to sync github down to gitlab
1. from now on, all development happens first in gitlab only
1. i.e. local edits, e.g. `nano README.md`
1. set author: `git config user.name "Andreas Krueger"; git config user.email "<email-address>"`
1. first commit `git add README.md; git commit -m "from now on all happens local and in gitlab only"`
1. push (ONLY) to gitlab: `git push` or `git push origin master`

only when I (got paid, and) want to reveal the new code to everyone, I push to the public repo:

`git push upstream master`


---

for reference, the full `cat .git/config`

```
[core]
	repositoryformatversion = 0
	filemode = true
	bare = false
	logallrefupdates = true
[remote "origin"]
	url = git@gitlab.com:andreaskrueger/prvpubtesting.git
	fetch = +refs/heads/*:refs/remotes/origin/*
[branch "master"]
	remote = origin
	merge = refs/heads/master
[remote "upstream"]
	url = git@github.com:drandreaskrueger/prvpubtesting.git
	fetch = +refs/heads/*:refs/remotes/upstream/*
[user]
	name = Andreas Krueger
	email = <email-address>
```

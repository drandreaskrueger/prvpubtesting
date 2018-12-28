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
1. ...

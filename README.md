# prvpubtesting
remote = private repo on gitlab, upstream = public repo on github

## steps
1. create new repo on github, public
1. gitlab import github https://gitlab.com/import/github/status (with token https://github.com/settings/tokens and repo scope)
1. gitlab project visibility **private** on https://gitlab.com/andreaskrueger/prvpubtesting/edit settings ... general ... permissions ... private ... save changes
1. clone from gitlab (with ssh key) git clone git@gitlab.com:andreaskrueger/prvpubtesting.git
1. ...

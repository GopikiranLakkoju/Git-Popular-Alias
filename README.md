[global]
[pull]
	rebase = true
# Git alias Commands
[alias]	
  g = "git"

  # clone
  cl = 'clone'

  # add new git project to remote
  ar = "remote add origin"

  # status / diff 
  s = "status -sb"
  ss = 'status --short'
  d = 'diff'
  dw = 'diff --word-diff'
  ds = 'diff --staged'
  dws = 'diff --word-diff --staged';
  dv = 'diff -w "$@" | vim -R -'

  # add / rm / mv
  a = "add"
  aa = "add -A"
  ap = 'add --patch'
  ai = 'add --interactive'
  au = 'add --update'
  rm = 'rm'
  mv = 'mv'

  # branch
  b = "branch"  
  ba = "branch -a"
  br = "branch -r"
  bt = 'branch --track'
  bm = 'branch --move'
  bdel = 'branch --delete --force'

  # commit
  c = "commit --verbose -m"
  ca = "commit --verbose -am"  
  c-amd = "commit --verbose --amend -m"

  # current branch
  cb = "symbolic-ref --short HEAD"

  # checkout
  co = "checkout"
  cob = 'checkout -b'
  ct = 'checkout --track'

  # switch
  sw = "switch"

  # pull / push
  p = "pull --rebase"
  ps = "push origin HEAD"
  psu = "push -u origin"

  # fetch / rebase
  f = "fetch --all --prune --verbose"
  r = "rebase"

  # all alias
  al = "config --get-regexp ^alias."

  # logs
  l = "log --pretty=oneline --graph --decorate --all"
  l2 = "log --stat -2"
  l4 = "log --stat -4"
  br = "branch --format='%(HEAD) %(color:yellow)%(refname:short)%(color:reset) - %(contents:subject) %(color:green)(%(committerdate:relative)) [%(authorname)]' --sort=-committerdate"
  
  # stash
  sl = "stash list"
  ss = "stash push"
  sp = "stash pop"
  sa = "stash apply"
  
  # reset
  hr = "reset --hard HEAD~"
  sr = "reset --soft HEAD~"
  mr = "reset --mixed HEAD~"
  
  # delete
  dr = "push origin --delete"
  dl = "branch -D"
  
  # config edit
  ce = "config --global --edit"

  # bisect
  bs = 'bisect'
  bsb = 'bisect bad'
  bsg = 'bisect good'
  bsr = 'bisect reset'
  bss = 'bisect start' 

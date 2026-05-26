[global]
[pull]
	rebase = true
# Git alias Commands
[alias]	
  # ===== Core =====
  # al: list configured aliases | use case: discover available shortcuts quickly.
  al = "!git config -l | grep alias | cut -c 7-"
  # ce: edit global git config | use case: quickly modify aliases and user settings.
  ce = "config --global --edit"
  # g: run git from inside git aliases | use case: chain git subcommands in shell aliases.
  g = "git"

  # ===== Repository Setup =====
  # ar: add origin remote | use case: set origin on a newly initialized local repo.
  ar = "remote add origin"
  # cl: clone repository | use case: quickly clone a remote repo.
  cl = 'clone'

  # ===== Working Tree And Staging =====
  # a: stage files | use case: add specific files to index.
  a = "add"
  # aa: stage all changes | use case: include new, modified, and deleted files.
  aa = "add -A"
  # ai: interactive add | use case: guided staging workflow.
  ai = 'add --interactive'
  # ap: patch mode add | use case: stage selected hunks.
  ap = 'add --patch'
  # au: stage tracked-file updates | use case: skip untracked files while staging.
  au = 'add --update'
  # d: show unstaged diff | use case: inspect working tree changes.
  d = 'diff'
  # ds: staged diff | use case: review what will be committed.
  ds = 'diff --staged'
  # dv: open whitespace-ignored diff in vim readonly | use case: deep visual review in terminal.
  dv = 'diff -w "$@" | vim -R -'
  # dw: word-level diff | use case: review text-heavy edits.
  dw = 'diff --word-diff'
  # dws: staged word-level diff | use case: review staged text edits.
  dws = 'diff --word-diff --staged';
  # mv: move or rename files | use case: preserve rename history in git.
  mv = 'mv'
  # rm: remove tracked files | use case: delete files from working tree and index.
  rm = 'rm'
  # s: short status with branch info | use case: frequent working tree check.
  s = "status -sb"
  # ss: compact status output | use case: script-friendly or quick review of file states.
  ss = 'status --short'
  # unstage: unstage selected files | use case: remove files from index without discarding edits.
  unstage = "reset HEAD --"

  # ===== Commits =====
  # c: commit with message and verbose diff | use case: quick commit with inline message.
  c = "commit --verbose -m"
  # c-amd: amend last commit with new message | use case: fix previous commit message/content.
  c-amd = "commit --verbose --amend -m"
  # ca: commit all tracked changes with message | use case: skip separate add for tracked files.
  ca = "commit --verbose -am"
  # cane: amend without changing message | use case: include missed changes in last commit.
  cane = "commit --amend --no-edit"

  # ===== Branching And Switching =====
  # b: branch operations | use case: create/list/manage branches.
  b = "branch"
  # ba: list all branches | use case: view local and remote branches together.
  ba = "branch -a"
  # bdel: force delete local branch | use case: remove local branch without merge checks.
  bdel = 'branch --delete --force'
  # bm: rename/move branch | use case: rename current or target branch.
  bm = 'branch --move'
  # br: list remote branches | use case: inspect origin branch list.
  br = "branch -r"
  # brv: verbose sorted branch view | use case: find recently active branches quickly.
  brv = "branch --format='%(HEAD) %(color:yellow)%(refname:short)%(color:reset) - %(contents:subject) %(color:green)(%(committerdate:relative)) [%(authorname)]' --sort=-committerdate"
  # bt: set tracking branch | use case: connect local branch to upstream.
  bt = 'branch --track'
  # cb: print current branch name | use case: scripts or prompt helpers.
  cb = "symbolic-ref --short HEAD"
  # co: checkout branch/path | use case: switch branches or restore paths.
  co = "checkout"
  # cob: create and checkout branch | use case: start a feature branch quickly.
  cob = 'checkout -b'
  # ct: checkout and track remote | use case: create local branch tracking upstream branch.
  ct = 'checkout --track'
  # sw: switch branches | use case: modern branch switching command.
  sw = "switch"

  # ===== Sync And Publish =====
  # f: fetch all remotes with prune and verbose | use case: refresh remote tracking branches.
  f = "fetch --all --prune --verbose"
  # p: pull with rebase | use case: keep linear history when updating local branch.
  p = "pull --rebase"
  # pf: pull fast-forward only | use case: safe update that refuses merge/rebase.
  pf = "pull --ff-only"
  # ps: push current HEAD to origin | use case: publish current branch without typing branch name.
  ps = "push origin HEAD"
  # psu: push and set upstream | use case: first push of a new local branch.
  psu = "push -u origin"
  # pushf: force push with lease | use case: safer force push after rebase/amend.
  pushf = "push --force-with-lease"
  # r: rebase current branch | use case: replay local commits onto new base.
  r = "rebase"

  # ===== History And Inspection =====
  # l: decorated custom log line | use case: readable commit history with date and author.
  l = "log --pretty=format:"%C(yellow)%h\\ %ad%Cred%d\\ %Creset%s%Cblue\\ [%cn]" --decorate --date=short"
  # l2: last 2 commits with stats | use case: quick recent change summary.
  l2 = "log --stat -2"
  # l4: last 4 commits with stats | use case: broader recent change summary.
  l4 = "log --stat -4"
  # last: show latest commit | use case: quick check of most recent commit details.
  last = "log -1 HEAD"
  # lg: graph log across all branches | use case: visualize branching and merges.
  lg = "log --graph --oneline --decorate --all"

  # ===== Reflog Recovery =====
  # rla: search all reflogs by term | use case: locate deleted branch events by branch name or keyword.
  rla = "!f(){ git reflog --all -n 500 --grep-reflog=\"$1\"; }; f"
  # rlb: branch-action focused reflog | use case: find checkouts/resets/rebases around branch loss.
  rlb = "reflog -n 200 --grep-reflog=branch|checkout|reset|rebase"
  # rlf: clean recent HEAD reflog view | use case: quickly inspect recoverable HEAD moves.
  rlf = "reflog -n 60 --pretty=%C(yellow)%h %Cgreen%gd %Creset%gs"

  # ===== Stash =====
  # sa: apply latest stash | use case: restore stash while keeping it saved.
  sa = "stash apply"
  # sl: list stashes | use case: review saved work snapshots.
  sl = "stash list"
  # sp: pop latest stash | use case: restore and drop most recent stash.
  sp = "stash pop"
  # stp: push stash | use case: temporarily save uncommitted changes.
  stp = "stash push"

  # ===== Reset And Undo =====
  # hr: hard reset one commit back | use case: discard last commit and local changes.
  hr = "reset --hard HEAD~"
  # mr: mixed reset one commit back | use case: undo commit and unstage changes.
  mr = "reset --mixed HEAD~"
  # sr: soft reset one commit back | use case: undo commit but keep changes staged.
  sr = "reset --soft HEAD~"

  # ===== Branch Cleanup =====
  # dl: force delete local branch | use case: remove local branch immediately.
  dl = "branch -D"
  # dr: delete remote branch | use case: remove obsolete branch from origin.
  dr = "push origin --delete"
  # rage: show remote refs sorted by date | use case: spot stale remote branches by age.
  rage = "for-each-ref --sort=committerdate --format='%(committerdate:short) %(refname:short)' refs/remotes/origin"
  # rmerged: list remote branches merged into origin/main | use case: identify cleanup candidates.
  rmerged = "!git fetch origin --prune && git branch -r --merged origin/main | sed 's#^ *##' | grep -Ev '^origin/(HEAD|main|master)$'"
  # rmergedd: delete merged remote branches from rmerged output | use case: bulk remote branch cleanup.
  rmergedd = "!f(){ git rmerged | sed 's#^origin/##' | xargs -r -n 1 git push origin --delete; }; f"

  # ===== Bisect =====
  # bs: start bisect workflow | use case: find commit that introduced a bug.
  bs = 'bisect'
  # bsb: mark current commit as bad | use case: bisect step classification.
  bsb = 'bisect bad'
  # bsg: mark current commit as good | use case: bisect step classification.
  bsg = 'bisect good'
  # bsr: reset/exit bisect | use case: end bisect and return to original branch state.
  bsr = 'bisect reset'
  # bss: start bisect session | use case: initialize bisect range.
  bss = 'bisect start'

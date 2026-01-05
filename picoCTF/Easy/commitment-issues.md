# Commitment Issues
#### debug info: [u:953389 e: p: c:411 i:295972]

## Description
I accidentally wrote the flag down. Good thing I deleted it!

# Approach
Upon unziping the folder, we see this block of text:
```
inflating: drop-in/.git/description  
  inflating: drop-in/.git/hooks/applypatch-msg.sample  
  inflating: drop-in/.git/hooks/commit-msg.sample  
  inflating: drop-in/.git/hooks/fsmonitor-watchman.sample  
  inflating: drop-in/.git/hooks/post-update.sample  
  inflating: drop-in/.git/hooks/pre-applypatch.sample  
  inflating: drop-in/.git/hooks/pre-commit.sample  
  inflating: drop-in/.git/hooks/pre-merge-commit.sample  
  inflating: drop-in/.git/hooks/pre-push.sample  
  inflating: drop-in/.git/hooks/pre-rebase.sample  
  inflating: drop-in/.git/hooks/pre-receive.sample  
  inflating: drop-in/.git/hooks/prepare-commit-msg.sample  
  inflating: drop-in/.git/hooks/update.sample  
  inflating: drop-in/.git/info/exclude  
 extracting: drop-in/.git/refs/heads/master  
 extracting: drop-in/.git/HEAD       
  inflating: drop-in/.git/config     
 extracting: drop-in/.git/objects/d2/63841da2567e3e869d2b90e8e3bdd8838555b5  
 extracting: drop-in/.git/objects/c0/cc0495794727db1682daa105367f28112796af  
 extracting: drop-in/.git/objects/e7/20dc26a1a55405fbdf4d338d465335c439fb3e  
 extracting: drop-in/.git/objects/d5/52d1ecd2d83fa2e65b6724d1ff73b45a7d59b7  
 extracting: drop-in/.git/objects/0c/1ab266b7a3a1cd099bb509f82b7a2d03aecd03  
 extracting: drop-in/.git/objects/a6/dca68e4310585eac3b5c9caf0f75967dfe972c  
  inflating: drop-in/.git/index      
 extracting: drop-in/.git/COMMIT_EDITMSG  
  inflating: drop-in/.git/logs/HEAD  
  inflating: drop-in/.git/logs/refs/heads/master  
 extracting: drop-in/message.txt
```
A key piece of information to notice is how this seems to be a git repository. Upon viewing the directory we can see all the files and `cat message.txt`:
```
TOP SECRET
```
Entering `.git`, we see the following files:
```
.  ..  COMMIT_EDITMSG  HEAD  branches  config  description  hooks  index  info  logs  objects  refs
```
Viewing `COMMIT_EDITMSG` reveals "remove sensitive info" - suggesting that an earlier version of the repo contains the sensitive information (flag).<br>
Running `git log` shows:
```
commit a6dca68e4310585eac3b5c9caf0f75967dfe972c (HEAD -> master)
Author: picoCTF <ops@picoctf.com>
Date:   Sat Mar 9 21:10:06 2024 +0000

    remove sensitive info

commit e720dc26a1a55405fbdf4d338d465335c439fb3e
Author: picoCTF <ops@picoctf.com>
Date:   Sat Mar 9 21:10:06 2024 +0000

    create flag
```
As we can see, the first commit will most likely contain the flag as per the description. Hence, we can copy the commit ID and run `git checkout e720dc26a1a55405fbdf4d338d465335c439fb3e` to go back the the repo as of that commit. 
```
Note: switching to 'e720dc26a1a55405fbdf4d338d465335c439fb3e'.

You are in 'detached HEAD' state. You can look around, make experimental
changes and commit them, and you can discard any commits you make in this
state without impacting any branches by switching back to a branch.

If you want to create a new branch to retain commits you create, you may
do so (now or later) by using -c with the switch command. Example:

  git switch -c <new-branch-name>

Or undo this operation with:

  git switch -

Turn off this advice by setting config variable advice.detachedHead to false

HEAD is now at e720dc2 create flag
```
Knowing we are in that commit, running `cat message.txt` now reveals:
```
picoCTF{s@n1t1z3_7246792d}
```
# start a new GIT repository from the COMMAND LINE

I created a new folder and a new README.md file and ran GIT STATUS:

$ git status
fatal: not a git repository (or any of the parent directories): .git

## Initialize a new GIT REPOSITORY

$ git init
Initialized empty Git repository in C:/Users/kinnp/Desktop/learn-git/demo-repo2/.git/

## I ran GIT STATUS to see what I had at this point:

$ git status
On branch master

No commits yet

Untracked files:
  (use "git add <file>..." to include in what will be committed)
        readme.md

nothing added to commit but untracked files present (use "git add" to track)

## Then I Ran GIT ADD 

$ git add readme.md

## and then GIT STATUS:
git
kinnp@chucks-dev-pc MINGW64 ~/Desktop/learn-git/demo-repo2 (master)
$ git status
On branch master

No commits yet

Changes to be committed:
  (use "git rm --cached <file>..." to unstage)
        new file:   readme.md

## Then GIT COMMIT:

$ git commit -m "New repository from COMMAND LINE"
[master (root-commit) 8bfa55e] New repository from COMMAND LINE
 1 file changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 readme.md

## Try to push to ORIGIN MASTER:

$ git push origin master
error: src refspec main does not match any
error: failed to push some refs to 'origin'

** Since I did not CLONE this from an existing respository,GITHUB does not know this respository exists

## We need to let LINK this LOCAL repositotry to the GitHub REMOTE repository.

## 1. GOTO GITHUB and create an EMPTY REPOSITORY:

## 2. Under the "Quick setup — if you’ve done this kind of thing before" section Copy the SSH link:

git@github.com:kinnpiano1970/demo-repo2.git

## 3. Use GIT REMOTE ADD ORIGIN "<SSH LINK HERE>" 

$ git remote add origin git@github.com:kinnpiano1970/demo-repo2.git

## 4. Use git remote -v to check if successful

$ git remote -v
origin  git@github.com:kinnpiano1970/demo-repo2.git (fetch)
origin  git@github.com:kinnpiano1970/demo-repo2.git (push) 

**This shows any REMOTE REPOSITORIES I've connected to this repo.

## 5. Used git push origin master:

$ git push origin master
The authenticity of host 'github.com (140.82.112.3)' can't be established.
RSA key fingerprint is SHA256:nThbg6kXUpJWGl7E1IGOCspRomTxdCARLviKw6E5SY8.
Are you sure you want to continue connecting (yes/no/[fingerprint])? yes  
Warning: Permanently added 'github.com,140.82.112.3' (RSA) to the list of known hosts.
Enumerating objects: 3, done.      
Counting objects: 100% (3/3), done.
Writing objects: 100% (3/3), 251 bytes | 5.00 KiB/s, done.
Total 3 (delta 0), reused 0 (delta 0), pack-reused 0      
To github.com:kinnpiano1970/demo-repo2.git
 * [new branch]      master -> master

 NOTE** The new repo is in MASTER branch. First repo-demo (I created on GITHUB website) is in branch MAIN (DOnt know why)

 NOTE** The SSH warning issue is new!!

**NOTE add the "-u" switch. This sets the  "UPSTREAM" so in future I dont have to type "ORIGIN MASTER" just "GIT PUSH"

$ git push -u origin master
Warning: Permanently added the RSA host key for IP address '140.82.113.4' to the list of known hosts.
Enumerating objects: 5, done.
Counting objects: 100% (5/5), done.
Delta compression using up to 4 threads
Compressing objects: 100% (2/2), done.
Writing objects: 100% (3/3), 1.57 KiB | 322.00 KiB/s, done.
Total 3 (delta 0), reused 0 (delta 0), pack-reused 0
To github.com:kinnpiano1970/demo-repo2.git
   8bfa55e..e190376  master -> master
Branch 'master' set up to track remote branch 'master' from 'origin'.

# <span style="color:red">WORKING WITH GIT BRANCHES AND FORKS</span>

## Type "git branch" to see what branch Im on:

$ git branch
* master

## It will have a "*" beside it

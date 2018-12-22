# GIT
- For source control management
- as a version control system
- to keep track of changes

source ~/.bash_profile

## Version Control History
* Source Code Control System (SCCS) - 1972
    - keep screenshot of save
* Revision Control System (RCS) - 1982
    - Keep all current changes
* Concurrent Version System (CVS) - 1986
    - Multiple user to work at the same time
* Apache Subversion (SVN) - 2000
    - taking a snapshot of whole directory 
    - able to track time changes of the directory
* BitKeeper SCM - 2000
    - distributed version control
    - close source
* Git is born - 2005
    - created by Linus Trovalds
    - distributed version control
    - open source and free software
    - faster than other SMCs
    - getter safeguards againts data corruption
* Github launch 2008 - host Git responsitories


## Distributed version control
* 

http://git-scm.com

## Git download
http://git-scm.com

```
which git => check where git is install
git --version => version show
```

### Configuration Git
* System
    - /etc/gitconfig
    Program Files\Git\etc\gitconfig
    `git config --system`
* User
    - ~/.gitconfig
    `git config --global`
    eg:
    `git config --global user.name "Sherine Foo"`
    to check list `git config --list`
    to call `git config user.name`
* Project
    - my_project/.git/config
    `git config`
* Three-tree architecture Git incorporates a respository => tree, owrking and staging index tree

## Codes
`cd ~` => Back to your user directory 
`ls -la`=> list all files
`cat .gitconfig` => cat shows what inside the file
`clear` => clear screen
`cd ref`

`mv ~/git-completion.bash ~/.git-completion.bash`
`nano .bash_profile`

`git help log`
`git help <command>`
`man git-log`

```
git init
pwd
ls
ls -la => check all the store git information
ls -la .git
```
remove .git to remove git
only changes in git file is `config` file, don't touch anytihng else

checkout log files
`git log -n 1` first commit 
`git log --until=2012-06-14`
`git log --since=2012-06-14`
`git log --author=sherine`

`git add <file>` => add to stagging index
`git commit` => add to respository

checksum => Git generate when each change set
data integrity => fundamental
Git sue SHA-1 hash => saved changes name where GIT store
HEAD => pointer to "tip" of current branch. (last commit)

`git diff` -diff of the working directory
`git diff --staged` // old verson --cached => only in stageing dic
`git mv second_file.txt secondary_file.txt`
`git diff --color-words contact.html`
`git dif contact.html`
`git commit -am "message"` => action for add . and commit. but add everything into one changes

`git checkout -- index.html` => "--" to stay on the branch and not swtiching branch. Here to change current work station to what the respository file was. 
`git reset HEAD resources.html` -> to unstage the the last stage process HEAD(last staging)
`git commit --amend -m "rearrange items"` amend changes to last commit specific commits by identify message name 
`git commit --amend -m "rearrange items an outdoor trip"` amend message on last commit
`git checkout 0ca44063d831a0 -- resources.html` change the resource.html file to this shas# commit and change in staging area
`git diff --staged` it shows the diff on staging area. \
`git revert a22217f66eb15fd49f54ce2 ` -simple change from A to B and B to A and add commit for you 

`git reset --` manage the move of HEAD pointer where to point
        - soft => does not change staging index or working directory
        - mixed => default, changes staging index to match repository; does not change working directory. unstage it. 
        - hard => change dtaging index and working directory to match repository
    `git reset --mixed a6f88064b7019ba98c82f2f` => reset to sp

`cat .git/HEAD` where does git point at
`cat .git/refs/heads/master` show you the SHA-1 that is pointing

`git clean -n` => tells you waht they can remove
`git clean -f` => remove anything that is not in repo


project/.gitignore
`nano .gitignore` => create gitignore file

Keet track of the empty file in git, crete .gitkeep file in the empty file. `touch keep/.gitkeep`

## Navigating Commit Tree
* parent commit
    -  HEAD^, acf808df^, master^ (^above parent)
    - HEAD~1, HEAD~ (~how many generation up = 1 is one)
* grandparenet commit
    - HEAD^^, acf808df^^, master^^ (^above parent)
    - HEAD~2
* greatgrandparenet commit
    - HEAD^^^, acf808df^^^, master^^^ (^above parent)
    - HEAD~3

`git help ls-tree`
`git ls-tree HEAD`
`git ls-tree master`
`git ls-tree master^_assets/`

blob => file
tree => folder

`git log --oneline` show only one line
`git log -3` => last 3 commits
`git log --since=2.weeks --until=3.day `
author, 
`git log --grep="temp"` search any commit with temp message
`git log 290843..983748 --online`
`git log s8vhudf.. index.html` show what's changes in this while with this commit
`git log -p` patch option, diff of saving

`git log --format=oneline` full SHAS
`git log --graph` show branch or 
`git log --oneline --graph --all --decorate`
`git show 434f754` - show what was changes 

`git diff 2907d12603a34` returns all the difference between directory in that point of time and current directory
`git diff 2907d12603a34 tour.html` returns all the difference between directory in that point of time and current directory
`git diff 150657..HEAD` comparison with commits and HEAD
`git diff --stat --summary c4b913e..HEAD` 
`git diff -b c4b913e..HEAD` ignore changes of 1-5 space changes
`git diff -w c4b913e..HEAD` ignore ALL space changes
`git merge --no-ff branch` fast forward merge wtihout keeping 
`git merge --ff-only branch` do only when ff option available (ff=fastforward) 
`git merge branch_name` merge branch_name to current branch
`git stash save "change mission page title"` save with message
`git stash list` show stash list
`git stash show stash@{0}` show the edits
`git stash show -p stash@{0}` show detail on difference 
`git stash pop stash@{0}` - pop out on our working directory and remove the stash. Pop will always pul the first one "0"
`git stash apply stash@{0}`- pull it from stash to working directory but still keep copy
`git stash drop stash@{0}` - remove stash
`git stash clear` - clear all stash

origin/master => master branch on our local  

`git remote` show you all remote it has
`git remote -v` show all for fetch and push
`git remote rm origin` remove the remote origin 
`git push -u origin master` -u track the branch
```
 * [new branch]      master -> master
    Branch 'master' set up to track remote branch 'master' from 'origin'. => -u does
```

`git branch -r` = remote branch 
`git branch -a` = all branch

`git fetch` fetch all changes to store in `origin/master`. Do that every morning before start work
`git pull` = `git fetch` + `git merge`

# ALWAYS `git fetch` latest changes, `git merge` than `git push`
Delete remote branch
OLD WAY
`git push origin :<branch_name>` delete remote branch (: is to delete remote branch)

NEW WAY
`git push origin --delete <branch_name>` easier to remember

## Revert/Rollback previous commits
git reset to sha key waht you want / roll back with HEAD~n
Git force push


## A collaboration workflow
MY WORK FLOW
> git checout master
> git fetch
> git merge origin/master
> git checout -b feedback_form
> git add feedback.html
> git commit -m "add customer feedback form"
> git fetch 
> git push -u origin feedback_form


Lynda's work
> git checkout master
> git fetch
> git branch -r (see all brnach)
> git merge origin/master
> git checkout -b feedback_form origin/feedback_form
> git log
> git show o8s879r3
> git commit -am " add tour selector to feeback form"
> git fetch
> git push

My work after lynda checked mine and change
> git fetch
> git log -p feedback_form..origin/feedback_form
> git merge origin/feedback_form
> git checkout master
> git fetch
> git merge origin/master
> git merge feedback_form
> git push

git remote add nameofRepo URL

### Setup alias
`git config --global alias.st status`
co => checkout
ci => commit
br => branch
df => diff
dfs => diff --staged
logg => "log --graph --decorate --oneline --abbrev-commit --all"

### Remote access
`git remote -v`
`git remote set-url https://github.com/USERNAME/REPO.git`

`git log origin master` see what have been fetch from master
`git push -f` push my all or last commit to origin/master and remove all the log files and changes others has
`git reset --hard origin/master` remove all my commits back to origin/master. Git log will hold commits as per origin/master
`git reset --hard head~1` reset to specific commits. ~1 last 1 commit; ~2 last 2 commits

`git branch --merged` which one in our local branch have been merged into the current branch fully
`git branch --no-merged` which one in our local branch have not been merged into the current branch fully.Contains commits that not been merged
`git branch -r --merged` list of remote branches
`git branch --merged HEAD`
`git branch --merge july_release`
`git branch --merge <sha>` 

### Delete branch
`git branch -d key_features`
`git branch -D key_features`

`git push ori`
Delete Remote
`git push orign :key_features`
`git push -d origin delete_test`

### Prune stale brnaches
- pruning means delete stale remoting-tracking branches
- remoted-tracking branches, not remote branches

`git remote prune origin` complete remote the remote-tracing doata
`git remote prune origin --dry-run` 

`git fetch --prune`
`git fetch -p` 
git config --global fetch.prune true => setup to prune 

`git prune` prune all unreachable objects / Do not need to use
`git gc` part of garbage collection. Clean all temp tracking to bin

### Tagging
Tag allow marking points in history as important
most often used to mark release(v1.0, v1.1, v2.0)
`git tag issue135 92874da83` - add lightweight tag
`git tag -a v1.1 -m "bersion 1.0" 92874da83` add annotated tag (most common)
`git tag -am "Start" v0.0 92874da83` "start" = messsage ; v0.0 is the name

`git tag --list` / `git tag -l`
`git tag -l "v1*"` * = wildcard list
`git tag -ln` list and show the annotation 
`git show v1.1` 
`git diff v1.0..v1.1`

`git tag --delete v1.1`
`git tag -d v1.1`

`git push origin v1.1` push single tag
`git push origin --tags` push all tags
`git push origin :v1.1`
`git push -d origin v1.1`
`git tag temp`
`git branch temp_branch`
`git branch -b temp_branch`
`git checkout v0.0` Head changes to v0.0 sha status

## Interacgtive Staging
`git add --interactive`
`git add -i` show you all the stae and unstaged info

### Patch Mode
`hunk` an area where two files diffe
`git add --patch`
`git add -p`

`git stash -p`
`git reset -p`
`git checkout -p`
`git commit -p` 

### Share select changes

`git cherry-pick sha`
`git cherry-pick sha..sha`
can't cherry pick a merge commit

`echo "Hello" > temp.txt`
git diff frome-commit to-commit > output.diff
`git diff 3c6ec26 21a5bee > ~/Desktop/for_review.diff` use the previous commit to check the difference. this will create diff patch file
```
➜  demo_repo git:(master) git log --oneline
21a5bee (HEAD -> master) add shopping items
dfb1945 fix typo
3c6ec26 edit shopping list
a607338  add butter to shopping list
0a0b81f add party invite list
a503ee2 (tag: v0.1, origin/master, prune_test) add Paul and Avin in invite list
730113b (tag: tag_list) add remainding files
70ef8a7 (tag: v0.0, v0.0) first commit
```

apply the diff file
`git apply output.diff`

#### Create branch based on sha/commits
`git checkout -b tester a607338`

apply diff file
`git apply ~/Desktop/for_review.diff`

`git format-patch sha`
`git format-patch sha...sha`
`git format-patch master`start with head and work it way back to master
`git format-patch master -o feature` put patch files into a directory
`git format-patch sha.sha --stdout > feature.patch` output patches as a single file
`git format-patch 3c6ec26..21a5bee -o ~/Desktop/patches`

apply patches
`git am feature/00001-some-name.patch` am = apply mailbox
`git am feature/*.patch` apply all patches in a directory

### Rebasing
- Taking commits from a branch and reply them at the same end of another branch
- useful to integrate recent commits without merging
- Maintin a cleaner, more liner project history
- Ensures topic branch commits apply cleanly

`git rebase master` rebase curren branch to tip of master
`git rebase master new_feature` rebase new_feature to top of master

* Thou shalt not rebase a public branch
* only use in your own local branch that you're using personallly

### Rebase Conflicts
`git rebase --continue` rebase one at a time 
`git rebase --skip` skip some rebase item and skip to next one
`git rebase --abort`


### Rebase vs Merge
* MERGE to allow commits to stand out or to be clearly grouped
* Merge to bring large topic brnaches back into master
* REBASE to add minor commits in master to a topc branch
* REBASE to move commits from one branch to another
* MERGE anytime the topic branch is already public and being used by others

##TODO: not so clear 
`git rebase --onto newbase upstream branch` 
eg: `git rebase --onto master ecommerce new_feature`
history : new_feature is branch out from ecomerce; Action required to rebase new_feature from master instead of ecommerce


Undo rebase
`git reset --hard ORIG_HEAD` go back to original head before rebase
`git rebase --onto sha master new_feature` undo by rebasing to former merge-base sha

Interactive Rebasing
`git rebase -i master new_featureAdd`

Squash commits
pick
squash
fixup
squash
`git rebase -i HEAD~3` able to edit commit message and squash to commit

Pull rebase
`git pull --rebase` or `git pull --r`
`git pull --rebase=reserve`
`git pull --rebase=interactive`

## Revert back to older commits
`git reset --hard sha` remove all the changes
`git clean -f -d` - clean the untrack files mean remove the changes from work directory
`git status` to check
`git pull --rebase` or `git pull --r`
`git rebase master` to rebase with master changes
`git rebase master new_feature` to rebase new_feature on top of master

`git log --graph --all --decorate --oneline` check all status in graphical
`git merge-base master camping` show which sha it was merge with master

Git Blame
`git blame filename.txt` annotate file with commit detials
`git blame -w filname.txt` ignore white spacee

`git blame -L 100,150 filename.txt` annotate lines from 100-150
`git balme -L 100,+5 filename.txt`nnotate lines from 100-105
`git balme sha filename.txt ` annotate file at revision sha
`git balme sha -- filename.txt `
`git annotate filename.txt` similar to blam but diff output format


Git Bisect (to trouble shoot)
`git bisect start`
`git bisect bad <treeish>` - define which sha is bad
`git bisect good <treeish>` - define which sha is good
`git bisect reset` quit the bisect


### Reset commits on remote and push desired commits
`git log --oneline` 
`git reset HEAD~9` reset the HEAD to commits required (only HEAD change)
`git add <changes reqruied>` add all correct changes requried
`git status` check status if everything is good to push
`git push --force` force push it up to remote.


## Rebasing very old branch to updated Master branch
`git branch -m OF-15612-conHeader-fix` change existing branch name to ref name so old commits is still around
`git push origin OF-15612-conHeader-fix`
`git branch -u origin/OF-15612-conHeader-fix` push to remote
`git reset 2fd3953da442ba1be559f7f2d134a8480779dcfe` reset it back to 
`git log` check out if it has been reset
`git add <link_to_file>` add to only files required to change for clean branch and rebase
`git status` check status
`git commit -m "All header updates in one commit"` commit 
`git push --force` push to remote
` git add -A` add all 
`git stash` stash the rest of the changes that have not push
`git rebase hackathon-chat-fix` rebase on the correct master branch

`git reset Head~1`
`git add -A`
`git commit -c ORIG_HEAD`
`git log`
`git push --force`
`git checkout OF-15612-conHeader`


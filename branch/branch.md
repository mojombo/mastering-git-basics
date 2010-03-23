!SLIDE reverse

# Branching and Merging



!SLIDE gitcmd

# git branch

## Show all local branches

                   $ git branch



!SLIDE

# The default branch is named

# *master*



!SLIDE center

## Branches are just pointers to commits

![branch-master](branch-master.png)



!SLIDE center

## It's easiest to think of the working
## directory as corresponding to a branch

![wd-master](wd-master.png)



!SLIDE center

## As you commit, the branch moves with you

![follow1](follow1.png)



!SLIDE center

## As you commit, the branch moves with you

![follow2](follow2.png)



!SLIDE center

## As you commit, the branch moves with you

![follow3](follow3.png)



!SLIDE gitcmd

# git branch

## Create a new branch pointing at
## the current commit

              $ git branch uppercase



!SLIDE center

## A new branch has been created
## but the working dir has not changed

![uppercase](uppercase.png)



!SLIDE gitcmd

# git checkout

## Switch working dir to the given branch

             $ git checkout uppercase



!SLIDE center

## Working dir now corresponds to *uppercase*

![checkout-uppercase](checkout-uppercase.png)



!SLIDE

## Convert the string to uppercase
## on this branch and commit the change

    $ vim hello.sh
    $ git add -p
    $ git commit -m 'convert string to uppercase'



!SLIDE center

## Branches have now diverged!

![diverged](diverged.png)



!SLIDE

## Switch back to the *master* branch.
## Notice that working dir has been changed.

<pre>
$ cat hello.sh        <span class="comment"># uppercase version</span>
$ git checkout master
$ cat hello.sh        <span class="comment"># master version</span>
</pre>



!SLIDE center

## Working directory is now consistent
## with the *master* branch

![gc-master](gc-master.png)



!SLIDE gitcmd

# git diff R1 R2

## Diff between two arbitrary commits

            $ git diff master uppercase



!SLIDE center

## Show the work done between branches

![diff-r1-r2](diff-r1-r2.png)



!SLIDE gitcmd

# git merge

## Merge the given commit into the current branch

              $ git merge uppercase



!SLIDE center

## Both branches now point at the same commit

![merge-uppercase](merge-uppercase.png)




!SLIDE

## This kind of merge is known as a
## **fast-forward merge** because the
## merged branch was a direct descendent



!SLIDE gitcmd

# git branch -d

## Delete the given branch

             $ git branch -d uppercase



!SLIDE center

## Only the pointer has been deleted

![delete-uppercase](delete-uppercase.png)



!SLIDE center

## What if both branches have commits?

![fork](fork.png)



!SLIDE gitcmd

# git checkout -b

## Create a new branch and switch to it

            $ git checkout -b greeting



!SLIDE

## Modify the greetings; commit;
## and switch back to *master*

          $ vim hello.sh
          $ vim goodbye.sh
          $ git add -p
          $ git commit -m 'new greetings'
          $ git checkout master



!SLIDE

## Create a new file on *master*
## and attempt to add it

<pre>
  $ vim README
  $ git add -p       <span class="comment"># nothing to review!</span>
  $ git status       <span class="comment"># find out why</span>
</pre>



!SLIDE

# File tracking

## Git remembers what files have been added.
## New files must be explicitly added.



!SLIDE

## Add the contents of the new file

<pre>
    $ git add .   <span class="comment"># add everything!</span>
    $ git status  <span class="comment"># see that it worked</span>
</pre>



!SLIDE

## Oops, we forgot something...

<pre>
    $ vim README
    $ git status        <span class="comment"># make sure</span>
</pre>



!SLIDE center

## Two deltas have been introduced

![split-deltas](split-deltas.png)



!SLIDE

## Inspect the deltas, and continue

<pre>
     $ git diff --staged <span class="comment"># old change</span>
     $ git diff          <span class="comment"># new change</span>
     $ git add -p        <span class="comment"># add again</span>
     $ git commit -m "add a readme"
</pre>



!SLIDE

# Fixing mistakes



!SLIDE gitcmd

# git commit --amend

## Modify the content of the **last commit**

<pre>
           $ vim README
           $ git add -p
           $ git commit --amend
</pre>



!SLIDE center

## Recap of forked lineage

![double-diverge](double-diverge.png)



!SLIDE

## Merge *greeting* into *master*

               $ git merge greeting



!SLIDE center

## A new merge commit (C5) is created

![recursive](recursive.png)



!SLIDE gitcmd

# git log --graph

## Show the commit log with graph structure

<pre>
             $ git log --graph
</pre>



!SLIDE

## This kind of merge is known as
## a **recursive merge** and
## uses a 3-way merge strategy



!SLIDE center

## Three way (recursive) merge strategy

![3way](3way.png)



!SLIDE

# The power of Undo



!SLIDE

# First, a word about references

## A reference is a way to refer to a commit



!SLIDE bullets

# Examples:

* 5c673e53912d86eb771ee0ab0c678ecffa4b939c
* 5c673e5
* master
* HEAD
* HEAD^^



!SLIDE

## *HEAD* is a dynamic reference that
## follows your current checkout

![head-master](head-master.png)



!SLIDE

## *HEAD* is a dynamic reference that
## follows your current checkout

![head-greeting](head-greeting.png)



!SLIDE

## *HEAD* is a dynamic reference that
## follows your current checkout

![head-master](head-master.png)



!SLIDE center

## Ancestry reference modifiers

![backrefs](backrefs.png)




!SLIDE gitcmd

# git reset --hard

## Reset a branch and working dir

              $ git reset --hard head^



!SLIDE center

## *master* is now pointing to C4.
## C5 still exists, but is **dangling**.

![reset](reset.png)



!SLIDE gitcmd

# git reflog

## Show previous values of *HEAD*

                   $ git reflog



!SLIDE

# Let's induce a merge conflict



!SLIDE

## Modify a line that was also changed
## in the *greeting* branch

          $ vim hello.sh
          $ git add -p
          $ git commit -m 'howdy pardner'



!SLIDE

## Attempt to merge *greeting*

               $ git merge greeting




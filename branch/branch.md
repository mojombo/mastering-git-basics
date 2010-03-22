!SLIDE reverse

# Branching and Merging



!SLIDE gitcmd

# git branch

## Show all local branches

                   $ git branch



!SLIDE

# The default branch is named

<h1 style="color: red;">"master"</h1>



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

## Working dir now corresponds to "uppercase"

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

## Switch back to the "master" branch
## Notice that working dir has been changed

<pre>
$ cat hello.sh        <span class="comment"># uppercase version</span>
$ git checkout master
$ cat hello.sh        <span class="comment"># master version</span>
</pre>



!SLIDE center

## Working directory is now consistent
## with the master branch

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

<h2><span style="color: red;">fast-forward merge</span> because the</h2>

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

## Modify the greeting, commit,
## and switch back to master

          $ vim hello.sh
          $ git add -p
          $ git commit -m 'new greeting'
          $ git checkout master



!SLIDE

## Create a new file on the master
## branch and attempt to add it

<pre>
  $ vim goodbye.sh
  $ git add -p       <span class="comment"># nothing to review!</span>
  $ git status       <span class="comment"># find out why</span>
</pre>



!SLIDE

# Tracked Files

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
    $ vim goodbye.sh
    $ git status        <span class="comment"># make sure</span>
</pre>



!SLIDE center

## Two deltas have been introduced

![split-deltas](split-deltas.png)



!SLIDE

## Inspect the deltas, and continue

<pre>
    $ git diff          <span class="comment"># newest change</span>
    $ git diff --staged <span class="comment"># prior change</span>
    $ git add .         <span class="comment"># add again</span>
</pre>



!SLIDE

# Fixing mistakes



!SLIDE gitcmd

# git commit --amend

## Add content to an existing commit

<pre>
           $ git commit --amend
</pre>



!SLIDE center

## Recap of forked lineage

![double-diverge](double-diverge.png)



!SLIDE

## Merge "greeting" into "master"

               $ git merge greeting



!SLIDE center

## A new merge commit (C5) has been created

![recursive](recursive.png)



!SLIDE

## This kind of merge is known as

<h2>a <span style="color: red;">recursive merge</span> and</h2>

## uses a 3-way merge strategy



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
* refs/heads/master
* HEAD



!SLIDE

## "HEAD" is a special kind of reference

![head](head.png)



!SLIDE gitcmd

# git reset --hard

## Reset a branch and working dir

              $ git reset --hard head^



!SLIDE center

## master branch is now pointing to C4.
## C5 still exists, but is dangling.

![reset](reset.png)




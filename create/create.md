!SLIDE reverse

# Creating and Committing



!SLIDE

## Make a directory for your new project

               $ cd path/to/repos
               $ mkdir hello
               $ cd hello



!SLIDE center

## Working directory

![wd](wd.png)



!SLIDE gitcmd

# git init

<pre>
      $ ls -al    <span class="comment"># dir is empty</span>
      $ git init  <span class="comment"># initialize git repo</span>
      $ ls -al    <span class="comment"># new .git dir</span>
</pre>



!SLIDE center

## Behold the index!

![index](index.png)



!SLIDE

## Write some code

                  $ vim hello.sh
                  $ vim goodbye.sh



!SLIDE gitcmd

# git add

<pre>
$ git add hello.sh   <span class="comment"># add content to index</span>
$ git add goodbye.sh <span class="comment"># add content to index</span>
</pre>



!SLIDE center

## Index now contains working dir content

![add](add.png)



!SLIDE gitcmd

# git status

## Show the status of index and working dir

<pre>
               $ git status
</pre>



!SLIDE gitcmd

# git commit

<pre>
      $ git commit  <span class="comment"># make a commit</span>
</pre>



!SLIDE center

## A commit is a snapshot taken from the index

<h2 style="color: red">NOT THE WORKING DIRECTORY</h2>

![commit-c0](commit-c0.png)



!SLIDE gitcmd

# git log

## Print a log of commits

<pre>
                 $ git log
</pre>



!SLIDE center

# Recap

## The current state of the repo

![history1](history1.png)



!SLIDE

## Make some ambitious changes

<pre>
     $ vim hello.sh  <span class="comment"># modify the file</span>
</pre>



!SLIDE center

## Working dir now contains D0: a delta from C0

![dirty-c0](dirty-c0.png)



!SLIDE

## Review the changed files

<pre>
               $ git status
</pre>




!SLIDE gitcmd

# git diff

## Show diff between index and working dir

<pre>
                $ git diff
</pre>



!SLIDE center

## D0 = Diff(Index, WorkingDir)

![diff](diff.png)



!SLIDE gitcmd

# git add -p

## Interactively add changed hunks

<pre>
               $ git add -p
</pre>



!SLIDE center

## D0 is now in working dir AND index

![dirty-c0i](dirty-c0i.png)



!SLIDE

# **git diff** now shows nothing!

## Where did it go?



!SLIDE gitcmd

# git diff --staged

## Show diff between commit and index

<pre>
            $ git diff --staged
</pre>



!SLIDE center

## D0 = Diff(Commit, Index)

![diff-cached](diff-cached.png)



!SLIDE gitcmd

# git commit -m

## Create a commit with the given commit message

         $ git commit -m "more ambition!"



!SLIDE center

## Commit is rolled from index

![commit-c1](commit-c1.png)



!SLIDE center

# Recap

## Two commits, C0 and C1

![history2](history2.png)



!SLIDE center

## Ever commit has zero or
## more parent commits

![history2a](history2a.png)
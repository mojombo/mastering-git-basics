!SLIDE

# git clone

!SLIDE

![repo](github-repo.png)

!SLIDE commandline

    $ cd my/repos

!SLIDE commandline incremental

    $ git clone git://github.com/mojombo/mastering-git-basics.git
    Initialized empty Git repository in /Users/tom/my/repos/mastering-git-basics/.git/
    remote: Counting objects: 9, done.
    remote: Compressing objects: 100% (6/6), done.
    remote: Total 9 (delta 0), reused 0 (delta 0)
    Receiving objects: 100% (9/9), done.

!SLIDE commandline

    $ cd mastering-git-basics

!SLIDE commandline incremental

    $ ls -al
    total 8
    drwxr-xr-x    7 tom  staff   238 Mar 20 13:00 .
    drwxr-xr-x  115 tom  staff  3910 Mar 20 13:00 ..
    drwxr-xr-x   13 tom  staff   442 Mar 20 13:00 .git
    drwxr-xr-x    3 tom  staff   102 Mar 20 13:00 clone
    drwxr-xr-x    3 tom  staff   102 Mar 20 13:00 install
    -rw-r--r--    1 tom  staff    74 Mar 20 13:00 showoff.json
    drwxr-xr-x    3 tom  staff   102 Mar 20 13:00 title
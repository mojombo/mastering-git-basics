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

!SLIDE

# git log

!SLIDE commandline incremental

    $ git log
    commit 00b362e62ce01b8539be71b14fb909e74aaf36be
    Author: Tom Preston-Werner <tom@mojombo.com>
    Date:   Sat Mar 20 13:09:29 2010 -0700

        add clone section

    commit 158a6ed953af3104cb0b0fb3a0b4e13ede051eaf
    Author: Tom Preston-Werner <tom@mojombo.com>
    Date:   Sat Mar 20 12:48:58 2010 -0700

        first commit

!SLIDE

# git show

!SLIDE commandline incremental

    $ git show 00b362e62ce01b8539be71b14fb909e74aaf36be
    commit 00b362e62ce01b8539be71b14fb909e74aaf36be
    Author: Tom Preston-Werner <tom@mojombo.com>
    Date:   Sat Mar 20 13:09:29 2010 -0700

        add clone section

    diff --git a/clone/clone.md b/clone/clone.md
    index 7ac819c..c3b7c16 100644
    --- a/clone/clone.md
    +++ b/clone/clone.md
    @@ -1,4 +1,36 @@
     !SLIDE

    -# git clone git://github.com/mojombo/mastering-git-basics.git
    +# git clone

!SLIDE bullets incremental

# References

* 00b362e62ce01b8539be71b14fb909e74aaf36be
* 00b362e
* head
* head^
* head~10

!SLIDE

# git diff

!SLIDE commandline incremental

    $ git diff head^^...


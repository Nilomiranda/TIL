After running

```bash
git push --force
```

Which can be really harmfull to your git history (may lose some commits, not only yours but also from your collegues) there's a way to recover from that.

First run:

```bash
git reflog
```

You'll see something like this:

```bash
      

11b17fa HEAD@{1}: commit: chore: handling file and uploading to google cloud

0c1e9e5 HEAD@{2}: reset: moving to HEAD

0c1e9e5 HEAD@{3}: reset: moving to HEAD

0c1e9e5 HEAD@{4}: commit: chore: fixing server

5d27dd7 HEAD@{5}: reset: moving to HEAD

5d27dd7 HEAD@{6}: reset: moving to HEAD

5d27dd7 HEAD@{7}: reset: moving to HEAD

5d27dd7 HEAD@{8}: reset: moving to HEAD

5d27dd7 HEAD@{9}: commit: chore: basic page to handle file

942fdac HEAD@{10}: commit: chore: basic page changes to match content

c958a35 HEAD@{11}: commit (initial): init commit
```

A list of commits and a head number

Locate the state you want to go to, for instance `head 9` and do

```bash
git reset --hard HEAD@{9}
```

or use the hash `5d27dd7` and:

```bash
git reset --hard 5d27dd7
```

and now you can use push "safely" to correct your commits history

```bash
git push --force
```
# This is a Practice
## Assignment: Practice Git Branching and Merging

```console
Testing file.
:)
```
[Lab_1] Merge Conflicts


~/codecore/day_5$ mkdir lab_1
~/codecore/day_5$ cd lab_1
~/codecore/day_5/lab_1$ ls
~/codecore/day_5/lab_1$ cd ..
~/codecore/day_5$ ls
git-branching	git_test	lab_1
~/codecore/day_5$ cd lab_1
~/codecore/day_5/lab_1$ git init
Initialized empty Git repository in /Users/gloriading/codecore/day_5/lab_1/.git/
~/codecore/day_5/lab_1$ touch file_1.txt
~/codecore/day_5/lab_1$ git add .
~/codecore/day_5/lab_1$ git commit -m 'add file_1.txt'
[master (root-commit) b06ee34] add file_1.txt
 1 file changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 file_1.txt
~/codecore/day_5/lab_1$ git status
On branch master
nothing to commit, working tree clean
~/codecore/day_5/lab_1$ git checkout -b much-enhance-prose
Switched to a new branch 'much-enhance-prose'
~/codecore/day_5/lab_1$ git branch
  master
* much-enhance-prose
~/codecore/day_5/lab_1$ touch file_2.txt
~/codecore/day_5/lab_1$ git add .
~/codecore/day_5/lab_1$ git commit -m 'add file_2.txt'
[much-enhance-prose 824c6c1] add file_2.txt
 1 file changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 file_2.txt
~/codecore/day_5/lab_1$ git log
commit 824c6c13f0bebf06338f2be680ad2e8ed97c3639 (HEAD -> much-enhance-prose)
Author: Gloria Ding <gloria.hc.ding@gmail.com>
Date:   Fri Nov 10 13:54:15 2017 -0800

    add file_2.txt

commit b06ee3427f4820b7f7a4d05cf30d4b0903d6acb5 (master)
Author: Gloria Ding <gloria.hc.ding@gmail.com>
Date:   Fri Nov 10 13:52:22 2017 -0800

    add file_1.txt
~/codecore/day_5/lab_1$ git checkout master
Switched to branch 'master'
~/codecore/day_5/lab_1$ git checkout -b enhance-prose
Switched to a new branch 'enhance-prose'
~/codecore/day_5/lab_1$ touch file_3.txt
~/codecore/day_5/lab_1$ git add .
~/codecore/day_5/lab_1$ git commit -m 'add file_3.txt'
[enhance-prose 6d56c6a] add file_3.txt
 1 file changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 file_3.txt
~/codecore/day_5/lab_1$ git checkout master
Switched to branch 'master'
~/codecore/day_5/lab_1$ git checkout enhance-prose
Switched to branch 'enhance-prose'
~/codecore/day_5/lab_1$ git merge much-enhance-prose
Merge made by the 'recursive' strategy.
 file_2.txt | 0
 1 file changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 file_2.txt
~/codecore/day_5/lab_1$ git branch
* enhance-prose
  master
  much-enhance-prose
~/codecore/day_5/lab_1$ git log
commit 84819a96492ab2c8f5ad3ea5c0f38862b2328e26 (HEAD -> enhance-prose)
Merge: 6d56c6a 824c6c1
Author: Gloria Ding <gloria.hc.ding@gmail.com>
Date:   Fri Nov 10 13:58:55 2017 -0800

    Merge branch 'much-enhance-prose' into enhance-prose

commit 6d56c6a5d898a9dab4aa5f83b99edb22e37f3610
Author: Gloria Ding <gloria.hc.ding@gmail.com>
Date:   Fri Nov 10 13:55:35 2017 -0800

    add file_3.txt

commit 824c6c13f0bebf06338f2be680ad2e8ed97c3639 (much-enhance-prose)
Author: Gloria Ding <gloria.hc.ding@gmail.com>
Date:   Fri Nov 10 13:54:15 2017 -0800

    add file_2.txt

commit b06ee3427f4820b7f7a4d05cf30d4b0903d6acb5 (master)
Author: Gloria Ding <gloria.hc.ding@gmail.com>
Date:   Fri Nov 10 13:52:22 2017 -0800

    add file_1.txt
~/codecore/day_5/lab_1$ git checkout much-enhance-prose
Switched to branch 'much-enhance-prose'
~/codecore/day_5/lab_1$ git log
commit 824c6c13f0bebf06338f2be680ad2e8ed97c3639 (HEAD -> much-enhance-prose)
Author: Gloria Ding <gloria.hc.ding@gmail.com>
Date:   Fri Nov 10 13:54:15 2017 -0800

    add file_2.txt

commit b06ee3427f4820b7f7a4d05cf30d4b0903d6acb5 (master)
Author: Gloria Ding <gloria.hc.ding@gmail.com>
Date:   Fri Nov 10 13:52:22 2017 -0800

    add file_1.txt
~/codecore/day_5/lab_1$ git checkout master
Switched to branch 'master'
~/codecore/day_5/lab_1$ git checkout -b integration
Switched to a new branch 'integration'
~/codecore/day_5/lab_1$ touch file_4.txt
~/codecore/day_5/lab_1$ git add .
~/codecore/day_5/lab_1$ git commit -m 'add file_4.txt'
[integration 9ff70e6] add file_4.txt
 1 file changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 file_4.txt
~/codecore/day_5/lab_1$ git merge enhance-prose
Merge made by the 'recursive' strategy.
 file_2.txt | 0
 file_3.txt | 0
 2 files changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 file_2.txt
 create mode 100644 file_3.txt
~/codecore/day_5/lab_1$ git log
commit 292ea13143ecaa1baab5d41c830405c62d2e1229 (HEAD -> integration)
Merge: 9ff70e6 84819a9
Author: Gloria Ding <gloria.hc.ding@gmail.com>
Date:   Fri Nov 10 14:07:33 2017 -0800

    Merge branch 'enhance-prose' into integration

commit 9ff70e668e00869a18888b79ca06beb362d84d55
Author: Gloria Ding <gloria.hc.ding@gmail.com>
Date:   Fri Nov 10 14:07:05 2017 -0800
commit 292ea13143ecaa1baab5d41c830405c62d2e1229 (HEAD -> integration)
Merge: 9ff70e6 84819a9
Author: Gloria Ding <gloria.hc.ding@gmail.com>
Date:   Fri Nov 10 14:07:33 2017 -0800

    Merge branch 'enhance-prose' into integration

commit 9ff70e668e00869a18888b79ca06beb362d84d55
Author: Gloria Ding <gloria.hc.ding@gmail.com>
Date:   Fri Nov 10 14:07:05 2017 -0800
commit 292ea13143ecaa1baab5d41c830405c62d2e1229 (HEAD -> integration)
Merge: 9ff70e6 84819a9
Author: Gloria Ding <gloria.hc.ding@gmail.com>
Date:   Fri Nov 10 14:07:33 2017 -0800

    Merge branch 'enhance-prose' into integration

commit 9ff70e668e00869a18888b79ca06beb362d84d55
Author: Gloria Ding <gloria.hc.ding@gmail.com>
Date:   Fri Nov 10 14:07:05 2017 -0800
commit 292ea13143ecaa1baab5d41c830405c62d2e1229 (HEAD -> integration)
Merge: 9ff70e6 84819a9
Author: Gloria Ding <gloria.hc.ding@gmail.com>
Date:   Fri Nov 10 14:07:33 2017 -0800

    Merge branch 'enhance-prose' into integration

commit 9ff70e668e00869a18888b79ca06beb362d84d55
Author: Gloria Ding <gloria.hc.ding@gmail.com>
Date:   Fri Nov 10 14:07:05 2017 -0800

    add file_4.txt

commit 84819a96492ab2c8f5ad3ea5c0f38862b2328e26 (enhance-prose)
Merge: 6d56c6a 824c6c1
Author: Gloria Ding <gloria.hc.ding@gmail.com>
Date:   Fri Nov 10 13:58:55 2017 -0800

    Merge branch 'much-enhance-prose' into enhance-prose

commit 6d56c6a5d898a9dab4aa5f83b99edb22e37f3610
Author: Gloria Ding <gloria.hc.ding@gmail.com>
Date:   Fri Nov 10 13:55:35 2017 -0800

    add file_3.txt

commit 824c6c13f0bebf06338f2be680ad2e8ed97c3639 (much-enhance-prose)
~/codecore/day_5/lab_1$ git checkout master
Switched to branch 'master'
~/codecore/day_5/lab_1$ git checkout -b asset
Switched to a new branch 'asset'
~/codecore/day_5/lab_1$ touch file_5.txt
~/codecore/day_5/lab_1$ git add .
~/codecore/day_5/lab_1$ git commit -m 'add file_5.txt'
[asset d8b2ed8] add file_5.txt
 1 file changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 file_5.txt
~/codecore/day_5/lab_1$ git checkout integration
Switched to branch 'integration'
~/codecore/day_5/lab_1$ git merge asset
Merge made by the 'recursive' strategy.
 file_5.txt | 0
 1 file changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 file_5.txt
~/codecore/day_5/lab_1$ git log
commit eb24258c9f65e0b8b8c3d7e77d739f505dfa05f8 (HEAD -> integration)
Merge: 292ea13 d8b2ed8
Author: Gloria Ding <gloria.hc.ding@gmail.com>
Date:   Fri Nov 10 14:10:11 2017 -0800

    Merge branch 'asset' into integration

commit d8b2ed80459307c642a597478004642addf9e429 (asset)
Author: Gloria Ding <gloria.hc.ding@gmail.com>
Date:   Fri Nov 10 14:09:36 2017 -0800

    add file_5.txt

commit 292ea13143ecaa1baab5d41c830405c62d2e1229
Merge: 9ff70e6 84819a9
Author: Gloria Ding <gloria.hc.ding@gmail.com>
Date:   Fri Nov 10 14:07:33 2017 -0800

    Merge branch 'enhance-prose' into integration

commit 9ff70e668e00869a18888b79ca06beb362d84d55
Author: Gloria Ding <gloria.hc.ding@gmail.com>
Date:   Fri Nov 10 14:07:05 2017 -0800
commit eb24258c9f65e0b8b8c3d7e77d739f505dfa05f8 (HEAD -> integration)
Merge: 292ea13 d8b2ed8
Author: Gloria Ding <gloria.hc.ding@gmail.com>
Date:   Fri Nov 10 14:10:11 2017 -0800

    Merge branch 'asset' into integration

commit d8b2ed80459307c642a597478004642addf9e429 (asset)
Author: Gloria Ding <gloria.hc.ding@gmail.com>
Date:   Fri Nov 10 14:09:36 2017 -0800

    add file_5.txt

commit 292ea13143ecaa1baab5d41c830405c62d2e1229
Merge: 9ff70e6 84819a9
Author: Gloria Ding <gloria.hc.ding@gmail.com>
Date:   Fri Nov 10 14:07:33 2017 -0800

    Merge branch 'enhance-prose' into integration

commit 9ff70e668e00869a18888b79ca06beb362d84d55
Author: Gloria Ding <gloria.hc.ding@gmail.com>
Date:   Fri Nov 10 14:07:05 2017 -0800

    add file_4.txt

commit 84819a96492ab2c8f5ad3ea5c0f38862b2328e26 (enhance-prose)
~/codecore/day_5/lab_1$

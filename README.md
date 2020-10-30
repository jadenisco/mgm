# Mike's Web Site

This repository contains the content for Mike's web site. This site is 
hosted on [site](https://app.netlify.com/sites/mgm/overview) and created 
using the web site renderer Hugo. For more information on Hugo please visit 
[Hugo](https://gohugo.io).

## Build and push changes

### First, Add your SSH Key

We suggest that you use ssh to access GitHub. To do that, simply
upload your public ssh key to your GitHub account.

### Clone the repo

To create a working copy of your fork, do the following:

``` console
$ git clone ssh://git@github.com/<userid>/site
Cloning into 'site'...
remote: Enumerating objects: 3, done.
remote: Counting objects: 100% (3/3), done.
remote: Compressing objects: 100% (2/2), done.
remote: Total 3 (delta 0), reused 0 (delta 0), pack-reused 0
Receiving objects: 100% (3/3), done.
$ cd site
```

### Work Locally with Hugo

To make your changes locally initialize the git submodules.

``` console
$ git submodule update --init --recursive
Submodule 'themes/airspace-hugo' (https://github.com/themefisher/airspace-hugo.git) registered for path 'themes/airspace-hugo'
Cloning into '/Developer/hugo/site/themes/airspace-hugo'...
Submodule path 'themes/airspace-hugo': checked out '207d048784e04bfef6564615ff6addfb35480611'
$
```

Then run the Hugo server locally.

``` console
$ hugo server --disableFastRender

                   | EN
+------------------+----+
  Pages            | 42
  Paginator pages  |  0
  Non-page files   |  0
  Static files     | 96
  Processed images |  0
  Aliases          | 11
  Sitemaps         |  1
  Cleaned          |  0

Total in 40 ms
Watching for changes in /Developer/hugo/site/{assets,content,data,layouts,static,themes}
Watching for config changes in /Developer/hugo/site/config.toml
Serving pages from memory
Web Server is available at //localhost:1313/ (bind address 127.0.0.1)
Press Ctrl+C to stop
$
```

You can then make your changes and preview them by pointing your browser to the URL
displayed from the hugo server command. 

### Push changes to your fork on GitHub

Edit and commit work locally. You can create local topic branch(es) if
you like, but it's not necessary.

``` console
$ git add *
$ git commit -s -m "Add a descriptive comment here"
$
```

Upload patches to your fork on Github:

```console
$ git push origin <branch-name>  # often <branch-name> == master
```
### Appendix: how to commit code to a git repo (using a branch)

```console
$ git remote add upstream ssh://git@github.com/FDio/site
$ git remote -v
origin	ssh://git@github.com/<username>/site (fetch)
origin	ssh://git@github.com/<username>/site (push)
upstream	ssh://git@github.com/FDio/site (fetch)
upstream	ssh://git@github.com/FDio/site (push)
$ git fetch upstream
$ git merge upstream/master
$
$ # Make your changes
$
$ git checkout -b add-to-readme
$ git status
On branch add-to-readme
Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git checkout -- <file>..." to discard changes in working directory)

	modified:   README.md

no changes added to commit (use "git add" and/or "git commit -a")
$ git add *
$ git status
On branch add-to-readme
Changes to be committed:
  (use "git reset HEAD <file>..." to unstage)

	modified:   README.md

$ git commit -s -m "Add to the README"
[add-to-readme f81812c] Add to the README
 1 file changed, 76 insertions(+), 1 deletion(-)
$ git status
On branch add-to-readme
nothing to commit, working tree clean
$ git branch
* add-to-readme
  master
$ git push origin add-to-readme
Enumerating objects: 8, done.
Counting objects: 100% (8/8), done.
Delta compression using up to 8 threads
Compressing objects: 100% (4/4), done.
Writing objects: 100% (6/6), 1.68 KiB | 1.68 MiB/s, done.
Total 6 (delta 1), reused 0 (delta 0)
remote: Resolving deltas: 100% (1/1), done.
remote:
remote: Create a pull request for 'add-to-readme' on GitHub by visiting:
remote:      https://github.com/<userid>/site/pull/new/add-to-readme
remote:
To ssh://github.com/<userid>/site
 * [new branch]      add-to-readme -> add-to-readme
```


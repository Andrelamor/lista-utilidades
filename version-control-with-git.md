# [Version Control With Git](http://swcarpentry.github.io/git-novice/)

### [Setting up Git: user name, email, proxy and text editor](http://swcarpentry.github.io/git-novice/02-setup/index.html)

Use git config with the --global option to configure a user name, email address, editor, and other preferences once per machine.


### [Creating a repository](http://swcarpentry.github.io/git-novice/03-create/index.html)

$ **git init** = creates a repository that includes subdirectories and their files; does not need to make subdirectories a Git repository because the original repository will track all files, sub-directories, and subdirectory files under it


### [Tracking Changes](http://swcarpentry.github.io/git-novice/04-changes/index.html)

$ **cat <file.file type>** = prints the content of the file

$ **git status** = shows the status of a repository

$ **git add** = puts changes on Git stage area

$ **git commit -m** = includes the message of the commit

$ **git log** = lists all commits made to a repository in reverse chronological order

	$ **git log -N** = where N is the number of last commits wanted

$ **git diff** = shows the actual differences and the lines on which they occur. In particular, the + marker in the first column shows where we added a line.

	$ **git diff --staged** = shows the difference between the last committed change and what’s in the staging area

* Directories 

````
Git does not track directories on their own, only files within them
````
$ **git add <directory/file directory/file directory/file directory/file>** = adds all files in the directory at once 


### [Exploring history](http://swcarpentry.github.io/git-novice/05-history/index.html)


$ **git diff HEAD~1 <file>** = last commit in green
HEAD = the most recent commit

$ **git show HEAD~N <file>** = shows what changes were made at a N commit as well as the commit message

$ **git checkout HEAD <file>** = restores the last saved commit of a file

$ **git checkout (commit ID) <file>** = restores the  version indicated by the commit ID of a file

$ **git checkout master** = reattaches your HEAD

! [Git checkout working](git_checkout.png)

$ **git revert [erroneous commit ID]** = reverses changes committed to the local and project repositories


### [Ignoring things](http://swcarpentry.github.io/git-novice/06-ignore/index.html)

$ **touch <name.file type>** = generate a blank file to be used by programs which do not generate output files themselves, but require empty files already generated

**.gitignore** = helps us avoid accidentally adding to the repository files that we don’t want to track

**! (exception operator)** = The ! modifier will negate an entry from a previously defined ignore pattern; e.g. _!results/data/  # do not ignore results/data/ contents_         


### [Remotes in GitHub](http://swcarpentry.github.io/git-novice/07-github/index.html)

````
A local Git repository can be connected to one or more remote repositories.

Use the HTTPS protocol to connect to remote repositories until you have learned how to set up SSH.

````

$ **git push** = copies changes from a local repository to a remote repository.

$ **git pull** = copies changes from a remote repository to a local repository


### [Collaborating](http://swcarpentry.github.io/git-novice/08-collab/index.html)

$ **git clone** = opies a remote repository to create a local repository with a remote called origin automatically set up.

$ **git remote -v** = lists all the remotes that are configured (we already used this in the last episode)

	$ git remote add [name] [url] is used to add a new remote

	$ git remote remove [name] removes a remote. Note that it doesn’t affect the remote repository at all - it just removes the link to it from the local repo.

	$ git remote set-url [name] [newurl] changes the URL that is associated with the remote. This is useful if it has moved, e.g. to a different GitHub account, or from GitHub to a different hosting service. Or, if we made a typo when adding it!

	$ git remote rename [oldname] [newname] changes the local alias by which a remote is known - its name. For example, one could use this to change upstream to fred.

$ **git fetch origin master** =  gets the remote changes into the local repository, but without merging them. 

$ **git diff master origin/master** =  to see the changes output in the terminal.


### [Conflicts](http://swcarpentry.github.io/git-novice/09-conflict/index.html)

````

* Pull from upstream more frequently, especially before starting new work

* Use topic branches to segregate work, merging to master when complete

* Make smaller more atomic commits

* Where logically appropriate, break large files into smaller ones so that it is less likely that two authors will alter the same file simultaneously

````

### [Licensing](http://swcarpentry.github.io/git-novice/11-licensing/index.html)

````
* People who incorporate General Public License (GPL’d) software into their own software must make their software also open under the GPL license; most other open licenses do not require this.

* The Creative Commons family of licenses allow people to mix and match requirements and restrictions on attribution, creation of derivative works, further sharing, and commercialization.

* People who are not lawyers should not try to write licenses from scratch.
````

### [Using Git from RStudio](http://swcarpentry.github.io/git-novice/14-supplemental-rstudio/index.html)

Once we have saved our edited files, we can use RStudio to commit the changes by clicking on “Commit…” in the Git menu. This will open a dialogue where we can select which files to commit (by checking the appropriate boxes in the “Staged” column), and enter a commit message (in the upper right panel). The icons in the “Status” column indicate the current status of each file. Clicking on a file shows information about changes in the lower panel (using output of git diff). Once everything is the way we want it, we click “Commit”:

**Error fetching history: nome do diretório é inválido**



## Notes 01/27/2017 - Basic Web Concepts and GitHub

### Discussion
* What is data in your field?
* How does it look?
* Is the data different?
* Is the process of working with the data different?
* What about distribution? Web? Print? Sculpture? Other?
* Interactivity?

### Version control
* [What is version control?](https://git-scm.com/book/en/v2/Getting-Started-About-Version-Control)
* What is it good for?
* Why should we use it? In architecture, urbanism, humanities, other?
* It's about version control but it's also about collaborative work?

### Git & GitHub
* What is Git and what is GitHub:
  * **Git**: "Git is an open-source version control system. Think of it a series of snapshots of your code."
  * **GitHub**: "GitHub is a web-page on which you can publish and share your repositories."
  * Other differences: Git works locally, on your own computer. In contrast to other backup systems like Time Machine, Git allows you to see changes and track your process. Also, if you don't "push" (upload) your repository and the changes to GitHub, Git won't function as a backup.
* Further explanation in [stackoverflow](http://stackoverflow.com/questions/11816424/understanding-the-basics-of-git-and-github).
* Other version control systems (*note: I haven't tested any of these so I can't vouch for them*):
  * [Perforce Helix](https://www.perforce.com/helix)
  * [Plastic SCM](https://www.plasticscm.com/)
  * [Pixelapse](https://www.pixelapse.com/): Version control and collaboration for designers.
  * [Subversion](https://subversion.apache.org/)

### Examples
* Humanities:
  * [mini lazarillo - edición mínima del Lazarillo de Tormes](https://minilazarillo.github.io/) and the [GitHub repository](https://github.com/minilazarillo/minilazarillo.github.io)
* Architecture:
  * [Unity version control integration](https://docs.unity3d.com/Manual/Versioncontrolintegration.html)
* Other:
  * [Financial data and administration](https://github.com/SFPC/finance-and-administration)

### GitHub terms
* **Repository**: The location where all the files of a particular project are located. It can be local (on your own computer), remote (on the web, usually on github.io), or both, if you are synchronizing your local repository with a remote copy. On GitHub, each repository will have its own URL.
* **Commit**: Once you've made some changes to your files, and you are satisfied with those changes you can `add` and `commit` your files, which means that Git will make a snapshot of your files at that moment and you will be able to return to that snapshot at any point in time.
* **Push**: If you are working with a remote repository (this is usually the case), once you `commit` your files you will want to `push` them, which means synchronizing your changes with the repository located on the Github servers. That way, your collaborators will be able to see your changes and synchronize their files with yours.
* **Fetch**: The `fetch` command will take a look at the remote repository and see if any of it's files have changed. This command will not update the files on your local copy of the repository, it will only notify you that the files have changed.
* **Pull**: The `pull` command will actually update your files based on the changes to the remote repository. If they are any conflicts - for example, if you have made changes to some files that have also been changed by someone else - you will be notified of this when you do a pull command and you will be prompted to resolve the changes.
* **Branches**: Branches are copies of the main repository. Each branch has a name and you can experiment with them, change them, independent of the main repository. They work the same way as a repository and once you are satisfied with your changes you can merge your branch into the 'Master' branch of your repository. Projects often have 3 branches: the 'Master', which is the stable, tested, working branch; the testing branch, which has been developed, has new features but it's still under testing; and the experimental branch, which is under active development.
* **Fork a repository**: Forking a repository means making a copy of it on your own computer. It doesn't mean you can change the files in the original repository but it gives you a copy of those files you can use or play with. However, if you do make changes to the files and you want to synchronize your changes with the original repository you can submit a `pull request`.
* **Pull request**: When you've forked a repository and you've made changes to your files that you want merged with the original repository you can submit a `pull request`. This will notify the owner of the original repository and will allow them to accept or reject your changes. Many of the large projects on GitHub evolve with people forking a repository, improving something on their end and submitting `pull requests` to the main repository. It is a great way to open up collaboration to the rest of the world without loosing control.

### Installing Git on your computer
* Mac:
  * There are many ways to install Git on your Mac. And, chances are, you might already have Git installed. So firs, double check: go to your Terminal and type `git version`. If you do have it installed you should get something like this: `git version 2.8.4 (Apple Git-73)`.
  * If you don't have it installed you can follow one of the following paths:
    * You can download the [Git for Mac Installer](https://sourceforge.net/projects/git-osx-installer/files/). Follow the prompts and test the version at the end to verify Git was installed.
    * Homebrew (or other package manager tools): [Homebrew](http://brew.sh/) is a package manager tool. It helps you install software on your computer and keep it up to date. If you plan to keep on using your Terminal, Homebrew is one of the best tools to install software and keep it updated. Here we will use it to install Git:
      * To install Homebrew go to your terminal and type `/usr/bin/ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"`.
      * Once you finish the installation process type `brew install git` to install Git (the command `brew install <package>` will install the package on your computer using Homebrew. While you are here, you should also install Wget with `brew install wget`. This tool will help you download information from URLs.)
      * Once you've installed Git through Homebrew, test it by typing `git version`.
    * There are other ways of installing Git. If you are interested check out this [tutorial](https://www.atlassian.com/git/tutorials/install-git/mac-os-x).
  * Next you need to configure Git with your username and email address. Do the following:
    * `git config --global user.name "UserName"`
    * `git config --global user.email "email@email.com"`
  * Finally, you should allow Git to remember your username and password so you don't have to type them in every time you want to use it:
    * First, check to see if the `credential-oskeychain` is installed:
      * `git credential-osxkeychain`
      * You should get the following message: `usage: git credential-osxkeychain <get|store|erase>`. If you do, it means that it is installed (skip the installation). If you don't, your computer should prompt you to download it as part of the XCode Command Line Tools: `xcode-select: note: no developer tools were found at '/Applications/Xcode.app', requesting install. Choose an option in the dialog to download the command line developer tools.`
    * Once you've got it, tell Git to use the `oskeychain helper` by typing: `git config --global credential.helper osxkeychain`. Now, the next time you use Git, requiring the your username and password, you will grant access to the OSX keychain and your credentials will be stored.
    * For more info take a look at this [brief tutorial](https://help.github.com/articles/caching-your-github-password-in-git/) and if you ever need to change your credentials, [here](https://help.github.com/articles/updating-credentials-from-the-osx-keychain/) is how to do it.

### GitHub workflow:
* Creating a new repository:
  * There are multiple ways of doing this. Usually, you create a new folder on your computer where your project will live, then you create the corresponding repository on GitHub and finally you link both.
  * Here is the GitHub page on how to [create a new repository](https://help.github.com/articles/creating-a-new-repository/). You usually do this after you've created a folder in your computer.
  * Next, [here's the tutorial on how to link the two](https://help.github.com/articles/adding-an-existing-project-to-github-using-the-command-line/).
  * The basic commands for this one are:
    * 

### Other
* [Git Large File Storage](https://git-lfs.github.com/): necessary for working with files that are more than 100MB. Usually, when working with large video, audio or database files you will hit that limit. Use this system to track those files and use them in your repositories.
* GitHub actually supports (understands) 3D files like .stl and .obj and can visualize those files on its website and show changes.
* GitHub also supports .geoJson files and will visualize them on an interactive map on their website.
# Version Control with Git

Git and GitHub make it easy to track changes over time, implement features without sacrificing the integrity of the source, and have a well-established version control system with rollback capabilities.

[Git](https://en.wikipedia.org/wiki/Git_(software) refers to a popular source code management system. GitHub provides a GUI for reviewing the code managed by Git. We call this codebase a "repository".

I'll outline a typical workflow. You'll need to make sure that you have Git [installed](https://git-scm.com/download) on your machine. You also need to have created a GitHub account. Finally, this outline also assumes basic working knowledge of the command line.

---

### Forking a Repository

In your browser, navigate to [this repository](https://github.com/sensutec/temp) and click "Fork". You should then select your own GitHub username. 

![Git Fork](http://i.imgur.com/dmMdSPl.jpg)

You have now effectively made an exact copy the repository, but one that's hosted under your username. This is the copy you will make modifications to via the command line.

### Cloning (creating a copy of a repository on your local machine)

Open your terminal and navigate to the directory where you would like to install this demonstration project. I always just use the `projects` folder. It's not important what you call this folder, but it _is_ important that you place it somewhere within reach of your `$HOME` directory. (You can navigate to your home directory by typing `cd $HOME` or more simply, `cd ~`).

So in my case, I would type
```
cd ~/projects
```

Now you're going to "clone" a repository that exists online. Start by copying either the SSH or the HTTPS link for **your recently forked repository**. It should exist at `github.com/myusername/temp`.

![Git Clone](http://i.imgur.com/loE7kEp.jpg)

Once this URL is copied to your clipboard, type the following in the terminal
```
git clone https://github.com/myusername/temp
```

This will create a folder named after the repository, in our case `temp`. Navigate to the temp directory.
```
cd temp
```

### Setting Up Remotes

Right now, there are a total of _three_ different copies of the same repository.
- The original repository that we forked
- The forked copy that exists under our username
- The local version on your computer that you just cloned

The first two of these are our "remotes", because they exist remotely from our computer.

Let's check out our remotes
```
git remote
```

We should see only one response from this command, "origin"
![git remote, origin](http://i.imgur.com/Ob6ACly.png)

If we type `git remote -v` (short for `git remote --verbose`) we will see a more detailed view of our remote.

![git remote, verbose](http://i.imgur.com/HijYk8p.png)

We can safely ignore the nuances between these two listings of "origin", but we should take note of the fact that the URL corresponds to our "fork", the version that we cloned earlier.

---

Let's add the original version as one of our remotes
```
git remote add upstream https://github.com/sensutec/temp
```

Now type in `git remote -v`, you should now see both of our "remotes" listed: one titled "origin" (our fork) and one titled "upstream" (the original version). Moving forward, we will refer to these remotes by these assigned titles.

This concludes the portion of this outline geared towards project setup.

### Making Changes to a Repository

Open your newly created folder and its contents in your favorite text editor. Let's create a new file called `test.txt`. Add a few words to `test.txt` and make sure to save the file. (Note: the file should be located inside of the folder that you cloned, in our case `temp`).

Move back into your terminal and type the following
```
git status
```

You 


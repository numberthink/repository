# How to commit 

...to a Git repository.

If you're like me and lack commitment in your life, you've come to the right place.

I'm going to walk you down the aisle of how to make a Git repository and commit to it. 

But first, what even is Git?

From [Wikipedia](https://en.wikipedia.org/wiki/Git),

>Git is a distributed version control system that tracks changes in any set of computer files, usually used for coordinating work among programmers collaboratively developing source code during software development.

So Git is a system that tracks changes to any sets of computer files. 

But why would you need that?

## Why use Git?

Take the example of software engineering, what Git was originally made for when it was authored by software developer Linus Torvalds for the development of the Linux kernel.

In software engineering, version control is paramount: you need to be able to rollback to previous versions of software if something goes wrong after a change. By tracking and saving each of the committed changes to a set of files, Git allows you to easily revert to a previous version when disaster strikes.

But just because Git was created with software development in mind doesn't mean it's not useful for other types of projects. Anyone who has a file, or a set files, they want to track over time can benefit from Git. A single Microsoft Word file, or a collection of blog posts, or even just a folder of your photos, are all great things to track with Git.

Among the benefits of using Git is that every change made to a repository--what the set of files being tracked is called--is snapshotted and stored forever. It's like a time machine that can transport your project back to any point in time. 

Another upside is that when you update a project, even if you restart completely from scratch, you don't have to worry about re-naming it (and ending up with a file called "Final-Final-REALLY-FINAL6.doc"). You can start fresh as many times as you want knowing the older versions are forever accessible in the Git history if you need them. Every day can be day one.

Git also forces you into the making updates in the "unit" of commits. This is helpful for me--and anyone else who might have commitment issues--because you can see everyday exactly what was committed to a repository. You can commit to making regular commits and have instant feedback on how strong your commitment really is.

If nothing is committed, what are you even doing? Twiddling your thumbs? Well then follow me and let's make a commit(ment) together.

## Making a repository

To start using Git, you can make an account on [GitHub](https://github.com), a popular place to manage Git repositories. (However, GitHub is not the only application for storing and managing Git repositories.)

Once you have a Github account and are logged in, there should be a big green button that says "New" next to your repositories.

Click it.

You should be taken to a page where you enter the name of your repository and decide if it's public or private.

For the name, I'll pick something boring like "repository". I'll make it public since public commitments can be easier to hold yourself to.

There are also some options on this page for adding a "License", which tells others how they can use your code, and a "README", a summary of what the repository does. These are common, especially in software, but by no means necessary.

I'll skip those for now but you can always add those things later on.

Now click "Make repository" and voilá: the repository exists.

This should bring you to a screen that explains how to either initiate the repository from the command line or start by importing code. It also gives you an HTTP URL for the repository which we'll need later on.

If you want, you can just follow those instructions and skip the rest of this article.

Or you can keep reading and I'll walk you through each of the steps, starting with creating the repository locally.

## Making a local repository

The "local" repository is the repository on your computer (which will be synced with the one on Github). 

To start it, go to the root folder of the repository on your computer. "Root" just means the starting folder that everything else is inside of (I guess because trees, a common metaphor with Git, always start at the root). Inside the root folder you could have a README, License, configuration files, and then sub-folders where the actual code--or text or other content--lives.

If you already have a folder or file that you want to use as the starting point, you can start there. Otherwise you can just make an empty new project folder.e that you want to use as the starting point, you can start there. Otherwise you can just make an empty new project folder. 

This next part requires a command line interface. For that, I use the "Terminal" app on my Mac (which might be called something like "Command Prompt" on Windows).

When you open the command line interface, you have to first go to your root project folder. You can do that with the command `cd path/to/my/project`. The path to your project folder is how you get to it from your base folder, and usually looks something like `/Users/myname/Projects/myprojectname`. (If you can't figure out the path, on a Mac you can left click on the project folder and select "Get info" and that should tell you where the file is located.)

Once you've `cd`'d to the root folder, run the command `git init`. (You'll need Git installed on your computer for it to work, which you can do [here](https://git-scm.com/book/en/v2/Getting-Started-Installing-Git))

That initializes the repository. 

If you already have stuff in the repository you can run the command `git add .` which tells Git to start tracking all those files. 

## Commiting to a repository

Now it's time to make the first commit. You can do that with the command `git commit -m "[first commit message]"`.

What's a good first commit message? "init repo" works, but I like to keep things simple so I'll do: "[first commit message]".

Now you need a branch. Why? Because every change in Git happens on a branch. The branch holds all the changes made since it was first branched.

At the very least you need one branch, often called "main". But you can create as many other branches as you please. For example, in software development you might have a "dev" branch where your doing active development, and then, when it's ready for primetime, you "merge" it into the main branch. 

We just need a main branch for now which you can create and "check-out" twith this command: `git branch -M main`.

I now have a branch ("main") with my first commit on it. But that's only on my local computer. I still need to "push" it, which means uploading all the "local" changes to the "remote" repository, i.e. the repository on [Github.com](https://github.com). 

To do that, you have to first add the repository from Github as the "remote" origin for the one on your computer. 

The command to do that is `git remote add origin` along with the URL that GitHub gave you for the repo. So for me that command ends up being: `git remote add origin https://github.com/numberthink/repository.git`.

(For this part you will also need to authorize your Github account on your computer if you haven't already. You can do that with the [GitHub CLI](https://cli.github.com/manual/gh_auth_login) via the `gh auth login` command.)

Finally I need to push my local changes to the remote repository. I'll do that with the `git push` command. The other arguments to the "push" command are the remote repository to push to, which will be "origin", and the branch, "main". 

So the command to push ends up being: `git push -u origin main`.

And that's it! We created a repository, made a commit and pushed it to the remote repository on Github.

In the future, once you make changes to your local repository, you can push them with just these commands:
 - `git add .` or `git add [filepath]` - Tell git to track new/updated files
 - `git commit -m "[commit message]"` - Commit the changes
 - `git push` - Push the committed changes to the remote repository

Some other commands that are useful (I know I seem commanding but I'm working on it, I promise!):
 - `git checkout -b newbranchname` - Make and checkout a new branch (can remove "-b" if it already exists)
 - `git push --set-upstream origin newbranchname` - Push to that branch on the remote repository
 - `git merge branchname` - Merge that branch into the main branch

You can find more commands and resources [here](https://docs.github.com/en/get-started/using-git/about-git).

Remember: commitment is forever (unless you get a divorce...I mean delete the repository).
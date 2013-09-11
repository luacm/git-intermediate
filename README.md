# Intermediate Git
If you looked at [git-intro](http://github.com/luacm/git-intro), then you should have a basic understanding of how to create a repository, add files, commit changes, and go back to old commits.

## What more could there be?
Oh boy, tons! But in this section, we're going to talk about the following topics:

* Remote Repositories
  - Pulling
  - Pushing
  - Cloning
* Branching
* Merging

Cool! So get ready, this is where we get to do the fun stuff with git :)

# Remote Repositories
In git-intro, you worked entirely on a local repository, which means the repository was on your computer and nobody else's. However, you can imagine that this may not be the best idea. For one, if your computer breaks, then you lost all of your work. Second, we said that git was a tool that aided collaboration, and if the repository is only on your computer, how are others suppsed to get your work? 

That's where a remote repository comes in. Remote repositories are copies of your repository that are located on some other computer. You can then push commits to that repository or pull commits down from that repository. Git doesn't have any built-in thing that makes a remote repository special - it's literally just a copy that you can update when you feel like it. However, by convention, we often have one remote repository that we treat as the master copy. Collaborators will add their commits to it, and we can pull new commits down from it. 

There's two scenarios when starting work on a remote repository: 

1. Someone else already has a repository made, and you want to make a 'clone' of it so you can start working on it.
2. You have a local repository, and you want to put it on some remote server to act as a backup or to let other people work on it.

## Cloning a repository
When we make a copy of a repo in git, we call it 'cloning'. To clone, you simply type the command:

```git clone <url of repo>```

At that point, git will pull down all of the code and put it in a folder whose name matches that of the repository. As an example, let's clone this repository! Simply type:

```git clone https://github.com/luacm/git-intermediate.git ```

And ta-da! You now have a local copy of this repository.


Let's start with scenario #1!

# Branching
Imagine the following scenario: You're writing a paper for class, and you're about halfway done. That's when you realize that you think you need to adjust your thesis, but doing so would require re-writing a few paragraphs. You don't want to lose your current version, so you make a copy of your paper and work on the copy instead, so you have a backup if anything goes wrong. That's branching in a nutshell. It's the concept of working on a copy (called a 'branch') so you can change things without worrying about ruining your current version. It's one of the greatest features in git, and it's really simple to do.

## Let's make a branch!


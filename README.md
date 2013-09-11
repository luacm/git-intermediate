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

Let's start with scenario #1!

## Cloning a repository
When we make a copy of a repo in git, we call it 'cloning'. To clone, you simply type the command:

```git clone <url of repo>```

At that point, git will pull down all of the code and put it in a folder whose name matches that of the repository. As an example, let's clone this repository! Simply type:

```git clone https://github.com/luacm/git-intermediate.git ```

And ta-da! You now have a local copy of this repository.

## Adding a remote repository
If you're working on a project, I encourage you to use the above method, just because it makes things easier. You can make an empty git repository online (like on [Github](http://github.com/) or [Bitbucket](http://bitbucket.org)) and clone it to start istead of using ```git init```. It's also easy to add a remote to your existing repository, it's just a couple more steps. So, let's begin!

Assuming you have a local repo already, let's make a repository on Github. Just go to [the site](http://github.com), login, and click the 'Create a new repo' button that's next to your name in the top left (or just click [here](https://github.com/new)). From there, just enter the details about your repo like the name and such. I always initialize with a Readme if I don't have one yet in my local repository, just because every project on Github should have one. You don't have to add a license, but if you do, the MIT License is a good one that lets people dow whatever they want with your code as long as they give attribution.

Now that you have the repo created, look for the 'clone URL' located somewhere on the page. Right now it's in the bottom right, but it's changed location over time. It may default to the 'SSH clone URL', but we don't want that one. Click on the HTTPS button to see the 'HTTPS clone URL'. Copy that URL.

Now let's go to our local repository and type the following command:

```git remote add origin <the url you copied>```

You now have added a remote repository called 'origin'! By convention we call the primary remote repo 'origin' because that's normally where you originally get your code from. You can pull down the differences between your repos (for instance, if you added a Readme) by typing ```git pull origin master``` or just overwrite the existing remote repository with a copy of yours by typing ```git push -f origin master```. 

But we haven't really gone over those commands, have we? Let's do that now!

## Pulling and Pushing
We need a way to communicate with the remote repository and share commits. That's where ```pull``` and ```push``` come in.

### Pull
When you do a pull, you get all of the new commits from the remote repo you specify added to your local repository. And that's it! There isn't much to pulling code at all. As an example, to pull from your origin remote by doing the following:

```git pull origin master```

And then you'll get your code! Don't worry if you don't know what the 'master' part means. We'll be going over it very shortly.

### Push
Pushing is how you take the commits from your local repo and add them to your remote repo. To do that, all you have to do is type:

```git push origin master```

And it will add your commits to the remote repo. Simple, right? 

Now to explain what that 'master' word we've been writing means by looking at one of the most useful tools git provides you: branching.

# Branching
Imagine the following scenario: You're writing a paper for class, and you're about halfway done. That's when you realize that you think you need to adjust your thesis, but doing so would require re-writing a few paragraphs. You don't want to lose your current version, so you make a copy of your paper and work on the copy instead, so you have a backup if anything goes wrong. That's branching in a nutshell. It's the concept of working on a copy (called a 'branch') so you can change things without worrying about ruining your current version. It's one of the greatest features in git, and it's really simple to do.

## Let's make a branch!


* title: Unable to show a Git tree in terminal
* url: http://stackoverflow.com/questions/1064361/unable-to-show-a-git-tree-in-terminal
* date: Jun 30 '09 at 15:30

# Masi
Killswitchcollective.com's old article, 30 June 2009, has the following inputs and outputs

git co master
git merge [your_branch]
git push

```
upstream    A-B-C-D-E            A-B-C-D-E-F-G
                 \        ---->               \
                 your branch       C-D-E                        G
```

I am interested how you get the tree like-view of commits in your terminal without using Gitk or Gitx in OS/X.
How can you get the tree-like view of commits in terminal?

# VonC
Jakub Narębski mentions in the comments [[tig|http://jonas.nitro.dk/tig/manual.html]] (2006-2009), a ncurses-based text-mode interface for git. See their releases.
It has a --graph option back in 2007.

# Sebastian Patten

```
git log --oneline --decorate --all --graph
```

A visual tree with branch names included.

Use this to add it as an alias

```
git config --global alias.tree "log --oneline --decorate --all --graph"
```

You call it with

```
git tree
```

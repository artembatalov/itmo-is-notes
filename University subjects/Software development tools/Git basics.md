Git is a free and open source distributed version control system designed to handle everything from small to very large projects with speed and efficiency.
#### **🔹 Repository setup**
```
git init              # initialize a new repo
git clone <url>       # clone an existing repo
```

#### **🔹 Status & history**

```
git status            # show current state (changes, index)
git log               # show commit history
git diff              # show differences
```

Flags for git log:
-  --oneline - every commit is shown in one string (hash + message)
-  --graph - show graph 
-  --all - show all branches of repository
#### **🔹 Staging & committing**

```
git add <file>        # add a file to staging
git add .             # add all changes
git commit -m "msg"   # save changes as a commit
```

#### **🔹 Branching**

```
git branch            # list branches
git branch <name>     # create a new branch
git checkout <name>   # switch to branch
git switch <name>     # modern alternative to checkout
git merge <name>      # merge branch into current
git branch -d <name>  # delete branch
```

#### **🔹 Remote work**

```
git remote -v                  # list remotes
git push origin <branch>       # push changes
git pull origin <branch>       # pull + merge changes
git fetch origin               # download changes (no merge)
```

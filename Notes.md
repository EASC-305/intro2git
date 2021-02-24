## A Quick intro to `git`


Let's say we have a folder called `mini_project` that we want to use version
control within.

Lets Initialize our repository:
```bash
git init mini_project
```

> ```
> Initialized empty Git repository in .../mini_project/.git/
> ```

Lets navigate into our project repository
```bash
cd mini_project
```


Lets create a python script called `project.py` and open it the the text editor
[`atom`](https://atom.io/):
```bash
atom project.py
```

Let's add to our python script and have it do something. In this case I'd like it
print the date.

```python
#!/usr/bin/python

import datetime

currentDT = datetime.datetime.now()

print('The date is: {}'.format(currentDT.strftime("%Y-%m-%d")))
```

Awesome! Once we've saved this file let's see how this has affected our repo:
```bash
git status
```

> ```
> On branch master
>
> No commits yet
>
> Untracked files:
>   (use "git add <file>..." to include in what will be committed)
> 	project.py
>
> nothing added to commit but untracked files present (use "git add" to track)
> ```

Hmm! Now lets add our changed `project.py` to the repo so we can keep track of
changes.

```bash
git add project.py
```

Cool. Lets see whats going on:

```bash
git status
```

> ```
> On branch master
>
> No commits yet
>
> Changes to be committed:
>   (use "git rm --cached <file>..." to unstage)
> 	new file:   project.py
> ```

Great. Now lets commit so our changes are tracked/logged by `git`. We'll want to
add a commit message (`-m`)that describes what we did: s
```bash
git commit -m "My first commit. I've started the project.py file and begun by just printing the date. More to come\!"
```
>```
>[master (root-commit) eab4f98] My first commit. I've started the project.py file and begun by just printing the date. More to come\!
> 1 file changed, 7 insertions(+)
> create mode 100644 project.py
>```

Now lets see what our repo looks like:
```bash
git status
```
> ```
> On branch master
> nothing to commit, working tree clean
> ```

Awesome.
Let's write some more code.
We'll add this the end of our python file:

```python
print('The time is: {}'.format(currentDT.strftime("%I:%M:%S %p")))
```


Lets see how this has affected our repo:
```bash
git status
```
> ```
> On branch master
> Changes not staged for commit:
>   (use "git add <file>..." to update what will be committed)
>   (use "git restore <file>..." to discard changes in working directory)
> 	modified:   project.py
>
> no changes added to commit (use "git add" and/or "git commit -a")
> ```

Lets add our changes so they can be tracked:
```bash
git add project.py
```

Finally lets commit the changes and describe what we did:
```bash
git commit -m "I' ve added a line to print the date before the time. Progress...."
```

> ```
> [master dc57f13] I' ve added a line to print the date before the time. > Progress....
>  1 file changed, 1 insertion(+)
> ```

Let's see  the status of our repo:
```bash
git status
```
>  ```
>  On branch master
>  nothing to commit, working tree clean
>  ```

Lets compare versions of  the `project.py`:
```bash
git diff HEAD project.py
```
This won't output anything since the "working tree clean", basically no chnages
have been made since our last commit.


Instead lets compare to the version from the last commit (`HEAD~`) of the `project.py` file:
```bash
git diff HEAD~1 project.py
```

>```bash
> diff --git a/project.py b/project.py
index 322eb3c..42eadc0 100644
--- a/project.py
+++ b/project.py
@@ -5,3 +5,4 @@ import datetime
 currentDT = datetime.datetime.now()  
>
> print('The date is: {}'.format(currentDT.strftime("%Y-%m-%d")))  
> +print('The time is: {}'.format(currentDT.strftime("%I:%M:%S %p")))
>```

This is just the begging of what you can do with `git`! For more indepth tutorials
please see below

__Resources__: 

1. [Git & GitHub Tutorial for Scientists](https://gitbookdown.dallasdatascience.com/)

2. [Intro to git](https://github.com/ICESAT-2HackWeek/intro-git/blob/master/git-intro-concepts.ipynb) from the ICESAT-2 Hackweek tutorial.

3. [Git Guide](https://rogerdudler.github.io/git-guide/) by Roger Dudler.  

4. [`atom`](https://atom.io/) a great text editor with build in support for `git` and GitHub.

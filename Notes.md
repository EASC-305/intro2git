## A Quick intro to `git`

Lets Initialize our repository:
```bash
git init mini_project
```

Lets create a python script called `project.py` and open it the the text editor
`atom`:
```bash
atom project.py
```

Lets add to our python script and have it do something. In this case I'd like it
print the date.

```python
#!/usr/bin/python

import datetime

currentDT = datetime.datetime.now()

print('The date is: {}'.format(currentDT.strftime("%Y-%m-%d")))
```

Awesome! Lets see how this has affected our repo:
```bash
git status
```

Hmm! Now lets add our changed `project.py` to the repo so we can keep track of
changes.

```bash
git add project.py
```

Cool. Lets see whats going on:

```bash
git status
```

Great. Now lets commit so our changes are tracked/logged by `git`. We'll want to
add a commit message (`-m`)that describes what we did: s
```bash
git commit -m "My first commit. I've started the project.py file and begun by just printing the date. More to come\!"
```

Now lets see what our repo looks like:
```bash
git status
```

Awesome. Now it's time to work on this project more. Let's add some more code.
Lets add to the end of our python file:

```python
print('The time is: {}'.format(currentDT.strftime("%I:%M:%S %p")))
```


Awesome! Lets see how this has affected our repo:
```bash
git status
```

Lets add our changes so they can be tracked:
```bash
git add. project.py
```


Finally lets commit the changes and describe what we did:
```bash
bash commit -m "I' ve added a line to print the date before the time. Progress...."
```

Let's see  the status of our repo:
```bash
git status
```

Lets compare our `project.py` file to the previous version:
```bash
git diff HEAD project.py
```


```bash
git diff HEAD~ project.py
```

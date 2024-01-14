---
title: "Hacking GitHub: How to do 1000 contributions worth one year in a second."
datePublished: Sun Jan 14 2024 23:04:23 GMT+0000 (Coordinated Universal Time)
cuid: clre3sh8l000208ld5hyvfvbv
slug: hacking-github-how-to-do-1000-contributions-worth-one-year-in-a-second
tags: github, python, automation, script, gitcommands

---

## Warning!

The following code is only for educational purposes. I am not trying to promote using this method to fool recruiters.

## Context

Ever wanted to develop a GitHub profile stats that look something like this:

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1705237786496/b1e366da-7cd3-4126-96b4-e2578021bc5c.png align="center")

Well, let me tell you how to do it. There is a hard way to do this by contributing every day to multiple projects and growing as a developer.

Or simply we write a script that performs commits throughout the year for us and viola! we are set.🙂

The second method is easy, however, the recruiter is always able to see the commits we have made throughout the year and see the specifications of these commits. This method will surely not help you land a job but it is worth reading through to know how to perform this.

## How does it work

A commit done in GitHub is tracked by the timestamp attached to it. by default, this timestamp is the same as the current time. This is exactly how GitHub marks our changes on files by how many days ago this file was changed.

We will simply manipulate this timestamp to past time and push a commit. This will create a commit at our newly selected timestamp.

## Let's code!

To build something like this firstly we need a language that can make changes to a file. This is the file that we will commit to multiple times.

We will be using Python. We will write a Python script that makes multiple commits.

Firstly we will write some Python code to manipulate a file. We write the current DateTime using the DateTime library of Python.

```python
from datetime import datetime
def change_file_content(file_path):
    with open(file_path, "w") as file:
        file.write(str(datetime.now()))
```

Now we can use this function to open a new file and simply write the current timestamp in it. This file change is what will allow us to commit multiple times.

Now we need to commit our changes. To commit our changes Python has a library called [GitPython](https://pypi.org/project/GitPython/) which can be used to do these commits easily.

So now we write a function that commits only a specific file with given commit message.

```python
from datetime import datetime
from dateutil.relativedelta import relativedelta
import random
from git import Repo, Actor

from git import Repo, Actor

def commit_file(repo_path, file_path, commit_message, author_name, author_email):
    # Initialize the repository
    repo = Repo(repo_path)

    # Create an actor for the commit
    actor = Actor(author_name, author_email)

    # Add the file to the staging area
    repo.index.add([file_path])

    # Commit the changes
    repo.index.commit(commit_message, author=actor)
```

the above code is good enough to make one commit. But we need to do more than 200-300 commits that also with different commit messages and different timestamps. So we modify it as follows:

```python
def commit(repo, file_path, x, y):
   # Check for changes
    if repo.is_dirty():
        # Add specific file
        repo.git.add(file_path)
        commit_date = commit_position(x, y)
       
        # Define author with specific timestamp
        author = Actor("Osaf Ali", "kingsayed02@gmail.com")
        author_time = int(time.mktime(time.strptime(commit_date, '%Y-%m-%d %H:%M:%S')))
        author_tz = "+0100"  # timezone offset

        # Commit with specific timestamp
        repo.index.commit(f"Commited on: {commit_date}", author=author, author_date=f"{author_time} {author_tz}")
        print(f"Commited on: {commit_date}")
    else:
        print("No changes to commit")
```

Here we are defining an author who is making the commit, and author\_time which defines the exact time where we want to make the commit. we pass it our DateTime in string format.

Finally, we commit these changes and print a commit message so we know when the commit took place.

Notice, we are using a function commit\_position(x, y) to get the commit\_date. This is because every commit will have a different date that we need to add. To generate those dates we want to think of GitHub stats as X and Y axis.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1705241272581/f78fc636-12d2-42f5-bdc9-517785712206.png align="center")

The red line marks the x-axis and the blue line marks the y-axis. We simply get today's date, subtract one year from it, and add a day to start at the marked square.

From this point, we can simply move on the x-axis by multiplying the value of x by 7, and for the y-axis, we can simply add it to the current value. The code of this looks something like this:

```python
def commit_position(x: int, y: int):
    origin = datetime.now() - relativedelta(years=1) + relativedelta(days=1)
    origin = origin + relativedelta(days=y)
    origin = origin + relativedelta(days=x*7)
    return origin.strftime('%Y-%m-%d %H:%M:%S')
```

At this point, we can use the above functions according to our needs. I used these functions to mark all the cells on the graph.

Have a look at my repo [here](https://github.com/OsafAliSayed/GitHacker), and Thank you for reading. Leave a like and a comment if you liked it.
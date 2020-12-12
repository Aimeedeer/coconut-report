---
date: 2020-12-12
title: How to Pretend to Be A Hacker
categories: ["hacks"]
tags: ["life", "covid19", "mental"]
---

- title1: How to Pretend to Be A Hacker
- title2: So you want to (pretend to) be a hacker


Since the [RiB] contributing policies have changed last month,
that we do not accept contributions from other channels
except for GitHub.
Some non-hackers, either co-founders or marketers,
started to use GitHub for submitting PRs,
and RiB has recieved some not-awesome PRs.

This reminds me of my first time (about two years ago
as I can remember) uses GitHub, and I could only
use its website for editing.
At that time, I didn't know I need to fork the original repo
to my account, and edit it, then push my changes back to
the original repository (repo for the below).
I thought I could and I thought I did edit the original repo.
Not to mention how to write a decent commit message.
How naive.

This post is for non-developers like me who want to participate
in developers' conversations via GitHub.
After reading this post, you will be able to interacte with
GitHub by creating a repo and committing to it.
You will fork a repo, subbmit a PR and file an issue to
other one's repo. In this case, it will be an example repo
that I created for you to play around.

Don't panic. That's fine to submit a strange PR at the first
time as long as you are willing to make progress.
Let's rock!

[RiB]: https://rustinblockchain.org

## No Joke, We Only Do It in The Hacker's Way

The main and most obviouse differences between hackers
and non-hackers are how do they interate with their computers.
Non-hackers, which are most of computer users, always need
mouses to help clicking things on their screens,
while hackers even don't need a mouse.
Hackers can do almost everything with command lines.

### Command Lines Kickoff

Before we use command lines,
we need some clicks to open the terminal to allow us
using command lines in it.
The terminal is the entry for recieving
our input and showing us the output from our computers.

If you don't know how to open your terminal,
just Google it.
Google things befor asking others is the first step
to (pretend to) be a hacker.
You can also choose [DuckDuckGo](https://duckduckgo.com/)
as the alternative search engine.

What we need here is to go to your determind directory
and create a new folder for your project.

Type `ls`, and it will show you a list of files and folders
in the current directory.
`cd` + space + the folder you want to jump in, and
`cd ..` to jump back to higher level of current directory.
Try to play with these three commands.

Then we go to a folder, for example, documents, typing `cd documents`
and create a test project, for instance, `my-test-project`,
with the command `mkdir my-test-project`.
Typing `ls` and you will see you have a new folder in current
directory. Then type `cd my-test-project` to go inside.

There is a trick that you can type `cd my-t` and kick your TAB key,
it will be automatically fullfilled. Sometimes you need to type
more characters if there are similar filenames.

Note that we don't recommand naming a file or foler with space,
because it creates complexity for the system, that
your operating system, other programs' systems and scripts 
deal with filenames which containing with space in multiple ways.
See simple explainations here:
[Is space not allowed in a filename?](https://unix.stackexchange.com/questions/148043/is-space-not-allowed-in-a-filename).

The Network Working Group also mentioned it in [URL specifications](https://www.ietf.org/rfc/rfc1738.txt):
>  Characters can be unsafe for a number of reasons.  The space
   character is unsafe because significant spaces may disappear and
   insignificant spaces may be introduced when URLs are transcribed or
   typeset or subjected to the treatment of word-processing programs.
   The characters "<" and ">" are unsafe because they are used as the
   delimiters around URLs in free text; the quote mark (""") is used to
   delimit URLs in some systems.  The character "#" is unsafe and should
   always be encoded because it is used in World Wide Web and in other
   systems to delimit a URL from a fragment/anchor identifier that might
   follow it.  The character "%" is unsafe because it is used for
   encodings of other characters.  Other characters are unsafe because
   gateways and other transport agents are known to sometimes modify
   such characters. These characters are "{", "}", "|", "\", "^", "~",
   "[", "]", and "`".


### Git Matters, So Does GitHub

With the new-created folder, we can play around with our tests in it.
The next step is installing [Git],
a version controll system for your files (and [more]).
With Git, you will be able to actively manage your file changes.

#### Just Git It

In this step, I use MacOS as the example.
Follow the official [Download for macOS],
and then you probably need to install [homebrew] first,
which helps a lot with package managing in your operating system.

Do remember, always use command lines.
This is the first principle for being a hacker
(or pretend to be).
Copy this piece of code and paste it to your terminal
to install homebrew:

```
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install.sh)"
```

After succussefully intalling homebrew, you can
use `brew install <some-package-name>` for most of packages
that you need on MacOS.
For example, we use `brew install git` to install Git.

Once you have Git installed, we can play with it for a bit.
Ready?
Let's move forward, and make sure your are in the `my-test-project`
folder.

Type `git init`, which normally you can see from documentations
with a `$` sign.
It's the sign that indicates this line is the input commands.
By contrast, thoese lines without a `$` sign suggest that
they are outputs.
I remembered I even tried typing `$` in my terminal before :)

```
$ git init
```

This command just shows its meaning that to initialize a project
with Git system,
and the terminal will soon show you the output.

```
$ git init
Initialized empty Git repository in /<your directory>/my-test-project/.git/
```
After that you can simple use `git log` to see the version history.
Let's try:
```
$ git log
fatal: your current branch 'master' does not have any commits yet
```

As the terminal shows that the `'master'` is the default branch.
Branches are very useful for collaborating with others on the
same project and also keep the available code running well.
In our starting case, we just use the default config.

Let's add a file in this folder first.
In MacOS, we use `echo` + content + `>` + the file name to
create it.
```
$ echo This is the first doc file > firstone.doc
$ ls
firstone.doc
$ cat firstone.doc 
This is the first doc file
```
By the way, it's a good habit to check states often as to verify
our commands worked or not.
In this example, I use `ls` to check if the file has been created,
and `cat` for printing the content in that file.
You can use `git status` frequently to check your files' states.

Ok, now we have some updates in this folder, and let's
check with our Git to see what happend there:
```
$ git status
On branch master

No commits yet

Untracked files:
  (use "git add <file>..." to include in what will be committed)
	firstone.doc

nothing added to commit but untracked files present (use "git add" to track)
```
Do pay attention to the terminal messages,
and let's follow the reminds and 
add our new file to the Git track:
```
$ git add firstone.doc
$ git status
On branch master

No commits yet

Changes to be committed:
  (use "git rm --cached <file>..." to unstage)
	new file:   firstone.doc
```

You can use `git add` + <your file> one by one if you have more files.
You can also use `git add .` to add **all** the files under current folder.
Then we can commit, with a clear message to tag with this version,
which we use `-m"<your message>"` as the argument.
```
$ git commit -m"add my firstone file"
[master (root-commit) ea430c3] add my firstone file
 1 file changed, 1 insertion(+)
 create mode 100644 firstone.doc
```
Done!
Now our file is totally under the version control.
We made it!
```
$ git status
On branch master
nothing to commit, working tree clean
```

That's the whole thing for the first step with Git.
You can keep playing around with these commands and
to create as well as commit more stuff to Git.

More command lines for managing files or more about Git,
just Google it! You can always figure it out.


[Download for macOS]: https://git-scm.com/download/mac
[homebrew]: https://brew.sh/


Other links:
- https://github.com/git/git/blob/master/Documentation/gittutorial.txt
- https://github.com/git/git/blob/master/Documentation/giteveryday.txt
- About ssh key: https://git-scm.com/book/en/v2/GitHub-Account-Setup-and-Configuration
- Git book: https://git-scm.com/book/en/v2


#### Collaborate on GitHub


[GitHub] is one of the most popular repo hosting services.
The other two are [GitLab] and [Bitbucket].
In this post, we use GitHub as our service.

GitHub provides great tutorials to help newcomers getting started.
_TODO_ links.



```
git push
```


For non-developers, there are not a must-have skill
to use GitHub, but if you ever want to build or are working
on building an open source developer community,
you would think about using GitHub to communicate with
your developers.

There are two main advantages by learning GitHub:
- Understand developers' mindset and the open source culture
- Win respect from developers by building your own skills


GitHub creates their own command lines: [GitHub CLI].

[Git]: https://git-scm.com/
[more]: https://git-scm.com/book/en/v2
[Git Basics]: https://git-scm.com/video/get-going
[GitHub]: https://git-scm.com/book/en/v2/GitHub-Account-Setup-and-Configuration
[GitLab]: https://about.gitlab.com/
[Bitbucket]: https://bitbucket.org/
[GitHub CLI]: https://cli.github.com/manual/

### Something

We can add some source to make your skills
look delicious that impresses developers.
For example, starting with your terminal to use command lines
for dealing with GitHub.



## So you want to contribute to that repo/project

### On the webpage

Which we don't recommend because we don't want to be not-professinal.
But if you only need to edit a typo, it maybe resonable convenient
to do it directly on that page you have already reading.

### From terminal

Git clone


## What if I want to edit multiple files at the same time

Editor recommend: Atom
- [ ] add atom link


## Conclusion / Final

Open source maintainers mostly are happy to recieve contributions
if there are not too many requirements to them.
But contributors still creat new works for maintainers
even though contributors themselves may not feel so.


As a commen sense that developers generally do not like
marketers because they don't want to be pushed with
hype or not informative messages, that content only
marketers themselves care.
For content suggestions, I wrote [Thoughts on Developer Community Building](/posts/2020-02-25-thoughts-on-developer-community-building)
earlier this year.


How I use the hacks in RiB:

When I started RiB, I asked questions to my developer friends,
about how to keep it open to anyone to edit.
Some suggested GitHub (thanks for beliving in me),
some other suggested Wordpress for publishing because learning
GitHub, and Git will be too complex to me.
But I did want the content to be open to anyone from the day
it was created.
So I compromised to use GitHub repo for keep the original
content, and move the final posts to Wordpress for publishing.
It worked well for a while until someday
I realized that I don't want to be a middle man to
involve in any new chances for potential mistakes.

As you can see that nowadays, the RiB newsletter is
hosting on GitHub with direct and visible contributions.
Thanks to GitHub!
I expect someday it will turn to be a community managed
newsletter as well as the website.


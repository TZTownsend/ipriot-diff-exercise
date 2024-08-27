# Overview

This is a repo to help you practice diffing!


## Instructions

To get started:

1. Fork this repo.
⚠️ IMPORTANT: Fork all branches. Not just `main`
2. Clone your forked repo:
```bash
git clone <your-forked-repo-url>
```

Follow these instructions carefully.

## Diffing

A diff is a specific file format that tells you the difference between lines in a file and, optionally, words on that line. It contains enough context to make sense to humans and enough information to allow a machine to apply a difference to a set of files such that:

$$
A = B \circ \text{Apply}(\text{Diff}(A, B))
$$
That is, the difference between A and B can allow A to be transformed into B and vice versa using a function that **applies** said difference.

Let's now look at an example diff:

```diff
diff --git a/README.md b/README.md ①
index 7f35690..14cf26a 100644 ②
--- a/README.md ③
+++ b/README.md
@@ -8,9 +8,12 @@ ④
This is a repo to help you practice diffing!
 To get started:

 1. Fork this repo ⑤
-2. Clone your forked repo ⑥
+2. Clone your forked repo:
+```bash
+git clone <your-forked-repo-url>
+```

-Follow these instructions c.a.r.e.f.u.l.l.y. ⑦
+Follow these instructions carefully.
```

Fill in what each of the elements of the diff mean (if you are not sure just guess!):
**①**:
> Insert your explanation here

**②**:
> Insert your answer here

**③**:
> Insert your explanation here

**④**:
> Insert your answer here

**⑤**:
> Insert your answer here

**⑥**:
> Insert your explanation here

**⑦**:
> Insert your answer here


Notice that the diff above only showed different **lines** in the file. Including whitespaces. We can also highlight changes at the word level with the --word-diff option:

```diff
diff --git a/README.md b/README.md
index 68750c8..0413c51 100644
--- a/README.md
+++ b/README.md
@@ -49,13 +49,13 @@ This is a repo to help you practice diffing!

Fill in what each of the elements of the diff mean (if you are not sure just guess!):
**①**:
> Insert your [-answer-]{+explanation+} here

**②**:
> Insert your answer here

**③**:
> Insert your [-answer-]{+explanation+} here

**④**:
> Insert your answer here
@@ -64,12 +64,12 @@ Fill in what each of the elements of the diff mean (if you are not sure just gue
> Insert your answer here

**⑥**:
> Insert your [-answer-]{+explanation+} here
```

See if you can guess the overall command to produce the above diffs:

```bash
? your guess is as good as mine
```

 ## Stashing
> Make sure you attempted to fill in your explanation above!

Guess what!? Your lecturer has also got an answer to these questions! They are in another branch though! 

Let's go check them out so we can decide whether we like them better. Run the following git commad:

```bash
git switch answers
```

Did it work? If it did it just means you didn't follow the instructions carefully! 

If it didn't work, you have yourself a quandary:

* Do you commit the changes you made even though you might not end up using them?
* Do you discard your changes, even though your lecturer could be tricking you and there is absolutely no solution in the `answers` branch?
* Do you live forever in FOMO (Fear Of Missing Out)?

Bet you didn't expect an existential crisis learning git (well, you should!).

Lucky for you, there is one quality of life option we didn't mention: `git stash`.

This command *stashes* your changes safely away so you can come back to them later. It is like a commit to the "not sure what to do with this yet" branch.

So let's do that:
    
```bash
git stash
```

Notice that your answers are gone! But don't worry, they are not lost, just stashed away. You can get them back with:

```bash
git stash pop
```

pop goes the stash and your changes are back (and no longer on the stash).

Okay, stash them again, and then switch to the `answers` branch

Go ahead. Look at the answers. Notice that some are probably better than yours, some are worse. You want to merge your stashed changes with the current changes. You can do this in this branch (simply pop the stash here) or you can merge the answers into main and then pop your stash. Either way, this time popping the stash will be a bit more complicated because there are changes in the same file that you have made and that your lecturer has made.

So you will have a conflict like any other merge conflict. But by now you are a pro at this! So go ahead, pop the stash and resolve the conflict.


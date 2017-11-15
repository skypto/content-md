### Branching strategy

Using branch commands is simple.  Using them effectively takes some planning and discipline.  
* [simple local strategy](https://www.visualstudio.com/en-us/articles/git-branching-guidance)  - contradicts what i said about tags, wha-eva  
* [simple workflow walkthrough](https://www.atlassian.com/blog/git/simple-git-workflow-simple)  
* [Stackoverflow Discusion](https://stackoverflow.com/questions/2428722/git-branch-strategy-for-small-dev-team)  
* [From the GIT docs](https://git-scm.com/book/en/v2/Git-Branching-Branching-Workflows)
* [comparison of strategies](http://www.creativebloq.com/web-design/choose-right-git-branching-strategy-121518344)    
* [develop, release, master](http://drewfradette.ca/a-simpler-successful-git-branching-model/)  
* [three-flow](http://www.nomachetejuggling.com/2017/04/09/a-different-branching-strategy/)  - says its better than the advanced one
* [so many words](http://scottchacon.com/2011/08/31/github-flow.html)
* [advanced group remote/local branching strategy](http://nvie.com/posts/a-successful-git-branching-model/)  
* [a repo](https://github.com/steotia/branching-strategies)

### Atomic Commits
When you start working on big projects, you will be modifying multiple files which will all need saving. However, it's best practice to save files purposefully; we call this an **atomic commit**.

If we were to add all the files onto one stage and not think about making atomic commits, this would make your snapshot really crowded and congested - this is bad for two reasons:

First, you will not know why the snapshot was meaningful and if you wanted to find a specific snapshot you would find it difficult to trace what you were trying to accomplish with those files.

Second, imagine if your project got corrupted or your code has a bug you can't figure out and does not work anymore. If you were to put all your files onto one stage and then tried to load a previous snapshot known to be stable, you would lose a lot of progress with your work and then piecing all the files back to their desired state would be painstaking.

To get around this, only `git add` files that are thematically similar. For example if your project had a lot of text files and image files, you could stage all text files together for one snapshot and then all image files together for another snapshot.

All snapshots taken must have a message attached to it. When you have staged files purposefully (or with a theme), it's easy to decide what kind of message to include.

To take a snapshot, you would run `git commit -m "Initial commit"`. The `-m` flag stands for message and then you include your short message in between the quotation marks: `"Initial commit"`.


* More about writing [atomic commits](http://chris.beams.io/posts/git-commit/)
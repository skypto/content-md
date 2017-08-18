# Git and Hub 101
-----------------


### Why GIT and GitHub ?
* GIT: To organize your development process and protect your codebase against human error.
* GitHub: Because finished code isn't a finished project.  

In the colaborative world of web development, a project (or your piece of one) isn't finished until someone else can understand it - be it a co-worker, collaborator, yourself in a month, or some rando. GIT and Github allows you to protect your code against silly mistakes, organize, and document your code so others know how to use it and what to use it for.

-------
### What's GIT ?
* Git is a command-line application that allows you to travel through time.  Every commit saves a complete image of your directory structure at the time of commiting (actually your staged directory structure, but whatever for now). 
* Git allows you to create alternative universes.  With branches you can save two copies of the same directory that differ by a single file/method/bug/...  This is very practical for testing experimental features, fixing bugs, or sharing work across a group.
* Git allows you to commune with parallel dimensions.  'Pull' and 'push' allows your local git commit tree to synchronize with a git tree located anywhere on the internet.  This is how you will use GitHub and how multiple people are able to collaborate on the same codebase.

Git has more tricks up it's sleeves, but these 3 will carry farther than you can see without awakening your third eye.

### What's GitHub ?
tl;dr - it can be anything you need it to be.  

We'll be discussing the following uses in this course:
* Remote hosting for Git repositories.  With pushing and pulling, you can use GitHub to back up your work.  If you stop there, you're a fool. GitHub can do so much more for you.
* [Personal portfolio](https://elium-student.github.io). GitHub has built-in tools for hosting static pages. With a little ingenuity this can be used to build a pretty sick portfolio that's fully integrated with your GitHub account.

These are for you to explore on your own:
* Social network and linkedin for developers.
* Project hosting and project management.
* An infinite library of useful code to study or use. 
* Interactive documentation.
* Integrator with many apps - we've used sketchboard.io's integration.
* 

We've created this curriculum entirely on GitHub relying mostly on these features: github pages, organizations, issues, repo hosting, and projects.
___

### How does this all fit together ?

![](https://github.com/jankeLearning/diagrams/blob/master/git-hub/where-it-fits.png)

It is your everything; documentation, ... you name it, you an probably do it on github.  Plus all the cool people are already there. 
----
Git is like a really **epic save button** for your files and directories - officially Git is called a version control system.

To compare, a *save* in a text editor would record all of the words of a document as a single file. You are only ever given one record of the file like `essay.doc` unless you make duplicate copies (which would be difficult to remember to do and keep track of):

`essay-draft1.doc`, `essay-draft2.doc`, `essay-final.doc`

A *save* in Git however, would record differences of files and folders AND keep a **historical record of each save**. This feature is a game changer. As an individual developer, Git enables you to review how your project grows and to easily look at or restore file states from the past. Once connected to a network, Git allows you to push your project to GitHub for sharing and collaborating with other developers.

While Git works on your *local* machine, GitHub is a *remote* storage facility on the web for all your coding projects. This means that by learning Git, you will get to showcase your portfolio on GitHub! This is really important because almost all software development companies consider the ability to use Git as an **essential skill for a modern web developer** to have; having a portfolio will provide proof to future potential employers as to what you are capable of.

In this lesson we will briefly explore the history of Git, what it is and what it's useful for.

In the next lesson we will go over the basic workflow of using Git which should enhance your understanding and demonstrate why Git is so useful.

And finally, you will set up a project with Git and this will serve as a template for setting up your future projects.

But for now, in this lesson, try to understand what Git is and why it is so powerful!

## Learning Outcome:
*By the end of this lesson you should be able to:*

* Define what kind of program Git is
* Describe the differences between Git and a text editor in terms of what they save and their record keeping
* Describe whether Git and GitHub work at a local or remote level
* Describe why Git is useful for an individual developer and a team of developers

## Assignment:
1. Read chapter 1 in this book about [version control](https://git-scm.com/book/en/v2/Getting-Started-About-Version-Control) and appreciate the differences between local, centralised and distributed version control systems.
2. Now watch this [video](https://www.youtube.com/watch?v=8oRjP8yj2Wo) about how git can improve the workflow of an individual or a team of developers.
3. Get some [context](https://www.youtube.com/watch?v=1h9_cB9mPT8&feature=youtu.be&t=13s) of how git and GitHub came about. Make sure you know the difference between the two: note how Git is referred to as a technology used in the *command line* while GitHub is a *website* you can [visit](https://github.com/)
4. Have a look at The Odin Project's very [own repository on GitHub](https://github.com/TheOdinProject/curriculum) - this is where all the lessons are stored!
5. Finally, gain an appreciation of [how git records all collaborative efforts](https://github.com/TheOdinProject/curriculum/graphs/contributors) and how GitHub visually represents this.


## Additional Resources

*This section contains helpful links to other content. It isn't required, so consider it supplemental for if you need to dive deeper into something*

* [Git and Github in plain English](https://blog.red-badger.com/blog/2016/11/29/gitgithub-in-plain-english)


Some good places to study git:     
   * The [simple guide](http://rogerdudler.github.io/git-guide/) to git.  
   * Derek Banas [introduction videos](https://www.youtube.com/watch?v=r63f51ce84A), if you're into that sort of thing.  
   * The best place to [practice git branching](http://learngitbranching.js.org/).  
   * I you REALLY want to know [how git works](https://www.youtube.com/watch?v=1ffBJ4sVUb4&list=TLj1nt5nzukA8).    
   * Git's [documentation](https://git-scm.com/documentation).  
 
   * A [CLI game](https://www.git-game.com) for learning all of git.   

   https://github.com/adrianholovaty/git_workflow

   https://www.theodinproject.com/courses/web-development-101/lessons/introduction-to-git

   https://blog.red-badger.com/blog/2016/11/29/gitgithub-in-plain-english

   https://www.cleverism.com/complete-guide-github/

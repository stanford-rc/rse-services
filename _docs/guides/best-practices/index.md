---
title: Best Practices
---

# Best Practices

## Version Control

If you are new to programming, or writing scripts to run a scientific analysis,
it's essential to start using version control. 

{% include alert.html title="What is version control?" type="question" content="Version control is like having
a well organized, Mary Poppins-esche recipe box that can summon up any previous version of your code on demand, and multiple people can interact with contents without bumping heads. More formally, it means tracking changes in your source code over time. You can work on multiple features at once, and multiple people can collaborate on the same code base without bumping heads. If you want to do reproducible research, this is the first step." %}

Reproducible science calls for keeping a history of your work, and version control brings that to code, 
or any kind of text file that can be stored in a repository.

{% include alert.html title="What is a repository?" type="question" content="A repository, or sometimes referred to as a repo, comes down to a folder of files and subfolders that has a hidden folder, (usually .git) that stores history, branches, and other metadata about the project." %}

In practice, this means that you keep an entire history of your work. It means that collaboration is easy - you
can make changes without worrying about overriding someone else's. If an error is introduced
into the codebase, you can revert to a previous version. It makes it easy to associate
versions with release tags, so someone installing your software can reliably use the 
right version. It's also a lot of fun! Platforms like [GitHub](https://www.github.com) and [GitLab](https://www.gitlab.com)
have nice interfaces and facilitate fun interactions. Maintaining code is an interactive,
and fulfilling experience. It will help you whether you are working on your own,
or on a large project with many others.


### Services

When you create a repository on your local machine, you can create a remote version of it
that you push and pull changes from along with others working on the project. Thus,
the first thing you would want to do is sign up for one of these remote services.

 - **Recommended** [GitHub](https://www.github.com) has become a leader in version control, with great support for open source and the academic community.
 - **Others** include [GitLab](https://www.gitlab.com) and [BitBucket](https://bitbucket.org). Often, you might want to check with your group about what version control service they use. Since the underlying technology, [git](https://git-scm.com/), is shared between these services, while signing up for an account to participate on the platform would be required, there isn't any reason you can't jump around between them, even with the same code bases. This is possible, although not recommended.

### Getting Started with Version Control

We don't need to post getting started instructions here because there are many already
available!

 - [Software Carpentry](http://swcarpentry.github.io/git-novice/) offers a git novice course, and it's also available [in Spanish](https://swcarpentry.github.io/git-novice-es/).
 - [try.github.io](https://try.github.io/) has a listing of resources to learn by doing, reading, or participating.
 - [Best Practices](https://github.com/trein/dev-best-practices/wiki/Git-Commit-Best-Practices) exist for writing commit messages, which are little messages that you add when you want to save the current state of your repository.
 - [Understanding the GitHub Flow](https://guides.github.com/introduction/flow/) gives a nice overview of all the terms and how to manage a repository.

By far, the best way to get started is to read about the basics, and then create an account and jump in! if you
can't find the answer to a question, [just ask]({{ site.repo }}/issues/new).

## Testing and Code Coverage

It's easy to write a function, and then make a change somewhere else, and your function
breaks (and perhaps you don't notice). To prevent this from happening, we can
regularly test our software. If we want to add new code? We test that everything still works.
When it's time for a release? We ensure that everything builds.
There are three main types of testing, and of the three, two are essential:

### Unit Testing

Unit testing means breaking your code down into small components (e.g., a function to read a file)
and then testing that component. When you add a new function or feature, it should be standard to 
write tests for it.

### Regression Testing

Regression testing is about consistency. We want to ensure that if you give your software the
same input over time, it returns the same value.


### Recommended Libraries

 - **Python**: while there is the module unittest and several deprecated, we recommend using [pytest](https://pytest.org/en/latest/) for easy writing and running of tests. [Here](https://www.tutorialspoint.com/pytest/pytest_introduction) is a tutorial to get started.
 - **R**: you can use [testhat](https://testthat.r-lib.org/).
 - **C/C++/Fortran**: you can use [CTest](https://gitlab.kitware.com/cmake/community/wikis/doc/ctest/Testing-With-CTest).
 - **Matlab**: provides a [list of resources](https://www.mathworks.com/help/matlab/matlab-unit-test-framework.html) for testing.

## Continuous Integration

**under development**

## Code Style

**under development**


## Documentation

**under development**


## Build Systems

**under development**

## Software Design

**under development**
 
## Resources

Here are some useful external resources.

**under development**

Would you like to see another guide? Please [let us know]({{ site.repo }}/issues/new).

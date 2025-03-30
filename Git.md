Is a [[version control system]]

A version control system records all the changes that we make to our code and records them in a special database called a [[repository]]

We can  look at a project history and see who has changed what and revert to a previous version

Free, [[Open Source]], Fast and Scalable

Operations 
Branching 
Merging 

## Using Git

Command Line: 

Code editors and IDEs:

VS code: we have the source control panel which gives us the essential Git commands and extensions like GitLens

Git GUIs for every platform: GitKraken and SourceTree

Git [[Bash]]: Born Again SHell is a command prompt window that emulates UNIX or LINUX environments

## Configuring Git

we have to configure Name, Email, Default Editor and Line Ending

we can do that on three different levels

System Level: all users
Global Level: all repositories from the current user
Local Level: the current repository

In the Bash Shell: 

``` 
git config --global user.name "Esempio"

git config --global user.email "esempio@gmail.com"

git config --global core.editor "code --wait" (for VS code)
```
to open the default editor to view and modify the config file:

`git config --global -e 

end of lines in Windows are marked with two special characters:

1. \\r is the Carriage Return
2. \\n is the Line Feed

in Linux and MacOS it's just the Line Feed 

Windows: `git config --global core.autocrlf true

Linux/MacOS: `git config --global core.autocrlf input

# [[Git Commands]]

Help: ` git config --help

Reduced Help: ` git config -h

Create directory: `mkdir Example

Change directory: `cd Example

Initialize a new empty repository: `git init

List directories: `ls

List all directories: `ls -a

Open a directory/repository: `open .git

Remove (forcefully): `rm -rf

Show the repository status: `git status`

## Workflow


## [Git Documentation](https://www.git-scm.com/docs)

### Cheat Sheet

### Visual Cheat Sheet


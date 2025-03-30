## Configuration

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

## 